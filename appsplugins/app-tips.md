<div style="color: black;">

### 🌐 Web UI Port

When you install an app, you will see all these addresses under port mappings in the docker. You might be confused on which port to use to access the local Web UI. One way to check is to click on the Web UI button of the app and see what port is written after your server’s IP in the address bar. Or you can click on the app, click edit, and see what port is stated for Web UI.

The one rule when it comes to Web UI ports is that **two apps cannot have the same port**. So when you click to install an app, the first thing you should do is look at the port, scroll down to "show docker allocations", and see if that port is already used by another app. If it is, then change it to something that isn't already in use. 

### 📜 Container Logs

When you start a container and try to go to its Web UI, it might give you an error. That's because it's probably still starting up. You can check what it's doing by clicking on the container and clicking logs. If you're looking for what errors may be occuring or if the app ever sends you a code of some sorts, you'll find it here.

### 🗑️ App Removal

When you remove an app, the app data doesn’t get deleted automatically. To delete it, you must go into the appdata share and delete its folder. Otherwise if you reinstall the app, it'll use the same configuration as before.

### 🕶️ Security

Now before you get all giddy and excited with installing apps, remember to be safe and use protection! The nerd way.. Anyways here are some measures to be secure:

* Having long and complicated passwords.
* Enabling 2FA whenever you can.
* Updating your apps on a timely basis to patch security exploits, **especially** the ones exposed to the internet through **port forwarding**.

### :pencil: File Editor Extensions

Unraid is able to edit a lot of file types, but it just doesnt have a full list built in for some reason. Go to **Main → Arrow next to Flash → config → editor.cfg**. Here you can add the extension of whatever files you want to edit within Unraid. Here's a small list that I've used:

```
txt
js
php
page
plg
xml
old
bak
log
css
ini
sh
json
yml
cnf
py
Dockerfile
lua
env
json
pem
```

</div>
