---
label: Extra Security & DDNS
order: 999
---
# Extra Security & DDNS

### Enabling DNSSEC

1. On Cloudflare, Click DNS, and then Settings. and Enable DNSSEC. And it should give you a bunch of keys and numbers.
2. Go to your Domain Registrar's settings, and under the DNS settings, find DNSSEC section.
3. Click to add a new DS, and enter whatever information it asks from the list of keys and numbers cloudflare gave you before. and click Save.

### Creating your own certificate

1. On the left side bar, click SSL/TLS, and then click Configure. And select Full (strict).
2. Then under SSL/TLS on the left, click Origin Server. And click Create Certificate.
3. Open up a notepad, copy the PEM text and save it as a `.pem` file. Similary for the private key, open another notepad, copy it, save it as a `.key` file.

### DDNS

Typically we would enter our public ip address into cloudflare ourselves and connect it to our domain.  Well, it has a habit of changing. It could change in a day, in a week, or in a month, making you unable to connect to your apps remotely.

That is where Dynamic DDNS comes in. If the Public IP address happens to change, the Dynamic DDNS will automatically update it, so you can continue to use your services like nothing ever happened.

1. First, let's grab your Cloudflare API key. Go to Cloudflare, on the top right click on the user icon and click Profile, click on API Tokens, and copy the Global API Key.
2. On the community apps, search for Cloudflare-DDNS by Selfhoster Tools.
3. Enter the email associated with Cloudflare, the API key you just got, and your domain. Click Apply.
4. Now if you go to Cloudflare's DNS Records, your domain will appear with your public IP Address.
