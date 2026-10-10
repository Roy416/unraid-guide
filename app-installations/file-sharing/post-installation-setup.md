<div style="color: black;">

# Post Installation Setup

### 📁 Folderview3 

First thing you probably said was "maan, this added like a gazillion containers on the Docker tab making it all ugly." Luckily for you theres a plugin called `folderview3`. After installing it, you'll see a `Add-Folder` button below all your containers. So you can group those containers in a folder, give it a picture, rearrange the order, and customize the colours.

### 🚫 Disabling Apps

There may be some features that are installed by default that you might not use. On the top right click on your **profile** → **Apps** → **Your apps**, and disable whatever you want.

### 🔏 Change Password/New Account

To change your password:

1. Click your **profile** on the top right and click **Accounts**.
2. Click on the **pencil icon** and enter a new password. Make sure to click the little arrow first before clikcing the check mark on the far right.

You won't be able to change the username. Instead you'd have to create a new account, log into that one, then delete the original admin account. On that same account page:

1. Click **New Account** on the top left and enter the **account name**, **password** and set the **groups** to admin. If you're using Authelia, set this account name as the same user name in Authelia, otherwise it will create a new Nextcloud account for you. Then login to the new account, and it'll let you delete the original admin account.

### 📱 Enable 2FA

To enable 2FA:

1. Click on your **profile** → **Administration Settings** → **Security** (under Administration)
2. Toggle **Enforce two-factor authentication**.
3. Then scroll up, and on the left, under the **Personal** header click **Security**, and **enable TOTP**.

### ⏪ NGINX Proxy Manager Fix

With NPM, Nextcloud can be fussy. After I added this to NPMs settings for Nextcloud, the issues stopped happening.

Go to **NPM** → edit the entry for **Nextcloud** → go to **Advanced** and **paste** the following:

```
client_body_buffer_size 512k; 
proxy_read_timeout 86400s; 
client_max_body_size 0;
```

You can go [here](https://github.com/nextcloud/all-in-one/blob/main/reverse-proxy.md#nginx-proxy-manager---npm) to see the recommended settings for NPM.

### 🖥️ Desktop Client

Nextcloud has a desktop client. So whenever you save a document in the Nextcloud folder, it'll be instantly backed up to your server. You can also choose so that all the Nextcloud files are also downloaded to your computer, creating another copy of them.

### 📱 Mobile App

Nextcloud does have a mobile app where you can view your files. However, the **issue with the app is, if you want to view something, it will download it in the cache on your phone.** Meaning, if you view 100 photos, it will download 100 photos on your phone, taking up space, until the app deletes it a week later. Which is why it's not ideal for it to be used to back up and view your mobile photos. 

### 🔄 Updating Nextcloud

Updating Nextcloud is a little different. To update it, click on your **profile** → **Administration settings** → **Open Nextcloud AIO Interface** → click **stop containers** → click **start and update containers**. 

On the docker page it might say the master container still needs an update. So apply the update on there too.

### 🌉 Removing Bridge Network 
You may have noticed that the Nextcloud master container has the networks of nextcloud_aio and bridge. You can remove the bridge network from it, but make sure to add the nextcloud_aio network to NPM so it can access Nextcloud. Refer to the [Custom Docker Network](../../apps&plugins/custom-docker-network.md) section. 

### ⬆️ Reinstalling Nextcloud

If you're reinstalling Nextcloud, you have to remove not only the containers but also the old volumes to have a clean slate. Here are the steps:

1. Remove all the Nextcloud containers.
2. In the terminal type: 
```   
sudo docker volume ls --format '{{.Name}}' | grep nextcloud_aio | xargs -r sudo docker volume rm
```
3. Type to see if there's any remaining volumes for Nextcloud. 
```
docker volume ls | grep nextcloud_aio
```
4. Delete the contents in the Nextcloud share.

</div>
