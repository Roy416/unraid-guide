<div style="color: black;">

# Share Permissions

{% hint style="info" %}
[Accompanying video by TechnGo](https://www.youtube.com/watch?v=PePFc-eQCsY)
{% endhint %}

### Creating Users

Currently you have a root user, however you wouldn't want to give that to just anyone or have that on your laptop for example. So you can create users with certain restrictions.

1. Go to the **Users** tab.
2. Click **Add User**.
3. Fill in your **name** and **password** and click **Add**.

Click on the share you created and you will see a new section called **SMB Security Settings**. The two settings we're concerned with are **Export** and **Security**.

The export settings dictate how the share appears under the Network section in file explorer on your computer.

| Export Options | Descriptions | 
| --------- | --------- |
| **No**    | Cannot access the share.    |
| **Yes**    | Can access the share.   | 
| **Yes (hidden)**   | Can't visually see the share, but can still access it.   | 
| Time Machine   | This refers to the back up feature on Mac OS and if it can see the share.    | 

Security controls who can read and write to the share.

| Security Options | Descriptions | 
| --------- | --------- | 
| **Public**   | Anyone on the network can read and write.   | 
| **Secure**  | Anyone can read, chosen users can write.   | 
| **Private** | Chosen users can read and write.  | 

</div>
