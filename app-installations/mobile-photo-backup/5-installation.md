<div style="color: black;">

# Installation

{% hint style="info" %}
[Immich's guide for Unraid](https://immich.app/docs/install/unraid/)
{% endhint %}

This is going to be a different kind of installation. Instead of installing Immich from the Community Apps, we will be using Docker Compose, which is the official and recommended way. With the Immich template on the Community Apps, there was something with having to keep track of the version of the database before updating Immich, which sounds like a hassle to remember.

1. **Create a share** (or folder) for your photos and **create a folder** in the appdata share for Immich's database (PostgreSQL).
2. Go to **Docker**, scroll all the way down, click **Add New Stack**, and give it a name.
3. Download Immich's [Docker Compose](https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml) and [Example.env](https://github.com/immich-app/immich/releases/latest/download/example.env) (files grabbed from [Immich's Unraid instructions](https://docs.immich.app/install/unraid)).
4. Click on the **Cog** next to the Stack you created → click **Edit Stack** → click **Compose File**. Delete whatever is there and paste the contents of the **Docker Compose file** you just downloaded.
5. Click **Edit stack** again and click **ENV File**. This time and copy and paste the content from **example.env**.
6. For `UPLOAD_LOCATION`, set it to the share you created for your photos (e.g. /mnt/user/photos). For `DB_DATA_LOCATION` set it to the folder you created for Immich's database in the appdata share (e.g. /mnt/user/appdata/postgres-immich).
7. To set your **timezone**, remove the hashtag and a space next to `TZ=Etc/UTC`. Search the **link** in the comment above it to find your timezone identifier, and paste it. Click **Save Changes**.
8. For the `DB_Password`, run the command below and paste it there.
```
openssl rand -hex 16
```
9. To the right of your stack, click **Compose Up**. It will start installing Immich. **DO NOT CLICK DONE** until it says `Connection Closed`.
10. Once it says **Connection Closed**, you can go ahead and **click Done**, and you'll see a bunch of containers appear. You won't be able to click on immich_server to go to its Web UI, but next to immich_server it'll say the Web UI port, which is 2283. So you can access Immich with ServerIP:2283.
11. From here the set up guide is pretty straight forward. Last I checked, the default storage template was kind of unusable. I use this `{{#if album}}{{album}}/{{filename}}{{else}}{{y}}/{{MM}} - {{MMM}}/{{filename}}{{/if}}` , so if a photo is in an album, it'll be in that album's folder, and if it's not in an album, then it'll be in the folder of its year, within a folder of the month. You can change this anytime within the admin settings.

</div>
