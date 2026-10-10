<div style="color: black;">

Have you ever wished to be able to share photos to your friends and family without needing to expose all of Immich? Look no further, Immich Public Proxy is here! The experience isn't exactly the same as Immich, but it's good enough. 

The downside currently is that, when you try to copy the link it won't let you unless you're accessing the page through https. Which kind of goes against not needing to expose it. But! If you add Immich to your tailnet via TSD Proxy, then it lets you. 

1. In Docker, create a stack for Immich Public Proxy, and edit the Compose file. Copy the contents of the [docker-compose.yml](https://github.com/alangrainger/immich-public-proxy/blob/main/docker-compose.yml), and paste it in the compose file.
2. For `PUBLIC_BASE_URL` add the subdomain (e.g. immich.example.com). For `IMMICH_URL` add your server IP. Click Save and Compose Up.
3. Expose Immich Public Proxy's port `3000` via reverse proxy or Cloudflare tunnel. Make sure the subdomain is the same that you entered for `PUBLIC_BASE_URL`. 
4. Go to **Immich** → **profile** → **Administration** → **Server Settings** and **add the same subdomain**. 

</div>
