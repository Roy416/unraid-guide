<div style="color: black;">

# Using Tailscale Instead

{% hint style="info" %}
[Accompanying video by Spaceinavder](https://www.youtube.com/watch?v=FU1vdM4dIhY\&t)
{% endhint %}

Unfortunatley Nextcloud AIO requires a domain. So instead of purchasing a domain, you can use your Tailscale domain instead. Currently if you type in your Tailscale IP (e.g. unraidserver.fox-garibaldi.ts.net), it would take you to your Unraid server. What we plan to do is redirect this URL to Nextcloud. You're probably thinking, "But what if i want to view the Web UI with the Tailscale IP?" You will still be able to, but you'll have to add an extra port at the end when inputting the IP in your browser.

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vSeGPV05T9kchAvpoJD2hSVtp7-jNMeviG4j4LFGUchfgb54Z4aX2aQE0wx-yQvjShmuz_mZE_5d6AK/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

1. Go to **Settings → Management Access** .You will  see your **Tailscale URL**. If you type this URL it will take you to the Unraid Web UI. Still on this page, change the HTTPS Port from **443 to 4443**. Now if you wanted to access the Unraid Web UI with the Tailsacle IP, you'd have to add 4443 at the end (e.g. unraidserver.fox-garibaldi.ts.net:4443). Now that port 443 is free, we can assign it to Nextcloud.
2. **Open the terminal** and enter  `tailscale serve --bg --https=443 http://127.0.0.1:11000`. This created a Tailscale IP for Nextcloud. However, if you were to restart your server or Nextcloud, this command wouldn't be in effect, so let's address that.
3. Go to Apps and download **User Scripts**.
4. Go to **Settings → User Scripts** → click **Add New Script** and give it a name.
5. Copy the command in Step 2, and click on the **cog** of the script you just created → click **Edit Script ** → **paste the command** under #!/bin/bash. Click **Save Changes**
6. Then on the right, change **"Schedule Disabled" to "At First Array Start Only"**. 
7. Go to the **Docker tab** and click **Edit on Nextcloud Master container**, click **More Settings**, and set **Skip domain check** to `True`. Click **Apply**.
8. Open the **Web UI** for Nextcloud and enter your Tailscale IP `server.sillyname1-sillyname2.ts.net` (e.g. andromeda.fox-garibaldi.ts.net), and click **Submit Domain**.
9. Go back to the [installation page](installation.md) and continue from **step 8**.

</div>
