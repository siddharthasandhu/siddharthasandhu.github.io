---
layout: post
title:  "Removing Files from S3"
date:   2020-02-15 12:03:36 +0530
categories: AWS S3
---
## Prerequites
* `awscli` should be installed.
* Setup `awscli` for your `IAM` user.
* Allow S3 admin access for the `IAM` user.

To remove a file in AWS S3 navigate to the bucket in which the file is stored:

* Navigate to the bucket:
```shell
aws s3 ls
```
* List files in the directory:
```shell
aws s3 ls s3://name-of-bucket/
```
* Recursively list files in "suffix keys" a.k.a directories in S3 till you reach the required file to delete.
* Run the following to remove the file:
```shell
aws s3 rm s3://name-of-bucket/<recursive-suffixes>/name-of-file-to-delete
```
***NOTE***: To avoid accidental deletion. Add `--dryrun` to the commandline to preview the removal.

## Remove All Files in S3 Folder

I highly advise running the following command with `--dryrun` first:
```shell
aws s3 rm --recursive s3://name-of-bucket/<recursive-suffixes>/
```


