<div style="color: black;">

# Installation

1. **Install Plex** using the template by `hotio`. We will use this template because it uses the Bridge network instead of Host, making it more secure. It does require a few extra settings to be filled out.  
2. For **/data**, select the share with all your media (make sure there is a / at the end). If you're following TRaSH guidelines, select the media folder.
   -  If you want to add another media path that's in a different share, scroll down and click "Add another Path, Port, Variable, Label or Device". Give it a container name (e.g. /data2/ - this is how it will show in Plex) and set the host path to the actual path of the share.
3. Go to [plex.tv/claim](plex.tv/claim) and create an account. Copy the claim token, go back to the installation page, and paste the token into the respective field. 
4. If you have **Quick Sync**, click on Advanced View, and in Extra Paramters paste `--device=/dev/dri:/dev/dri`. Make sure there is a space between the previous parameter. 
5. In **Advertise URL** enter `http://your-server-ip:32400` (e.g.http://192.168.0.23:32400). You even have to do this if you want to watch locally even if nothing is port forwarded, don't ask me why. 
4. Give it a moment, click "**Got it**", and **name your server**. Click **Next**.
5. Click **Add Library**. Choose the **type of media** you want to add and customize its name if you want.
6. Click **Add folders**, then **Browse for Media**, and click on the **data folder** on the left. Then on the right, select the folder your type of media is in. You could also look through the **Advanced Settings** and see if there's anything you want to enable/disable. I personally like to hide items which are in collections.  
7. Repeat this for all different types of media.
   -  Note, you can add multiple libraries of the same type of media (e.g. adding a separate shows library for anime).

#### ⏩ Portforwarding

Port forwarding for Plex is very simple. Simply use `32400` for both the internal and external ports, and enter the IP of your Unraid server. You don't need to do anything with the reverse proxy. 

</div>
