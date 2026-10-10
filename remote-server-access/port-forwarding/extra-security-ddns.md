<div style="color: black;">

### DDNS

You know the public IP address we used in the last section?  Well, it has a habit of changing. It could change in a day, in a week, or in a month, making you unable to connect to your apps remotely.

That is where Dynamic DDNS comes in. If the public IP address happens to change, the Dynamic DDNS will automatically update it, so you can continue to use your services like nothing ever happened.

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vS8iaok7r73wFUqc5YjAdWIKxSgor3ZQCTcuUB8dgpkatcRbzCcbmySZhFfmtwXLi_SPTUcHw94DAAt/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

1. First, let's create a Cloudflare API token. On the top right click on the **user icon** → **Profile** → **API Tokens** → **Create Token**.
2. Select **Create Custom Token**. Give it a name. Then under Permissions, Change **Account → Zone** and in the following fields select **DNS**, and **Edit**. Then under Zone Resources, change **All Zones → Specific zone**, then in the next field select your **domain**. click Continue to summary, and click Create Token. **Copy the token** and save it somewhere temporarily. 
3. On the community apps, search for `cloudflareddns` by hotio.
4. Enter the **API token** and your **domain**, and click Apply. Now if you view the logs of cloudflareddns, it should state your domain, your public IP address, with hopefully no errors. 

### Enabling DNSSEC

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vSf-3USgVCen5KYc_NrfNBwiH1UamU987xj_UIk21okwkexdOpPMGzAkN9090KHePSRGIYt202kWb_w/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

1. On Cloudflare, Click **DNS** → **Settings** → **Enable DNSSEC**. And it should give you a bunch of keys and numbers.
2. Go to your **Domain Registrar's settings**, and under the **DNS settings**, find the **DNSSEC section**.
3. Click to add a new DS, and enter whatever information it asks from the list of keys and numbers cloudflare gave you before. and click Save.

### Creating your own certificate

<iframe 
  src="https://docs.google.com/presentation/d/e/2PACX-1vRliJLAYqtyOjfNVSL8JedoRMkopxN4oGvhp8SrsKk7IY2CbLAvwYHwsq_LWYoNaBrtnl2hbFwFdGDf/pubembed?start=false&loop=false&delayms=3000" 
  width="814" 
  height="494" 
  allowfullscreen>
</iframe>

<span style="color:white;">●</span>

1. On the left side bar, click **SSL/TLS** → **Configure** → select **Full (strict)** → **Save**.
2. Then under SSL/TLS on the left, click **Origin Server** → **Create Certificate**.
3. Open up a notepad, **copy the PEM text and save it as a `.pem` file**. Similary for the **private key**, open another notepad, copy it, **save it as a `.key` file**. We will use these in the next section.

</div>
