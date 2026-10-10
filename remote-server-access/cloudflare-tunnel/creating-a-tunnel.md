# Creating a Tunnel

<div style="color: black;">

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vS4dACOsknxvk4i2J3HEklMpYU026yD6y6gjesGs1g0L9NBuj9SJB6aRqqAj3Y2IzzPenpf8CkJag6H/pubembed?start=false&loop=false&delayms=3000"
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

1. On the Cloudflare Dashboard, on the sidebar, look for **Protect & Connect** and click **Zero Trust**. 
2. Expand **Networks** and click **Tunnels & Mesh**. Click **create a Tunnel**. 
3. Select **Cloudflared** as your tunnel type and give your **tunnel a name**. 
4. Change the device's operating system to **docker**. **Copy the token**. 
5. Go to **Unraid's Community Apps** and **search** for `cloudflared` and download the template by `Figro`. 
6. **Paste the token** in tunnel token. **Remove the text** `docker run cloudflare/cloudflared:latest tunnel --no-autoupdate run --token ` before the token including the space, so that only the token remains. Click **Apply**. 
7. Go back to the **Cloudflare page**, and **under Connectors** you should see your server. Click **Next**. 
8. It will ask you to set up an application for remote access. If you're not ready, you can close this and come back later to the next section.

</div>
