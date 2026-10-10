<div style="color: black;">

**Reverse proxy** looks like an intimidating term, but what this basically does is links your URLs (e.g., nextcloud.domain.com) to your apps so that you can access them outside of your home. You’ll be making these URLs in the next part.

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vR6oCcjMI0yfObDaB4Ioh_XDbY0bVrbk0e_XHGE5iQ0VthDDhrGC2CynETImXy9zDzr2dIAAx3rk6HO/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

### Installation

1. Search `nginx proxy manager official` by mgutt from the community aps and install. It might say that it requires a custom network. You will learn more about [Custom Docker Networks](../../apps&plugins/custom-docker-network.md) later. But for now let the network type be br0. 
2. Change the HTTP port from **80 to 1880** and the HTTPS port from **443 to 18443**. This is because Unraid's Web UI already uses those ports.
3. Open the Web UI of NPM and enter the default credentials that was written in the overview, user: `admin@example.com` and password: `changeme`. 
4. Go to your **router's port forwarding settings** and enter these **two entries**. Make sure you're entering the correct ports for external/internal as some interfaces have the order switched. **Remember to save**:

| Name      |Protocol   |External Port/Start  | Internal Port/End | IP Address   |
| --------- | --------- | ---------            | ---------          | ---------    | 
| HTTP      |TCP        |80                    | 1880               | Server IP    |
| HTTPS     |TCP        |443                   | 18443              | Server IP    |

5. Remember those certificates we made in the previous section? Let's add them in. Go back to NPM, and on the top bar click **Certificates** → **Add Certificate** → **Custom Certificate**. 
6. Give your certificate a name, for the **Certificate Key select the .key file**, and then select the **.pem file for the other Certificate**, and click Save.
7. Click on your **profile** on the top right and **change your email and password** (click Edit Profile to change your email). 

#### 🔢 Alternatives

You may have heard of SWAG and Traefik, these are also other reverse proxies. They seem to have more features but are also harder to setup. Pangolin is the new hot thing on the block, however it essentially requires you to buy a VPS, and those aren't dirt cheap as they once were. 

</div>
