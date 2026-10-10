<div style="color: black;">

You can add external libraries to Immich. I use this to add my childhood photos and videos. The one downside is that only one person can view it. So if another person wants to view those photos and videos too, you have to create another external library for the same photos and videos.

1. Edit **Immich's stack** and click edit the **Compose file**.
```
immich-server:
    volumes:
      - ${UPLOAD_LOCATION}:/data
      - /mnt/user/photos/old_photos:/old_photos:ro
```
2. Look at the example above. My photos are in `/mnt/user/photos/old_photos`, this is the host path. Add a `:`. Followed by `/old_photos`, the path where I can find them in Immich, the container path. Then I added `:ro` to make it read only, so if I accidentally delete a photo in Immich, it won't delete the actual file. 
3. Go to **Immich** → **profile** → **Administration** → **External Libraries** → **Create Library** → Select the **user** who wants to view it → add the **container path** (e.g. /old_photos) → click **Scan** on the top right. Repeat this for whoever else wants to view the same media. 
    - To see what's happening, click on Job queues, and it should the media in the external library being processed. 

</div>
