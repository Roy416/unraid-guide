---
label: Initial Installation
order: 999
---

# Initial Installation

{% hint style="info" %}
[Accompanying video by IBRACORP](https://www.youtube.com/watch?v=c6Y6M8CdcQ0)
{% endhint %}

**Note**<mark style="color:red;">**:**</mark> <mark style="color:red;"></mark><mark style="color:red;">Cloudflare is constantly changing their website layout, so in the future these steps may not exactly depict what to do, but the same stuff needs to be done none the less.</mark>

1. **Buy a domain** from a registrar of your choice.
2. **Sign up with Cloudflare** using a free account, enter your domain, and it should prompt you to do a quick scan for DNS records.
3. After the scan, the DNS records page should appear. If not, on the bar on the left, click DNS and then Records. This page lets you create URLs and connects them to your server, we will come back to this later. Click continue.
4. It'll now ask you to **replace your domain registrar's nameservers** with Cloudflare's own nameservers. <mark style="color:red;">What is a nameserver</mark>
5. Go to your **domain registrar's settings** and find the **DNS section**. Next, it should say somewhere to use custom nameservers. Add both of the nameservers that Cloudflare gave.
6. Then go back to Cloudflare and **click "Done, check nameserver**s." This could take a few mins to 30 minutes, or even longer.
