<div style="color: black;">

# Common Unraid Terms

### Array

An array is where your hard drives live. You can think of it of as linking all your drives together creating one gigantic storage space. But unlike traditional RAID, you're still able to go into each hard drive and see what files are on there. Also unlike RAID, if one of your storage drive dies, only the data on that drive would be jeopardized, not all the data on the array.

You also don't *need* to have an array for Unraid to function. Which is nice for if you want to make a full SSD build.

### Parity Drives

Parity parity parity, you must have heard this term a bunch of times when watching videos about Unraid. Similar to a backup drive, a parity drive serves to prevent data loss, but THEY ARE NOT THE SAME.

What a parity drive does is it keeps track of all the data that is being written to your array, and waits for one of your storage drives to fail. If a storage drive does fail, then the parity drive swoops in and tries to save that data.

However, there is **no guarantee the the parity drive will be successful in retrieving your lost data**, whereas a backup already has a copy of it. This is because during the recovery process, is when it's the highest chance that the parity drive will die, due to the amount of stress. One way to mitigate this is to get a second parity drive.. However a lot of people just roll with one 🤷🏽‍♂️. 

The positive about the parity drive is that you just need one drive to cover the failure of the rest of your drives, whereas you would need multiple backup drives to duplicate your data. Again however, if two of your drives die at once and you only have one parity drive, then one of the drive's data goes bye bye. 

Another thing to note is that a **parity drive won’t be counted as your storage space**. The parity drive’s storage must also be either equal or larger than your storage drives. This makes sense because if you have a 4TB parity drive, but one of your 8TB storage drives fails, it wouldn’t be able to save all 8TB of data.

### Cache Pools

Cache pools are just a group of SSDs. They work more like traditional RAID. There are even some configurations with parity but it isn't quite the same as parity drives in arrays. More info on this in the following sections. You can also create multiple pools for different purposes.

</div>
