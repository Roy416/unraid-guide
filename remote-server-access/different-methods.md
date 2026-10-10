<div style="color: black;">

# Different Methods

In this section, we will be setting up the network that will allow you to access your apps outside of your home. If you don’t plan on needing remote access, you can skip to the [Apps & Plugins](../apps&plugins/understanding-docker.md) section.

There are 3 ways to connect your server remotely; **VPN**, **Port Forwarding**, and **Cloudflare Tunnel**. I'll be explaining each of these. There is also a TLDR chart at the bottom.

## 🕸️ VPN

VPN stands for Virtual Private Network and it's awesome. You may have seen ads for VPNs, this uses the same technology but for a slightly different purpose. You can think of it as having your own private tunnel, where nobody else can see the data that goes through it nor can they hack into it, and it's free!

VPNs have all the positives except for one. Which is, if you want your friends to access an app on your server, they must also have the VPN client downloaded and be connected to your network. So the hardest part of this method is getting them to do the few minute setup 😅. 

## ⏩ Port Forwarding

With this method, your friends can easily access your apps. To achieve this, it does come with some compromise to your security. With this, you're *opening a port* so your friends can connect to it, but potentially so can the hackers that are scanning for open ports.

Whether this is safe or not depends on the security of the app you're running behind that port. So if the app is popular and is constantly getting updates, then the chances of you getting compromised is low but technically always exists.

In order to connect to your apps remotely, you would need to purchase a domain which go for $10-$30 per year. We will also be using Cloudflare for protection, however that invites an upload restriction of 100mb. I found this to be a problem when long videos on my phone were trying to be backed up.

## 🚇 Cloudflare Tunnel

Cloudflare Tunnels has been touted to be the best method as it's quick to set up, secure, and your friends can easily access it. However it has one big caveat. Which is, it is **NOT meant to be used for large data transfers**. This includes no media streaming, no transferring of files, etc. So it's best served for static websites (e.g. Seer, recipe sharing website, idk).

Some people still debate on what Cloudflare’s TOS applies to, or if there is a way around it.  Technically you’re still able to do it, but it’s up to you if you want to take the chance of getting banned.

Another downside is, since you are using Cloudflare's Tunnel, **any data that you send or receive is being seen by Cloudflare**. Whether this is concerning or not depends on you. Cloudflare's bread and butter is providing security, so you would think them seeing your data is not an issue. But if you're sensitive to privacy then this is a no go.

And like the Port Forwarding method, you would need to purchase a domain and there would be the same upload restriction.

## 🤷 So..what do I use?

Ideally you would want most of the apps you want to use remotely under a VPN, as it's really secure and has no data restrictions.

If you want to share Media Servers/Google Drive alternatives with your friends you could use the Port Forwarding method. For Plex only (due to its magic), you simply have to open its port and can avoid the lengthy setup. You *can* use the VPN method to share Media Servers however that requires your users to set it up and the support for VPNs on devices such as the Firestick isn't really great right now. 

Then if you want to share apps with static websites and want to avoid Port Forwarding, you can use Cloudflare Tunnels.

| Methods | 🟢 Pros | 🔴 Cons |
| --------- | --------- | --------- |
| 🕸️ VPN    | <ul><li>Free</li><li>Very secure</li><li>Private</li><li>Easy to set up</li><li>No download or upload restrictions</li></ul>      | <ul><li>Friends must be connected to VPN to access services</li></ul>    |
| ⏩ Port Forwarding    | <ul><li>Friends can easily access services </li><li>Private</li><li>No download restrictions</li></ul>  | <ul><li>Security concern</li><li>Annual cost ($10-$30/yr)</li><li>100mb upload restriction</li><li>Longest to setup</li></ul>     |
| 🚇 Cloudflare Tunnel    | <ul><li>Friends can easily access services</li><li>Secure</li><li>Easy to set up</li></ul>      | <ul><li>Download restrictions (meant for static sites, no streaming or downloading)</li><li>Not private (Cloudflare sees all data sent and received)</li><li>Annual cost ($10-$30/yr)</li><li>100mb upload restriction</li></ul>    |

</div>
