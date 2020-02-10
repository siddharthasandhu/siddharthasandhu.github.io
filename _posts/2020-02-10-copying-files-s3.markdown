---
layout: post
title:  "Copying Files to S3"
date:   2020-02-10 12:03:36 +0530
categories: AWS S3
---

After you have setup the your `awscli` with aws credentials, use the following command to create a bucket in S3 thorugh your terminal:

## Create an S3 Bucket
```shell
aws s3 mb s3://siddhartha.sandhu
```
Feel free to replace `siddhartha.sandhu` with a bucket name of your choice.

Then navigate to the directory where you have the file you want to copy to S3:

```shell
aws s3 cp <FILE_NAME> s3://siddhartha.sandhu
```

## To copy the file from s3 to a folder:
1. Go to the folder where you want to copy the file
1. List all buckets in S3:
```
aws s3 ls
```
1. Check all the files in S3 in a bucket:
```shell
aws s3 ls s3://siddhartha.sandhu/
```
1. Copy file available in a bucket to your local:
```shell
aws s3 cp s3://siddhartha.sandhu/<FILE_NAME> ./
```

Alternatively, to accomplish above in 1 step when you now the name of the file and the name of the bucket:

```shell
aws s3 cp s3://siddhartha.sandhu/<FILE_NAME> /User/siddharthasandhu/<LOCAL_FOLDER>
```

The above command is for Mac user space. For linux:

```shell
aws s3 cp s3://siddhartha.sandhu/<FILE_NAME> /home/siddharthasandhu/<LOCAL_FOLDER>
```

## Copy A Local Folder to S3

```shell
aws s3 cp --recursive /home/siddharthasandhu/<LOCAL_FOLDER> s3://siddhartha.sandhu/<FILE_NAME> 
```

Alternatively,
```shell
aws s3 sync /home/siddharthasandhu/<LOCAL_FOLDER> s3://siddhartha.sandhu/<FILE_NAME> 
```

## Copy A S3 Directory to Local

```shell
aws s3 cp --recursive s3://siddhartha.sandhu/<FILE_NAME> /home/siddharthasandhu/<LOCAL_FOLDER>
```

Alternatively,
```shell
aws s3 sync s3://siddhartha.sandhu/<FILE_NAME>  /home/siddharthasandhu/<LOCAL_FOLDER>
```

Here is the [S3 Documentation][s3-docs].

[s3-docs]: https://docs.aws.amazon.com/AmazonS3/latest/user-guide/what-is-s3.html
