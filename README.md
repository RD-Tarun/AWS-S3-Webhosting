# AWS-S3-Webhosting

Hosting a Static Website on Amazon S3

This guide will help you host a static website on Amazon S3, a scalable and cost-effective solution.


Prerequisites :
1. AWS Account: You will need an AWS account to use S3.
2. AWS CLI (Optional): If you prefer to use the command line instead of the AWS Management Console
3. Website Files: Your static website files (HTML, CSS, JS, etc.).

Step-1 : Create a S3 Bucket 
Create a S3 bucket by navigating to S3 tab. Make sure ACLs, public access and bucket versioning are enabled.
![image](https://github.com/user-attachments/assets/ab87329d-81e4-4e1b-9370-3cf59ba6816f)

Step-2 : Upload Website Content to Bucket
Upload the required contents to your bucket , using the Upload Option.
![image](https://github.com/user-attachments/assets/6a86fd1d-bc47-40c3-924e-405253549f93)

Step-3 : Configure a Static Website on Amazon S3
Enable static-bucket-hosting in the Properties section of your bucket.
