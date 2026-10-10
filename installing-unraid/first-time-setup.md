<div style="color: black;">

# First Time Setup

1. Open a web browser and **enter the IPv4 address** you noted earlier. You can also access it by entering `<servername>.local`, however this is less reliable.
2. **Create a password** for the Root user.
3. Next, you'll get a prompt to enter your **activation code** or to start a free trial.
4. **Assign your drives** to the array. Remember, the parity drive has to be the largest capacity or equal to it.
5. For cache drives, scroll down and click **Add Pool**, give it a **name**, click **Add**, and **assign** your SSD drive. 
6. If you have multiple drives in the pool, you can change the **configuration type**. Click on the **Pool**, change the file system type to **ZFS**. Then it'll allow you to choose the Allocation profile. 

==- Raid Configurations  
| Configuration | Description | 
| --------- | --------- | 
| Stripe (RAID0)    | All drives combine to make one storage space with faster speeds.</p><p> <ul><li>If 1 drive fails, all data in the pool is lost. </li></ul>  |
| Mirror (RAID1)   | 1 drive will be used for storage while the other will mirror the data of that drive, meaning you''ll lose half of your storage space (redundancy). </p><p> </p><p></p><ul><li>If 1 drive fails, you have another drive with a exact copy of it. </li></ul>  |
| RAIDZ1 (Z for ZFS)   | Needs 1 parity drive with at least 2 storage drives. </p><p> <ul><li>If 1 drive fails, the pool uses parity information to try to recover that data. </li><li>If 2 drives fail at the same time or parity recovery is unsuccessful, all data is lost.  </li></ul>   |
| RAIDZ2 (Z for ZFS)   | Needs 2 parity drives with at least 2 storage drives. </p><p> <ul><li>If 2 drives fail at the same time, the pool will try to recover. </li><li>If 3 drives fail at the same time or parity recovery is unsuccessful, all data is lost. </li></ul>|
===

7. Click **Start** to turn on the array. It should try to build the parity, however it will probably ask you to format your drives. So click on the "**Yes I want to do this**" checkbox, and click **Format**. After it's formatted, your array should be up and running!

</div>
