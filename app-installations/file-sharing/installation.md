<div style="color: black;">

# Installation

{% hint style="info" %}
[Accompanying video by Spaceinavder](https://www.youtube.com/watch?v=U47nvwXrAOo\&t)
{% endhint %}

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vSC6_R-vg_qeZGb_MpOr1kIViWWLIa_RPtQfSIoFAyQsLAYmHr4v7-I75mMm0v9wqPg7HAyc-Aie4ag/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

1. **Create a share** named `nextcloud`. This is where your files will reside. Nextcloud's appdata will also be in this share, so perhaps setting the primrary storage to a cache drive and secondary storage to none, may be the move (assuming you aren't going to be syncing large files). 
2. Go to **Settings** → **Docker**, click on the toggle on the top right to show the **Advanced View**,  set **Enable Docker** to `No` and click **Apply**. Then set **Preserve user defined networks** to `Yes`, and set **Enable Docker** to `Yes` again and click **Apply**.
3. Click on Apps and install the **official container of Nextcloud AIO**. 
4. Go to its **Web UI**, and you'll be greeted with a Warning screen. Click **Advanced** and click **Accept the Risk and Continue**.
5. You'll be shown a pass phrase, which is the recovery key. **Take note of the pass phrase** in a password manager of sorts, as this is the only time you'll see it. Click **Open Nextcloud AIO login and paste the pass phrase.**
6. If you bought a domain, follow the instructions of giving access of the method you chose. Set the scheme to http, the port to 11000, and the IP to your server's IP (you can replace it with `nextcloud-aio-apache` after the setup if using custom docker networks). If you want to access remotely with Tailscale, go to [Using Tailscale Instead](using-tailscale-instead.md).
7. Enter your **domain** and click **Submit Domain**.  
8. **Choose the optional containers** that interest you, and click **Save changes**. These can be enabled/disabled later under the App settings. Scroll down and **change your timezone** and **click submit timezone**, **select the latest version** if shown, and **click Download and start containers**. This will take a minute.
9. You'll get a screen with the status of the containers, **after a moment click** **Reload** and they should all be running or wait until they're all green.
10. When they're all running, your **initial username and password** will show. Click **Open your Nextcloud**, and **use that info to login**.

#### ⏲️ Session Timed Out?

If you're reinstalling Nextcloud you might get a session timed out error. Clear the cookies and cache for your Nextcloud domain, and you'll be good to go. 

</div>
