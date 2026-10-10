<div style="color: black;">

# Mapping Shares

{% hint style="info" %}
[Accompanying video by TechnGo](https://youtu.be/PePFc-eQCsY?si=_V3pszyVh35g5s3F\&t=165)
{% endhint %}

Here are all the ways you can map your shares on Windows and Mac OS:

### 🪟 Mapping Shares on Windows

1. Open **File Explorer** → **Network**, and your server should be there. 

2. Or open **File Explorer** → **This PC** → click on the **three dots** at the top → **Add Network Location** → enter `\\<server ip>\<share name>` (ignore the arrows). You could also click "Add Network Drive" instead of location, if you so choose.

### 🍎 Mapping Shares on MacOS

1. Open the **Finder** → **Network** → click on your **server**.

2. Or open **Finder** → press **CMD + K** → Enter `smb://<server ip>/<share name>` (ignore the arrows).

### 🚫 Error with Connecting?

If you're having trouble trying to your private/secure share, here are some things you can try.

Refresh the permissions of the shares:

1. Go to the **Tools** tab.

2. Select **New Permissions**.

3. Change the setting from **Disks** to **Shares**.

4. Only choose the **problematic shares** and click **Start**.

If that doesn’t work, some other things you can try are:

* Restarting your PC

* Restarting SMB by clicking the terminal (the **>\_** on the top right of the Web UI) and type 
`/etc/rc.d/rc.samba restart`  and restart your PC.

* Delete your login in the Windows Credential Manager ([shown here](https://youtu.be/PePFc-eQCsY?si=vihJ6fif8Plc-pzP\&t=167)), and restart your PC.

Another tip a user suggested was using the same user name and password as your windows login for your new Unraid user.

### 🤷🏽‍♀️ My Personal Experience

In my personal experience, the most **error-free way** to link your shares to your PC is through **network** **location** and selecting **“Remember my credentials”**.

The “Remember my credentials” checkbox only shows up if your Windows login is different from the Unraid user's credentials.

### 🐌 Why are my transfer speeds slow?

Make sure you mapped your shares **using your server IP** and not the server name. For me, using the server IP was 4 times faster.

You could also go into **Settings** → **Disk Settings** and change **Tunable (md_write_method)** to **reconstruct write**. ( aka Turbo Mode). However this makes it so all of your drives turn on when transferring files. 

</div>
