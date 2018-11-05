# Lab 2 - Object Tagging and Inventory

## Introduction
This lab will take you through the process of tagging objects and setting up S3 Inventory

## Tagging Overview
Use object tagging to categorize storage. Each tag is a key-value pair.
You can add tags to new objects when you upload them or you can add them to existing objects. Note the following:

* You can associate up to 10 tags with an object. Tags associated with an object must have unique tag keys.

* A tag key can be up to 128 Unicode characters in length and tag values can be up to 256 Unicode characters in length.

* Key and values are case sensitive.

In addition to data classification, tagging offers other benefits. For example,

* Object tags enable fine-grained access control of permissions. For example, you could grant an IAM user permissions to read only objects with specific tags.

* Object tags enable fine-grained object lifecycle management in which you can specify tag-based filter, in addition to key name prefix, in a lifecycle rule.

* When using Amazon S3 analytics, you can configure filters to group objects together for analysis by object tags, by key name prefix, or by both prefix and tags.

![Add Tag](/images/2-object-tags.png)

![Key Value Pairs](/images/2-enter-object-tags.png)

## Lab Steps 

### 1. Step 1

### 2. Step 2 

### 3. Step 3

## S3 Inventory Overview
Amazon S3 inventory provides comma-separated values (CSV) or Apache optimized row columnar (ORC) output files that list your objects and their corresponding metadata on a daily or weekly basis for an S3 bucket or a shared prefix.

You can query Amazon S3 inventory using standard SQL by using Amazon Athena, Amazon Redshift Spectrum, and other tools such as Presto, Apache Hive, and Apache Spark. It's easy to use Athena to run queries on your inventory files. You can use Athena for Amazon S3 inventory queries in all Regions where Athena is available.

The following is an example CSV inventory list opened in a spreadsheet application. The heading row is shown only to help clarify the example; it is not included in the actual list.
![Inventory CSV](/images/2-inventory-list.png)

### 1. Step 1
When you configure an inventory list for a source bucket, you specify the destination bucket where you want the list to be stored, and whether you want to generate the list daily or weekly. You can also configure what object metadata to include and whether to list all object versions or only current versions.

Since the inventory is only generated on a daily basis, in this lab, we will setup inventory, then view an inventory that has already been created.

### Step XYZ - View An Existing Bucket Inventory
Since the inventory is only generated on a daily or weekly basis, we will view an existing inventory.
Go to this [Sample Bucket] (https://s3.console.aws.amazon.com/s3/buckets/s3reinvent2018demosourcebucketaccount1/inventory/s3reinvent2018demosourcebucketaccount1/s3reinvent2018demosourcebucketaccount1inventory/data/?region=us-east-1&tab=overview) 

If the URL doesn't work, navigate to s3reinvent2018demosourcebucketaccount1 and go into the Inventory / Data prefix (folder)

You will see a listing of GZip CSV inventory objects like this
![Inventory CSV](/images/2-inventory-csv.png)

You can download, unzip and view one of the CSV files if you wish.
It will look similar to this without the column headers
![Inventory CSV](/images/2-inventory-list.png)

### Navigation
[Lab 3](../lab3/README.md) | 
[Back to Overview](../README.md)
