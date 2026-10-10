<div style="color: black;">

1. Set up [OIDC for Authelia](../../remote-server-access/authelia/oidc.md) if you havent already. 
2. Go to Authelia's appdata folder and open the configuration.yml. Scroll down until you see `clients`. Delete the hashtag for the client header and the nextcloud section.
3. Open the terminal and run the command below.  

```
docker run --rm authelia/authelia:latest authelia crypto hash generate pbkdf2 --variant sha512 --random --random.length 72 --random.charset rfc3986
```
4. This created a random password and a Digest. Paste the Digest password in client secret field (with the quotes). 
5. Under `redirect_uris`, replace YOUR_DOMAIN with your domain. Save the file and restart Authelia.
6. Go to Nextcloud and install the app called `OpenID Connect user backend`. 
7. Go to your profile -> administration settings -> click OpenID Connect (under administration) and click add a Registered Provider. 
8. Enter the following fields:

| Field | Value  | 
| --------- | --------- | 
| Identifier   | Authelia    |     
| client_id    | nextcloud   |     
| Discovery endpoint   | https://auth.YOUR_DOMAIN.com/.well-known/openid-configuration - Add your domain   | 
| scope    | openid email profile groups   |    
| Attribute Mapping   | preferred_username     |     
| Authentication and Access Control Settings    | Uncheck use unique user ID    |

9. Log out of Nextcloud and try log back in, and you'll see a Login with Authelia button now!

**how to remove regular login**

'hide_login_form' => true,
'auth.webauthn.enabled' => false,
'simpleSignUpLink.shown' => false,

try changing this in the config.php

link the page for nextcloud-aio for authelia

</div>
