<div style="color: black;">

### :question: What is Docker?

Docker is a platform that allows you to run apps. These apps are isolated in their own “containers” or environment, so they don’t interfere with each other. Here are some other terms you'll come across:

**Image** - Essentially the download file for the app.

**Volume** - Assigning storage space for the app.

**Docker Compose** - Docker Compose is like a pre-made configuration file, where it’ll have the settings. It also gets the image, and sets up all the volumes and stuff, so you don’t need to do a thing (other than put your system’s info). Some services don’t have a sample docker compose file but other people may have posted theirs for you to use.

### Docker Volumes & Images on Unraid

I just mentioned that docker uses volumes and images. Unraid does things a little differently.

Unraid foregoes assigning volumes to containers. Instead, the data of the apps simply go into `/mnt/user/appdata` a.k.a the appdata share. 

Unraid still downloads the image of the app, however it combines all the images you download into a file called **docker.img**. This is important to know because if you download so many images that it exceeds the default size of the docker.img, then docker and all your apps will stop working (will show how to expand this later).

### 🥸 Unraid is Linux..?

Under the hood, Unraid is indeed running a custom version of Linux. So when you're poking around your files or messing around with containers, you might see /var, /opt, and /mnt, which are Linux's filesystem directories. This also means that each docker container is running in its own Linux environment.

### 🎭 Multiple Entries for the Same App?

When you look for an app on Community Apps, you might see multiple entries. All those entries are different "docker templates". A docker template in the context of Unraid, is basically everything a docker compose file has but it's tailored for Unraid. And different maintainers create their own templates. The version of the app may even differ depending on which repository is used to get the image. 

Some recommended templates are by hotio and binhex, otherwise I get whichever one was updated most recently.

### 🆚 Community Apps vs Docker Compose

Since Unraid is Linux, that means a typical Docker Compose configuration can also be used. Some people even prefer using Docker Compose to install services directly from the source repository (seen as Compose on the Docker tab). It does require you to understand the configuration file and how to put your own settings in, but it is generally straight forward after a little learning. This is where assigning volumes also comes back into play. With that being said, I personally still install from the Community Apps since it's more convenient 🤷🏽‍♀️. If I can't find it there, then installing via Docker Compose it is. 

</div>
