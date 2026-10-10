<div style="color: black;">

1.	Create a free B2 Cloud Storage account on Backblaze. 
2.	Go to Buckets -> Create a Bucket. The name must be unique. Make note of the endpoint.
3.	Go to Application Keys -> Add a New Application Key. Copy the keyID, applicationKey, and the endpoint in a temporary notepad. 
4. Install Backrest by AlexRed. For **Path to backup** select the folder you want to back up. Click Apply.  
    - If there files in other share you want to back up, scroll down, click Add another Path, Variable, Local Device, -> Give it a name, give it a container path (e.g. /documents), and set the host path (e.g. /mnt/user/documents).  
5.	Open Backrest's Web UI. Name the Instance ID and create a user and password. 
6.	Click Add Repo and give it a name that represents the server.
7.	Under Repository URI, grab the endpoint link from step 3, and type this `s3:endpoint link/nameofyourbucket` (e.g. s3:s3.us-west-004.backblazeb2.com/chumbucket)
8.	Type or Generate a password. You will **need this password to decrypt** your data later. 
9.	Under Env Vars, click Add twice. Name the first one `AWS_ACCESS_KEY_ID=` and enter the keyID. Name the second one `AWS_SECRET_ACCESS_KEY=` and enter the application key. 
10.	Click Test Configuration and hopefully it says connected. Click Submit.

### create backup schedule 
1.	Click Add Plan. Give it a name and select the repository that you just created. 
2. Under scope add `/backup` (or whatever you changed it to), and any other container paths you added.
5.	Next you can set up how often you want a backup to occur. You can leave the settings at Cron and Local. 
6.	The retention policy decides how long it’ll keep a snapshot before it’s deleted. By default it keeps a snapshot for the past 30 days, and one monthly snapshot for the past 12 months. It’ll basically only be clearing up space (pruning) from the files you already deleted and old versions of files. If you want it to keep everything including deleted files and old versions of files, you can choose None.   
7.	Click Submit, click on the backup plan, and click Back Up Now. 

</div>
