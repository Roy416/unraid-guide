---
label: Different Methods
order: 1001
icon: number
---
# 🔢 Different Methods

In this section, we will be setting up the network that will allow you to access your apps outside of your home. If you don’t plan on needing remote access, you can skip to the Apps & Plugins section.

There are 3 ways to connect your server remotely; **VPN**, **Port Forward**, and **Cloudflare Tunnel**. I'll be explaining each of these. There is a TLDR chart at the bottom.

## 🕸️ VPN

VPN stands for Virtual Private Network and they're awesome. You may have seen ads for VPNs, this uses the same technology but for a slightly different purpose. You can think of it as having your own private tunnel, where nobody else can see the data that goes through it nor can they hack into it, and it's free!

VPNs have all the positives except for one. Which is if you want your friends to access an app on the server, they must also have the VPN client downloaded and connected to your network. It would also require some tinkering so your friends only have access to the app and not your entire server.

## ⏩ Port Forward

With this method, your friends can easily access your apps. To achieve this, it does come with some compromise to your security. With this, you're *opening a port* so your friends can connect to it, but so can the hackers that are scanning for open ports.

Whether this is safe or not depends on the security of the app you're running behind that port. So if the app is popular and is constantly getting updates, then the chances of you getting compromised is low but technically always exists.

In order to connect to your apps remotely, you would need to purchase a domain which go for $10-$30 per year. We will also be using Cloudflare for protection, however that invites an upload restriction of 100mb. I found this to be a problem when long videos on my phone were trying to be backed up.

## 🚇 Cloudflare Tunnel

Cloudflare Tunnels has been touted to be the best method as it's setup quick, secure, and your friends can easily access it. However it has one big caveat. Which is, it is **not meant to be used for large data transfers**. This includes no media streaming, no transferring of files, etc. So it's best served for static websites (e.g. Overseer, recipe viewing website, idk).

Some people still debate on what Cloudflare’s TOS applies to or if there is a way to go around it.  Technically you’re still able to do it, but it’s up to you if you want to take the chance of getting banned.

Another downside is, since you are using Cloudflare's Tunnel, **any data that you send or receive is being seen by Cloudflare**. Whether this is concerning or not depends on you. Cloudflare's bread and butter is providing security, so you would think them seeing your data is alright. But if you're really sensitive to privacy then this is a no go.

And like the Port Forwarding method, you would need to purchase a domain and there would be the same upload restriction.

## 🤷 So..what do I use?

Ideally you would want most of the apps you want to use remotely under a VPN, as it's really secure and has no data restrictions.

If you want to share Plex/Jellyfin/Google Drive alternative with your friends you can use the port forwarding method. For Plex only (due to its magic), you simply have to open its port and can avoid doing this.

Then for any static websites that you want to share (e.g. Overseerr), you can use Cloudflare Tunnels.

<table><thead><tr><th width="127">Methods</th><th>🟢 Pros</th><th>🔴 Cons</th></tr></thead><tbody><tr><td>VPN</td><td><ul><li><mark style="color:green;">Free</mark></li><li><mark style="color:green;">Very secure &#x26; private</mark> </li><li><mark style="color:green;">Easy to set up</mark></li><li><mark style="color:green;">No download or upload restrictions</mark></li></ul></td><td><ul><li><mark style="color:red;">Friends must be connected to VPN to access services</mark></li></ul></td></tr><tr><td>Port Forward</td><td><ul><li><mark style="color:green;">Friends can easily access services</mark></li><li><mark style="color:green;">Private</mark> </li><li><mark style="color:green;">No download restrictions</mark></li></ul><p></p></td><td><ul><li><mark style="color:red;">Security Concern</mark></li><li><mark style="color:red;">Annual Cost ($10-$30/yr)</mark></li><li><mark style="color:red;">100mb Upload Restriction</mark></li><li><mark style="color:red;">Longest to setup and sometimes fickle</mark></li></ul></td></tr><tr><td>Cloudflare Tunnel</td><td><ul><li><mark style="color:green;">Friends can easily access services</mark></li><li><mark style="color:green;">Secure</mark></li><li><mark style="color:green;">Easy to Setup</mark></li></ul><p></p></td><td><ul><li><mark style="color:red;">Meant for static sites (no streaming, downloading)</mark></li><li><mark style="color:red;">Cloudflare sees all data sent and received</mark></li><li><mark style="color:red;">Annual Cost ($10-$30/yr)</mark></li><li><mark style="color:red;">100mb Upload Restriction</mark></li></ul></td></tr></tbody></table>

\\
