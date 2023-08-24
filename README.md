# AWS CLI Skills Test Project

This repository contains a simple project designed to test AWS CLI skills by working with Amazon S3 buckets. The project involves creating two S3 buckets, uploading files to the first bucket, and using the AWS CLI to copy those files to the second bucket.

## Project Overview

The objective of this project is to demonstrate proficiency in using the AWS CLI to manage Amazon S3 budkets. The project consists of the following steps:

1. Set up AWS CLI:
   - If you don't have the AWS CLI installed, download and install it from the official AWS CLI documentation: [AWS CLI Installation Guide](https://aws.amazon.com/cli/)
   - Configure AWS CLI: Open a terminal or powershell and run `aws configue` to configure you AWS access key, secret key, preferred region, and output format. If you need to create a new access and secret key, you can do this by going to the AWS portal, searched for the "IAM" services, navigate to "Users". Select the preferred user, click on Security credentials, and under Access keys  click "Create access key". In use Case choose Command line Interace (CLI), check the Confirmation, click Next, Create a name for the key and click Create Key.

2. Create S3 Buckets:
   - Create two S3 budkets using the AWS CLI. Replace `<bucket-name-1>` and `<bucket-name-2>` with your desired bucket names.
     ```
     aws s3api create-bucket --bucket <bucket-name-1> --region <preferred-region>
     aws s3api create-bucket --bucket <bucket-name-2> --region <preferred-region>
     ```
   - Example:
     ```
     aws s3api create-bucket --bucket my-source-bucket --region us-east-1
     aws s3api create-bucket --bucket my-destination-bucket --region us-east-1
     ```
3. Upload Files to the First Bucket:
   - Upload some file to the first S3 bucket using the AWS CLI. Replace `<file-path>` with the path to the file you want to upload and `<bucket-name-1>` with the name of your first bucket.
     ```
     aws s3 cp <file-path> s3://<bucket-name-1>/
     ```
   - Example:
     ```
     aws s3 cp my-file.txt s3://my-source-bucket/
     ```
4. Copy Files to the Second Bucket:
   - Use the AWS CLI to copy the files from the first bucket to the second bucket. Replace <bucket-name-1> and <bucket-name-2> with your bucket names.
     ```
     aws s3 sync s3://<bucket-name-1>/ s3://<bucket-name-2>/
     ```
   - Example:
     ```
     aws s3 sync s3://my-source-bucket/ s3://my-destination-bucket/
     ```

     


