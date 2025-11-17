---
label: Installation
order: 1000
---
# Installation

{% embed url="<https://docs.google.com/presentation/d/1c81oPsVoC_dWP6Ff8dnftuFeqgOXkBQNeUGnhRlqA-Q/edit?usp=sharing>" fullWidth="false" %}

1. On the community apps, install **Tailscale (Plugin)** by **Derek Kaser** or it might just say "Official" (It might be installed by default).
2. Go to **Settings** → **Network Services** → **Tailscale**.
3. It'll ask you to **reauthenticate** and **sign up** to Tailscale. It'll then ask you to **connect** the server to this account and redirect you to the admin console.
4. In the admin console, you'll see your server and the **Tailscale IP** associated with it. By clicking on the 3 dots, you can change it's name. You should also **disable the key expiry** for the devices that will permanently be on your Tailscale network. 
5. Click **DNS.** Under **Tailnet name**, you can optionally change the randomly generated wordy address you got, to something more fun and memorable. Scroll down to **Magic DNS** and **HTTPS Certificates**, these should both be enabled.
   * With HTTPS on, IF somebody got a hold of your Tailnet name, they could search it up somewhere and see the names of the devices on your Tailscale network. Not a big deal but just  a little disclaimer.
6. At the top, you can click **download** to get the **Tailscale client** for your device. Once installed and signed in, try putting your server's Tailsacle IP, and it should take you to your Unraid login page!
   * If you already have a VPN such as Proton, Nord, etc, it may not work. In your VPN settings, try split tunneling (whitelisting) all the ranges of Tailscale IPs, which is `100.64.0.0/10`.
7. You can also access any of your services with this, by typing the server's Tailescale IP and then the Web UI port at the end (e.g. 100.96.53.101:2283).
