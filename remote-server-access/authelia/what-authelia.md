<div style="color: black;">

Authelia is known as a SSO (Single Sign-On). It isn't necessary to set up right away, but it's the next step in security if you're accessing your apps remotely via port forwarding or cloudflare tunnel. If you're using Tailscale, you can ignore this, unless you don't trust the users you've given access to your tailnet. 

A SSO does two things:

1. Sets up **two factor authentication** for your sites. With either an authenticator app or passkey. 

2. Lets you **log in with the same username and password** across all your sites, hence *single sign-on*. 

There are two ways of setting up Authelia for an app, with **forward authentication** or with **OIDC**. With forward authentication the setup goes through NPM and is a lot easier. However this way isn't compatible with an app's mobile app and desktop client, which is where OIDC comes in. 

OIDC is the built-in way for an app to use Authelia (and other services like it). The extra setup for OIDC isn't too bad, but you know, all this setting up can get tiring. Not all apps support OIDC. You can see the list HEREEE

Some apps have 2FA built-in, such as Nextcloud, which takes seconds to set up. So if you only need 2FA for Nextcloud for example, you could skip setting up Authelia. 

If using cloudflare tunnels, OIDC doesn't require a reverse proxy where as forward authentication does. 

</div>
