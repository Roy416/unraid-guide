You're probably thinking you should look into backing up yor stuff pressured by others yelling 3-2-1 strategy or from fear that your house might burn down and you'll lose all your stuff. 
There are a bunch of different ways to back up your data. Today I'll be showing you how to back up your data to BackBlaze with Backrest. 

### What is Backblaze
Backblaze is a S3 compatible storage. It's a lot cheaper than the typical cloud services you know, I pay $3.50 for 500gb. Most cloud services have a minimum price of $10 per month (for a minimum plan of 2 TB).

"Why is S3 compatible storage so cheap?", you may ask. It has no fancy features and uses a pay-as-you-go model. No fancy features such as sharing files, trash bin, etc. For Backblaze, downloading all your files is essentially free. You will only have to start paying if you download 3x your storage size in a month. This works out great as we’re only using it to restore in case of emergencies.

### What is Backrest
After testing a few alternatives, I decided to use the backup software called Backrest. It’s based off of Restic which is a solid solution. Backrest encrypts your data. Which means we will also need to set up backrest on your computer, so you can decrypt and view your data. If you don't want to encrypt it, you can look at a solution such as rclone. 

These backups work differently than you might expect, it has some really smart features. Which include snapshots, deduplication and incremental backups. The rundown is:

<details>

<summary><span data-gb-custom-inline data-tag="emoji" data-code="1f511">📝</span> Rundown</summary>

- You upload your data and a snapshot (**backup**) is created.
- If the data remains unchanged, then it doesn’t get uploaded twice (**deduplication**).
- If you edit a file, it’ll only change parts of that file and creates a new version (**incremental backups**) while keeping the old.  
- So if you create a new snapshot, it will have the newly edited file while the older snapshot will have the original file. 
- Extra info: A snapshot isn’t exactly a typical backup. All your files, old versions and new, are in one folder. When you restore a snapshot, it picks the files and their versions from that folder from when the snapshot was taken. 

</details>
