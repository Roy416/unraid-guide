make a trouble shoot section and add docker image size and 

### IPv6 El Diablo

Story time. I got new internet and nothing was working. My containers with VPNs, custom docker networks disappeared, and security cameras (outside of Unraid) stopped working. As soon as I disabled IPv6 on my modem/router and restarted everything, it all clicked into place.  

^ remove from custom docker network section if you do

- unraid os can now be on SSD - mention USB die a lot. can use the ssd with boot + data as of 2026 (?). unraid will recognize the data parition as a different mount. 

- 
ADD SECTION ABOUT NGINX PROXY MANAGER AND WHAT APPS ARE GONNA HAVE IT ON THIS GUIDE? NEXTCLOUD-AIO AND IMMICH? LIKE THAT WE HAVE TO CHANGE BR0

## Other Concerns

### HDD NOISE EVERY FEW SECONDS

### Array to Cache

- If the HDD is making noises every few seconds and you’re not using any of its services, this is what fixed it for me. You’re going to need a cache drive.
- Some or all files on the **appdata, system,** or, **domains** shares might be on your HDD. So when the apps on the docker are doing their thing, they’re constantly accessing the HDD and making noise. So what we need to do is move that stuff to the cache drive, so when the apps need to access it, it would use the cache drive and be silent.
- First go to Settings -> Docker, and put “Enabled Docker” to no. Then for each of the shares I mentioned earlier, **set the Primary storage to cache, Secondary storage to array, and Mover action: array --> cache**. Then go on the main tab, scroll down, and click “Move”. Enable the Docker and voila, no sound.
- I also changed the secondary storage of those shares to none like before. Not sure if it does anything or matters.
- You might also notice that your cache drive is now getting more writes and is filling up a little faster. But don’t worry, all that extra stuff will be moved to the HDD later when the Mover is scheduled.

### No Health Parameter

- Sometimes the random noises could be Plex. Go to edit Plex’s container, on the top right press the basic view toggle to make it advanced, then in ‘extra parameters’ type  ‘--no-healthcheck’ without quotes..

### MY DRIVE HAS SO MANY WRITES

- I was a noob like you once (5 mins ago), where I thought the amount of writes meant a lot of data was getting written. The amount of writes just represents the amount of operations.
- To find out if this is problematic, go into the Dashboard tab, the drive, click the cog, click Self-Test, download smart report. In “Data Units Written” it shows the amount of total data (in TB) that has been written on the drive. Come back 24 hours later and download the smart report again and compare the two.
- This is only a concern regarding SSDs, as they have an endurance limit; represented as TBW (Terabytes Written). This isn’t a concern for HDDs as they don’t have an endurance rating, they can only fail if something mechanically messes up.
- For me, the cache drive writes 30gb in a day. Which sounds like a lot, but it isn’t a concern in regards to the drive’s TBW.

### bitwarden

when putting it on your phone and oding tailscale method, the tailscale number ip wont work. it has to be the 

SMART data what entries matter and the temperature before failure with that on backblaze data? 

disable ssh 
enable mirror syslog to flash
under plex under portforwarding add a snippet about using tailscale? about how some people say its usable and you can avoid the remote access but im not able to test it. 
maybe mention how the slides are meant to be supplementary to the notes and not something you can follow fully on its own. 

maybe add a section in the troubleshoot thats "got new internet nothing works?" then put the ipv6 warning and the way of booting up your switch, modem, router. 
