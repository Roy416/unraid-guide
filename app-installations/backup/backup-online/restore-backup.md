### restoring backup setup

so you could go onto the webui and download the old files from there if you need. but lets setup if you cant access yourserver, how to retrieve your files

1.	On your PC or laptop, download Backrest (click Show all Assets at the bottom to see the Windows download). Extract this folder somewhere safe where you won’t accidentally delete it.  
2.	Click on backrest-windows-tray.exe. Then go to your systems tray, find backrest, and click Web UI.
•	If you get an error, in the windows search bar, search advanced system settings -> Environment Variables -> Double click on PATH -> Add an entry of C:\\Windows\System32
3.	Create a user and add the repo the same way was before. 

### how to restore backup (lots of clicking)
1.	Click on your Repo -> Index Snapshots, this will update the snapshot list. Then under your server, expand backup (or whatever you named your plan), expand the date, then you’ll see the snapshot. 
2.	On the right side, expand Snapshot Browser, and expand the remaining folders. You can download the entire folder or specifc files by clicking Restore to Path.
3.	By default, the restore path will create a folder in your OS drive (C:). If you want it on your desktop you can do /users/youruser/Desktop/backupname
