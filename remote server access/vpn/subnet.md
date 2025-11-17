---
label: Subnet (Optional)
order: 999
---
# Subnet (Optional)

If you log into Unraid with your Tailscale IP and click on the Web UI of a container, you'll notice that IP address reverts back to the local one. It's working now because you're at home, but once you're outside, it won't. Now you could take your Tailscale IP, and slap the port of the container you want at the end of it, then bookmark it, and call it day. Another way is by creating a subnet.

By creating a **subnet**, all the devices on your Tailscale network would be connected to your local network. So basically you can be away from your home, but your device will act like its connected to your home wifi. So you can start your laundry machine remotely or a better example is viewing your home security cameras without opening any ports.

Creating a Subnet:

{% embed url="<https://docs.google.com/presentation/d/1sa_ROgrLSaqS0letGc1pkwEXjhbxC2pSqTnBfWS0brE/edit?usp=sharing>" %}

1. Go to **Settings** → **Tailscale**. Click on "**Viewing**" and **Sign in**. You might have to try it again twice or thrice.
2. A new but similar page will pop up, click **Subnet**.
3. To find what route to enter, take your Unraid IP Address, remove the number after the last decimal, and append "0/24". For example, if your Unraid IP Address is 192.168.2.202, your subnet would be 192.168.2.0/24. After entering that in, click **Advertise new routes.**
4. Click the blue text that says "**the machine’s route settings**". Alternatively, go to Tailscale's Site → Admin Console → Click on your Server's Machine.
5. Under Subnets, it'll say awaiting approval, click Edit, select the route, and click Save.
