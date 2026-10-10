<div style="color: black;">

# Nextcloud

Nextcloud is a Google Drive replacement where you can share files, sync documents, and a lot more. You can also install apps within Nextcloud that offer more functionalities. There are two versions of it, the bare bones version and the AlO (All In One) version. I've used the bare bones version in the past and it did give me issues over time. So we will be installing the AIO version.

As the name suggests, the All In One version includes everything you need, the install is much easier, and requires no maintenance other than updating. However it does require a domain. There is a roundabout way to make it work with use a Tailscale domain, which I'll also show.

Nextcloud gets a bad rap for being bloated and being fussy. So, many people set out for an alternative, but in the end return back to Nextcloud. 

### Alternatives

|           |           |
| --------- | --------- | 
| Seafile    | Probably the closest to Nextcloud in terms of basic functionality. Super efficient file syncing, so good for a lot of files. More finicky to install. </p><p>Your files are stored as little chunks in its database, which is more secure but you aren't able to see your files straight up on your server. Although, you can could a script and use rsync to copy your files into a share as a workaround.  |
| Syncthing    | Syncs your files across multiple devices but doesn't store your files on the server.   | 

</div>
