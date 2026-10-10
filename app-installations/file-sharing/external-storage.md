<div style="color: black;">

# External Storage

External Storage allows you to connect a share to Nextcloud. This is useful when you want to share files that is already in one of your shares, rather than having to copy and paste it into Nextcloud, and then sharing.

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vSnYhKqZEgRw4UpoF134JI_ofY6pp3AiZiKQAIjJsyO86PGeocBqrDY6vrRcSNcNVfZiApK1mVBqFPU/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

0. The external storage app may not be installed by default. If not, click on your **profile** → **Apps** → **Integration** → and find **External storage support** (featured). 
1. Click edit on the nextcloud-aio-mastercontainer.
2. Scroll down and click **"Add another Path, Port, Variable, Label or Device"**.
3. Change the **Config Type to Variable** and set the **Name** and **Key** to `NEXTCLOUD_MOUNT` and the **value** to `/mnt/user/YOUR_SHARE` and click **Save** and **Apply**. 
    - You do not want to share /mnt/user, as that's super unsafe. Unfortunatley it seems you can only add one share. 
4. Go to your **profile → Administration Settings → Overview** (under Administration) **→ Open Nextcloud AIO Interface → Click Stop Containers**. Once they're all stopped, **start them again**.
5. Once all the container are started, Go to your **profile → Administration Settings → External Storage** (under Administration). Click **Add external storage**
6. Give the folder a **name**, change External storage to **Local (server storage)**. You can restrict the storage to specific users or a group. If nothing appears when you click on it, start typing the name of the user or group and it'll appear. 
7. **Set the location** to `/mnt/user/YOUR_SHARE/` (e.g. /mnt/user/media/books).
8. If you want to enable sharing, click **Mount options** and toggle **Enable Sharing**. You can also enable **Read only** which could be useful when adding other people to your Nextcloud instance. Click **Create**. Enter your password if it asks for it. 

</div>
