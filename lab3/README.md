# Lab 3 - Storage Classes and Lifecycle Management

## Introduction
This lab will take you through the process of viewing and setting storage classes on an object and setting up lifecycle policies

## Storage Classes
Each object in Amazon S3 has a storage class associated with it. For example, if you list all objects in the bucket, the console shows the storage class for all the objects in the list.
![Storage Classes](/images/3-ObjectStorageClass.png)

Amazon S3 offers the following storage classes:
![Storage Classes](/images/3-storageclasses.png)

* STANDARD—The default storage class. If you don't specify the storage class when you upload an object, Amazon S3 assigns the STANDARD storage class.

* The STANDARD_IA and ONEZONE_IA storage classes are designed for long-lived and infrequently accessed data. (IA stands for infrequent access.) STANDARD_IA and ONEZONE_IA objects are available for millisecond access (similar to the STANDARD storage class). Amazon S3 charges a retrieval fee for these objects, so they are most suitable for infrequently accessed data. 

** STANDARD_IA—Amazon S3 stores the object data redundantly across multiple geographically separated Availability Zones (similar to STANDARD storage class). STANDARD_IA objects are resilient to the loss of an Availability Zone. This storage class offers greater availability, durability, and resiliency than the ONEZONE_IA class.

** ONEZONE_IA—Amazon S3 stores the object data in only one Availability Zone, which makes it less expensive than STANDARD_IA. However, the data is not resilient to the physical loss of the Availability Zone resulting from disasters, such as earth quakes and floods. The ONEZONE_IA storage class is as durable as STANDARD_IA, but it is less available and less resilient. 

* The GLACIER storage class is suitable for archiving data where data access is infrequent. Archived objects are not available for real-time access. You must first restore the objects before you can access them.

 You cannot specify GLACIER as the storage class at the time that you create an object. You create GLACIER objects by first uploading objects using STANDARD, RRS, STANDARD_IA, or ONEZONE_IA as the storage class. Then you transition these objects to the GLACIER storage class using lifecycle management. For more information, see Object Lifecycle Management.

 You must first restore the GLACIER objects before you can access them (STANDARD, RRS, STANDARD_IA, and ONEZONE_IA objects are available for anytime access). For more information, Transitioning to the GLACIER Storage Class (Object Archival).


## Architecture overview

### 1. Step 1

### 2. Step 2 

### 3. Step 3

### Navigation
[Lab 2](../lab2/README.md) | 
[Back to Overview](../README.md)