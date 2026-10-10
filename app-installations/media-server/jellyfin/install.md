<div style="color: black;">

1. **Install Jellyfin** using the template by `hotio`.
2. For **/data**, select the share with all your media (make sure there is a / at the end). If you're following TRaSH guidelines, select the media folder.
   -  If you want to add a media path that's in a different share, scroll down and click "Add another Path, Port, Variable, Label or Device". Give it a container name (e.g. /data2/ - this is how it will show in Jellyfin) and set the host path to the actual path of the share.
3. If you have **Quick Sync**, click on **Advanced View**, and in **Extra Paramters** paste `--device=/dev/dri:/dev/dri`. Make sure there is a space between the previous parameter. 
4. Click **Apply**.  Give your server a name and create your account. 
5. Click **Add Media Library**. Select the content type and give the library a name. When browsing for your media, it'll be under /data. Repeat this for your other type of media. 
   - Note, you can add multiple libraries of the same type of media (e.g. adding a separate shows library for anime).
6. Continue through the wizard and Jellyfin will automatically begin to scan. The initial scan process is really slow, so don't be alarmed. 

#### Transcode Setup

1. Click on your profile -> Dashboard -> Playback -> Transcoding
2. For **hardware accerlation**, choose **Intel QuickSync**.
3. In **QSV Device** enter `/dev/dri/`.
4. Scroll down and enable VPP Tone mapping (if your CPU is 11th gen or higher). Otherwise select Enable Tone mapping. 
5.You can take a look at the rest of the settings and see if you find anything interesting. Just remember what settings you enable because it might break something.

#### 🫴 Remote Access

There's no special instructions to access Jellyfin remotely with either port forwarding or Tailscale. However it can be a little difficult to install Tailscale on TVs (or devices for TVs). 

</div>
