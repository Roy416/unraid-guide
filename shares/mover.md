<div style="color: black;">

# Mover

One of the **perks of having a cache drive** is that you can set it up so that when you download or transfer files to your server, it will use the faster SSD speeds. Then later at night, those files would be transferred to the array. This is possible by the **mover feature**.

To set this up, click on a share to open its settings, change primary storage to cache and secondary storage to array. To change the time the mover occurs, go to **Settings → Scheduler**.

### 🤫 Quiet your server 

Currently all the random server system stuff occurs on the **array**, and when this happens the **HDD makes noise**. You can put all that on a **cache drive** to avoid that noise.

For the **appdata**, **domains**, **isos**, and **system** shares:

1. Set **Primary storage** → **Cache**

2. Set **Secondary storage** → **Array**

3. Set **Mover action** → **Array → Cache**

Then go to the **Main page** and click **Move**. Once that’s done, change the **Secondary storage** → **None**.

### 🛑 Stopping the mover
If you started the mover and it’s taking too long and want to stop it, go to the terminal and type **`mover stop`**. It might take some time for the mover to fully stop as it might be finishing the transfer of the last file.

</div>
