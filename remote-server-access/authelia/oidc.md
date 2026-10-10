[!badge text="Note" variant="danger"] Only set this up, if you are planning to add a client right after. Since if you set this up and don't have an app to use it, **Authelia won't start**. This set up only has to be done once. 

### Setting up OIDC

1. Go to Authelia's appdata folder and open configuration.yml. Scroll down until you see `identity_providers`. I've pasted it beforehand to avoid you the trouble of messing with indentations. Simply remove the hashtag. 

2. To get the HMAC secret, open the terminal and type this and paste it in there:
```
docker run --rm authelia/authelia:latest authelia crypto rand --length 64 --charset alphanumeric
``` 
3. Now CD into the appdata for authelia with `/cd /mnt/user/appdata/Authelia` and paste: 
```
docker run --rm -u "$(id -u):$(id -g)" -v "$(pwd)":/keys authelia/authelia:latest authelia crypto pair rsa generate --directory /keys
``` 
4. This created a private.pem file in Authelia's appdata folder. Copy the contents in the private.pem file and paste it under key. It's crucial for the identation to be the same as the example text.
5. Now continue with the installation instructions for the app you wanted to add to Authelia with OIDC. 

### hacking way

but they can still login with the nextcloud user and pass by adding `?direct=1` to the end of the nextcloud site. to disable this, go into advanced settings for proxy in npm and add 

```
if ($arg_direct = "1") {
    return 403;
}
```
