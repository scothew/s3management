# Lab 4 - Versioning and Cross Region Replication

## Introduction
This lab will take you through the process of enabling object versioning and configuring CRR (Cross Region Replication).

## Versioning Overview
Versioning is a data protection mechanism for S3 buckets/objects. Versioning is enabled at the bucket level and is recommended by AWS as a best practice.  It can be enabled via the console or programatically. This session focuses on the console.

 ![Version View](../images/4-versioning-1.png)

**Benefits of CRR**

* Protects against unintended deletes (think Recycle Bin)
* No performance penalty
* Easy retrieval of deleted objects
* Lifecycle policies assist "versioning" with variant control, clean up, and storage class mobility

## Versioning Lab

1. Go to the S3 console, select your S3 bucket **(stg209-student-x)**, click on **Properties** tab
2. Click on **Versioning**, select **Enable versioning**, click **Save**

 ![Enable Versioning](../images/4-versioning-2.png)


3. Go to your S3 bucket **(stg209-student-x)** and navigate to prefix (folder) **"lab4/version1"**. Click on **Versions: Show** to observe the current state of the files in this folder.

 ![View Versions](../images/4-versioning-3.png)

As you can see, there is only one version of each file. Feel free to open any txt file.  It will read "This is version 1". 

4. Navigate to the folder **"lab4/version2"**. Turn off versions view by selecting **Versions: Hide**.  Select the checkmark at the top left corner to **select all** the files.  Click **Actions** and choose **Copy**

 ![Copy Version1](../images/4-versioning-4.png)
 
 
5. Navigate back to folder **"lab4/version1"** and choose **Actions**, then **Paste** to write the contents to the folder. Click **Paste**.


6. Click on **Versions: Show**. You now have multiple versions of the same file.  Each version has a unique Version ID.

 ![Display Versions](../images/4-versioning-5.png)
 
 
7. Open both versions of the same file. The "Latest" will read **"This is version 2"**. The older file will read **"This is version 1"**.  If you delete the "Latest" version of a file, it will promote the older version to "Latest".  


## Cross Region Replication (CRR) Overview
CRR is a bucket level feature that allows for asynchronous replication of objects in different regions.  Source and destination can be same or different accounts. Only new Objects or Puts will be replicated. Deletes and Lifecycle Policies will not be replicated.  All data in transit is encrypted (SSL/TLS).

* **Use cases:** Compliance, Latency, Operational, Security.
* **Requirements:** Versioning (source/dest), Different Regions (source/dest), Permissions (replication)
* **Updates:** Overwrite ownership (two diff owners), Different storage class, Bi-directional, Independent Lifecycle Policies


## Cross Region Replication Lab

1. A target bucket has already been created for you.  It will have "CRR" in the name e.g.**stg209-crr-student-x**. Versioning is required in both the source and destination buckets. 

2. **Enable "Versioning" on your destination (CRR) bucket.** Follow the same instructions as above.
 ![Identify Source Dest](../images/4-crr-6.png)

3. Go to the source bucket (without CRR in the name).  Navigate to the **Management** tab, choose **Replication** and click on **"+ Add Rule"**

 ![Start Replication](../images/4-crr-7.png)

4. Select **Entire bucket**. _Do not enable encryption_.  Click **Next**

 ![Set Source](../images/4-crr-8.png)
 

5. Set Destination bucket.  **Buckets in this account**.  Find and choose your assigned CRR bucket **(stg209-crr-student-x)**. Leave Options blank. Click **Next**


6. On step 3-Configure options, For IAM role Select **Create new role**. Name the rule **"s3-crr-student#"**. Click **Next**

 ![Replication Rule](../images/4-crr-9.png)


7. Review Source, Destination, Options and Click **Save**

 ![Replication Review](../images/4-crr-10.png)


8. Remember...CRR only replicates "new" PUTs and Objects. Test the replication by copying and pasting files into the source bucket.  The objects will automatically be copied to your destination bucket.

9. If you do not see the files in the destination folder, wait a few seconds, then use your browsers reload button and check again.

## Lab Complete

Congratulations! You have completed the Lab 4.

This ends the lab portion of this session.

**Please remember to fill out your survey!**

## Navigation
[Back to Overview](../README.md)

