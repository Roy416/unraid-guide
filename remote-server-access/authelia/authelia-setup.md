{% hint style="info" %}
[Accompanying video by AlienTech42](https://www.youtube.com/watch?v=LRFwjATqFdw&t=)
{% endhint %}
   
### Setting up configuration files

1. Install Authelia. if you're using custom docker networks, make sure it's on a network that NginxProxyManager has access to.
2. Open the Unraid terminal and run this command. This will create three random strings. Keep these on a temporary notepad:
```
for i in 1 2 3; do openssl rand -base64 32; done
```
3. Now enter the command below. The random password is the password to your Authelia account. Keep both of these in a temporary notepad as well. This will also create a container with a funny name, you can delete it after. 
```
docker run --rm authelia/authelia:latest authelia crypto hash generate argon2 --random --random.length 64 --random.charset alphanumeric
```
4. Download these files. They are based off of [AlienTech42's configs](https://github.com/AlienTech42/unraid-config-files/tree/main/authelia):

[!file icon="rocket" text="configuration.yml"](../../assets/configuration.yml)

[!file icon="rocket" text="users_database.yml"](../../assets/users_database.yml)

5. Open configuration.yml with an editor. Replace `YOUR_DOMAIN` with your domain (e.g. https://nextcloud.example.com, the domain is example). A replace all feature would be handy here. 
6. There are 3 lines where you must replace `REPLACE_WITH_RANDOM_STRING` with the three random strings you created before. Under:
    - session, secret.
    - storage, encryption_key.
    - identity_validation, jwt_secret.
    - Save the file.
7. Open users_database.yml. Under users, rename `user` to what you want your login name to be. Replace the password with the Digest you created before. And change the display name and email. Click Save. 
    - By itself, `admins` in groups means nothing. This is for Access Control Lists (ACL), for when you want only certain people to access the site. Refer to the subject section in [this configuration](https://www.authelia.com/configuration/security/access-control/#configuration)
8. On Unraid go to Authelia's appdata folder. Delete the configuration.yml that exists, and upload the configuration.yml and the users_database.yml you just edited. Restart Authelia.

### Exposing Authelia
1. Expose Authelia as your normally would with either portforwarding or cloudflare tunnels. The protocol is `http` and the port is `9091`. Make the subdomain to `auth`. 
2. Go to your Authelia site, login with the password you created in step 3 above.
3. Click Register device and either select WebAuthn Credentials (passkey) or One-Time Password (authenticator app). It will ask for a OTP. Go to the appdata folder for Authelia and open `notifications.txt` to get it.
4. Then depending on what you chose, continue setting up via authenticator app or password manager. 

Sometimes when you log into your authelia site and put your 2FA in, it'll give you a blank screen. In the url field add the `auth.` back in infront of your domain, for whatever reason it removes it. Then youll be able to manage your devices.

Even though you have 2FA enabled, if you log into Authelia with just your user and password, it'll let you manage your devices without completing the 2FA. Fortunatley, if a person does get in, they can't really do anything, since it requires them to have access to your server files to make any changes.

### Using Authelia on an app (Forward Authentication)
Now lets setup an app to use authelia. If you're using cloudflare tunnels, this requires you to set up Nginx Proxy Manager. 

0. In the configuration.yml by default, I made it so every site that uses Authelia through NPM is automatically set to two factored authenication, so you dont have to go into the config every time. If you want to change this, remove the asterix on line 33, and uncomment lines 45 and 46.
1. Set up your app for remote access. If you're using cloudflare tunnels, create a proxy for it within NPM too. 
2. Edit the proxy, click the cog on the top right, then paste the script below respective to the method you chose, replacing `SERVER_IP` and `YOUR_DOMAIN` with your own:

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f511">⏩</span> Port Forwarding</summary>

```
# Fix large cookie issues (Authelia)
client_header_buffer_size 16k;
large_client_header_buffers 4 32k;

# Enable Authelia authentication
auth_request /authelia;

# Internal Authelia verification endpoint
location = /authelia {
    internal;
    proxy_pass http://SERVER_IP:9091/api/verify;



    proxy_set_header X-Original-URL $scheme://$host$request_uri;
    proxy_set_header X-Forwarded-Proto $scheme;

    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

    # Required for auth_request
    proxy_pass_request_body off;
    proxy_set_header Content-Length "";
}

error_page 401 =302 https://auth.YOUR_DOMAIN.com/?rd=$scheme://$host$request_uri;
```

</details>

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f511">☁️</span> Cloudflare Tunnels</summary>

```
# Fix large cookie issues (Authelia)
client_header_buffer_size 16k;
large_client_header_buffers 4 32k;

# Enable Authelia authentication
auth_request /authelia;

# Internal Authelia verification endpoint
location /authelia {
    internal;
    proxy_pass http://SERVER_IP:9091/api/verify;                                      # CHANGE THIS (AUTHELIA-IP)

    # REQUIRED for Cloudflare Tunnel setups
    # Force HTTPS since Cloudflare terminates SSL

    proxy_set_header X-Original-URL https://$http_host$request_uri;
    proxy_set_header X-Forwarded-Proto https;

    # Pass real client IP from Cloudflare
    
    proxy_set_header X-Real-IP $http_cf_connecting_ip;
    proxy_set_header X-Forwarded-For $http_cf_connecting_ip;

    # Required for auth_request
    proxy_set_header Content-Length "";
    proxy_pass_request_body off;
}

# Redirect unauthenticated users to Authelia login
error_page 401 =302 https://auth.YOUR_DOMAIN.com/?rd=https://$http_host$request_uri;     # CHANGE THIS (YOURDOMAIN)
```

</details>

### Adding a new user

1. Go to Authelia's appdata folder and open users_database.yml. 
2. Copy and paste the existing user. Make sure the indentation is the same!
3. Open the terminal and type the command below. As before, the random password is what the user will log into Authelia with.
```
docker run --rm authelia/authelia:latest authelia crypto hash generate argon2 --random --random.length 64 --random.charset alphanumeric
```
4. Paste the digest in password. Change the remaining fields.
