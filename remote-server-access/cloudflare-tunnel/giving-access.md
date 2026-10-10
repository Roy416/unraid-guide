<div style="color: black;">

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vQTblk6p6kl6NWGSZ5tsDbm6OC7JIkaJtRErvez691kSztPJkz9i1ZkxzP66w0eNL7XNiJqGCf9DAxL/pubembed?start=false&loop=false&delayms=3000"
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

### 🚇 Exposing an app through the tunnel

0. Here's how to get back to the page to add another app or if you exited the setup process in the previous section: 
    - On the sidebar under Protect & connect → Zero Trust → Networks → Tunnels and Mesh → three dots besides your tunnel → Configure → published application routes → Add published application route. 
1. **Create a name** for the sub domain for your app. **Select your Domain**.
2. For **Type**, your two options are **HTTP** and **HTTPS**. **Majority of the apps use HTTP** but some do use HTTPS (e.g. Nextcloud). If you have any doubts of which one you should select, a quick google should clear that up.  
    - For HTTPS, expand "Origin request and connection settings" at the bottom, expand TLS, and enable No TLS Verify. 
3. Under **URL**, enter your **Server IP and the Web UI port of the container** with a colon seperating them (e.g. 192.168.0.26:5055).
4. Now try entering your URL (e.g. seer.domain.com) and hopefully you see something that isn't an error screen!

### ⏪ Want to use a reverse proxy? (Optional)
{% hint style="info" %}
[Accompanying video by Thomas Wilde](https://www.youtube.com/watch?v=TB2bnASgJV4&t=)
{% endhint %}

It is also possible to use a reverse proxy in conjunction with a Cloudflare Tunnel. One reason to do this is so you can use a SSO, such as Authelia. However there is a method where you can use Authelia without a reverse proxy as well. Another reason is so you can see the IP of the people who are connecting to your sites, allowing you to use something like CrowdSec to protect your server even more. 

1. Set up a reverse proxy following [this section](../port-forwarding/reverse-proxy.md) from the Port Forwarding method. 
2. Follow the same steps above to add a container, however instead of using the Web UI port of the container, you use the Web UI port of the reverse Proxy. So in this case, it would be `1880`.
3. Add the container the same way in [Giving Access](../port-forwarding/giving-access.md), disregarding the SSL stuff, and bob's your uncle. 
4. Then if you want to see the IP of the person that's on your site, go into the advanced tab and add `real_ip_header CF-Connecting-IP;`. 

</div>
