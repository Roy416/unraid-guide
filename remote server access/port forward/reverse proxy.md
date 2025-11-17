---
label: Reverse Proxy
order: 998
---
# Reverse Proxy

A **reverse proxy** looks like an intimidating term, but what this basically does is links your URLs (e.g., nextcloud.domain.com) to your apps so that you can access them outside of your home. You’ll be making these URLs in the next part.

### Installation

1. Search `nginxproxymanager` from the app store and install.
2. Change the HTTP port from 80 to 1880 and the HTTPS port from 443 to 18443.
3. Open the Web UI of NPM and enter the default credentials that was written in the overview, `user: admin@example.com` and `password: changeme`. Change the email and password.
4. Go to your router settings, to the port forwarding section, and enter these 2 entries. Remember to click save!

<table><thead><tr><th>Name</th><th width="179.36663818359375">Port From (External)</th><th>Port To (Internal)</th><th>IP Address</th></tr></thead><tbody><tr><td>HTTP</td><td>80</td><td>1880</td><td>your server ip</td></tr><tr><td>HTTPS</td><td>443</td><td>18443</td><td>your server ip</td></tr></tbody></table>

5. Remember those certificates we made in the previous section? Let's add them in. Open NPM, Click SSL Certificates on the top bar, Click Add SSL Certificate, and Click Custom.
6. Give your Certificate a name, for the Certificate Key, choose the .key file, and then the .pem file for the other Certificate. Click Save.
