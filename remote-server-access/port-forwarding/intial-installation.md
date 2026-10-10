<div style="color: black;">

{% hint style="info" %}
[Accompanying video by IBRACORP](https://www.youtube.com/watch?v=c6Y6M8CdcQ0&t)
{% endhint %}

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vQfZNcHnbe5AwCtnoEji6VJBmh-iyN060GamAv8It3d9teIWtjWrl4pUF1HYOfCWJicWc3DA1RfBAQZ/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

[!badge text="Note" variant="danger"] Cloudflare is constantly changing their website, so in the future the names of things or button placements will change, but the same stuff needs to be done nonetheless.

1. **Buy a domain** from a registrar of your choice.
2. **Sign up with Cloudflare** using the free plan, **enter your domain**, and select **Manually enter DNS records**, and click Next. The DNS records page should now appear, this page lets you create URLs and connects them to your server. 
3. Let's add your domain. First, we need to get your public IP address. **Google** `what is my ip address` and click on the first link, and **copy the address**. If you have a VPN on, make sure it turn it off.  
4. Go back to the DNS Records page and **click Add Record**. Under name enter `@` and under IPv4 address enter the public IP address you got in the last step. Click save then click continue to activation.
5. It'll now ask you to **replace your domain registrar's nameservers** with Cloudflare's own nameservers. 
6. Go to your **domain registrar's settings** and find the **DNS section**. Next, it should say somewhere to use custom nameservers. Remove the old ones if they appear, and add both of the nameservers that Cloudflare gave.
7. Go back to Cloudflare and **click "Done, check nameservers**." This could take a few mins to 30 minutes, or even longer. You'll get an email when it's done.

</div>
