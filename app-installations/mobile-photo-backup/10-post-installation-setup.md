<div style="color: black;">

### 📱 Mobile App

If you're using a **domain you purchased**, enter your server URL with **https**, even though that's not what you put in NPM. If you're using a **Tailscale address** (e.g. 100.96.55.104) then you can keep it at **http**.

### ⬆️ How to Update

Since we installed Immich through Docker Compose, we'll have to update it with a different way. It'll always show that an update is available but that **isn't to be trusted**. Instead click `Update Stack` button next to Immich's stack. 

You'll know when there's an update because a pop up will appear when you're using Immich. 
I recommend skimming Immich's Github page in case there's anything you need to do on your end before updating. It rarely happens but just in case. 

### 🔄 Auto Start

To make Immich auto start, enable it by toggling the **slider beside its stack**. NOT by enabling auto start on each container. 

### ⏪ Nginx Proxy Manager Settings
Here are Immich's recommended settings for NPM. Click **edit** on the proxy for Immich in NPM → click the **cog** on the top right, and **paste this**:
```
client_max_body_size 50000M;
proxy_request_buffering off;
client_body_buffer_size 1024k;
proxy_read_timeout 600s;
proxy_send_timeout 600s;
send_timeout 600s;
```

### 🕸️ Enabling TSD Proxy

Since we installed Immich with Docker Compose, label manager can't see its containers. But we can manually add it. 

1. **Edit Immich's Docker Compose** and under immich-server service scroll down. 
2. Under networks add the following. Make sure networks and labels are in the same indentation. Change tsdproxy.name to whatever you want the subdomain to be. **Restart** Immich.
3. Go to **Tailscale** to find Immich's machine, and **approve** it. 
```
    labels:
      - tsdproxy.enable=true
      - tsdproxy.name=photos
      - tsdproxy.port=2283
      - tsdproxy.ephemeral=false
      - tsdproxy.persistent=true
```

</div>
