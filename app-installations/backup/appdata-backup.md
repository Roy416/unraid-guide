<div style="color: black;">

{% hint style="info" %}
[Accompanying video by AlienTech42](https://www.youtube.com/watch?v=ms4AnHgj9hc&t)
{% endhint %}

There you are, installing a bunch of cool containers, tweaking stuff, having a blast. Then you try something new and it messes up, and can't get it back to normal. That is where Appdata Backup comes saves the day. Backing up your appdata and allowing you to restore it when somethings goes wrong.   

### Setting up Appdata Backup

1. Create a share for the backups
2. install appdata back up by Robin Kluth
3. Go to Settings -> Backup/Restore Appdata (under User Utilities)
4. For **Delete backups if older than x days** and **Keep at least this many backups**, it depends on how many changes and container installs you're doing. You can leave this at default if you're not sure. 
    - Keep in mind, these backups can get fairly big with media server metadata and game servers.
5. For **Backup destination** select the share you made in step 1. Optionally enable multicore compression. 
6. Assuming you want to run this on a schedule, change **Scheduled Backup Frequency**. Again, the frequency depends on how many changes you're doing. In the beginning you're still messing around a lot, so you can have this to even daily if you wanted or something custom. The hour field uses a 24 hour format (e.g. 23 = 11 PM).  
7. Optionally you can have containers automatically update after a backup. I personally like to update my containers manually, as new updates can come with unexpected breakge of things. 
8. In container settings you can skip backing up a container and its appdata. You can also click on the container name to see more settings. Allowing you to even skip certain folder. If you have a mutli mapping error, you would fix it here. On the right, you can also change the Start order if you want. 
9. Scroll down, and you can click on manual backup to make one right away. 

### Restoring Appdata backup
1. Go to Settings -> Backup/Restore Appdata (under User Utilities). On the top, click the Restore tab. 
2. The backup source should already be filled in to the share you created. Click Next.
3. Select the specific backup you want to restore. Click Next.
4. Select the templates and the coressponding containers, and click Do It. 

</div>
