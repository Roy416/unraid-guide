<div style="color: black;">

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vR5jXlargncLgBnoRDGvObkgnW6kDXT0hIuwghLsT_7_DRdKwN2CEEvnVY-q8qMamPMntwVTVS7XIor/pubembed?start=false&loop=false&delayms=3000"
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

1. First note the **Web UI port** of the container you want to access remotely. You'll find it on the docker tab, under the **LAN IP:Port** of the container. If there are multiple ports listed, click edit on the container, as it's usually stated in the description which one is the Web UI port.
2. Open **Nginx Proxy Manager** → **Proxy Hosts** → **Add Proxy Host**.
3. **Create the subdomain** (e.g. seer.domain.com). Make sure to click add, as sometimes it doesn't enter properly.
4. Whether or not you should use http or https depends on the app. **Majority of the apps use http**, but some do use https (e.g. Nextcloud). If you have any doubts of which one you should select, a quick google should clear that up.  
5. For the **Forward Hostname/IP** → **your server IP**. And for **Forward Port** → **Web UI port**.
6. You can **enable Cache Assets** and **Block Common Exploits**, these are basically optional. If it doesn't work, try turning these off and enabling them one at a time. **Containers that refresh by themselves require Websockets support enabled**, it doesn't hurt to turn this on anyways. 
7. **Click SSL** and choose your **custom certificate**. **Enable Force SSL** and **HTTP/2 Support**. **It's better to have HSTS enabled**, but if something isn't working try disabling this. Force SSL can cause some issues, try disabling this if something isn't working as it should. Click **Save**. 
8. Now head on over to **Cloudflare** → click on your **Domain** → and go to its **DNS Records**. Click **Add Record** → change the type to **CNAME** → for name enter the **subdomain** → for the target enter your **domain**.
9. All done! Now try entering that URL in your browser and hopefully you can see your container!

</div>
