# AWS-S3-Webhosting

Hosting a Static Website on Amazon S3

This guide will help you host a static website on Amazon S3, one of the most scalable and cost-effective solutions available today.

Prerequisites :
1. AWS Account: You will need an AWS account to use S3.
2. AWS CLI (Optional): If you prefer to use the command line instead of the AWS Management Console
3. Website Files: Your static website files (HTML, CSS, JS, etc.).

Step-1 : Create a S3 Bucket 

Create a S3 bucket by navigating to S3 tab. Make sure ACLs, public access and bucket versioning are enabled for both bucket and the objects present in the bucket.

![image](https://github.com/user-attachments/assets/ab87329d-81e4-4e1b-9370-3cf59ba6816f)

Q.What is an ACL ?

An ACL = a set of rules that decides who can get access to a resource.

Enabling ACLs in this S3 setup lets you control who can access and do things with the objects (i.e. website files) you upload into your bucket.

With ACLs, different AWS accounts can own and control different files in your bucket.

The warning that pops up suggests that it's simpler to use something called "bucket policies". While they let you control access for the entire bucket (e.g. making the entire bucket and its objects public), bucket policies don't give you fine grained control over individual objects in your bucket.

Bottom line, if you know that the entire bucket contains no sensitive information, you can use a bucket policy. But if there's even one object in the bucket that you want to keep private, use ACLs.

Step-2 : Upload Website Content to Bucket

Upload the required contents to your bucket , using the Upload Option.(Make sure to upload a HTML file , makes the website part easier)

![image](https://github.com/user-attachments/assets/31bf0ca1-e803-4dac-b539-9f9d0d3de763)

Step-3 : Configure a Static Website on Amazon S3

Go to Properties section 

![image](https://github.com/user-attachments/assets/c5efab33-21d0-4e67-b0dc-f55fcecf25cc)

Scroll down till you find the "Configure a Static Website" option.

![image](https://github.com/user-attachments/assets/52606a40-1c9f-42b0-b48b-69a0bdf22770)

Click Edit.

![image](https://github.com/user-attachments/assets/3c5c1900-9e48-4d43-99dd-4824e5494432)

Select Enable , and Save Changes.

![image](https://github.com/user-attachments/assets/8d6a6fb1-a498-4e70-bc13-e9d2481372f0)

Checkpoint : If you followed all the above steps correctly , you should get this 

![image](https://github.com/user-attachments/assets/20142ee4-fd1b-45cb-8d93-3f3b36ef3e08)



If you thought the process ends here , no it does not. 

Click the link of the hosted website and check it , you will be getting 403 Forbidden Error.

![image](https://github.com/user-attachments/assets/422f18c3-c1bf-4bcb-89cd-b8f18384fcd2)

WHY ?

Objects (in this case, the HTML and images files you uploaded) are private by default. This default setting helps keep your account's data secure.

The error message you're seeing is telling you that your static website is being hosted by S3, but the actual HTML/image files you've uploaded are still private. It's kind of like having a bucket on display, so everyone can see the bucket - but the contents are covered up, preventing anyone from seeing what's inside.

To solve this error, we need to set the permission of the objects to public - this is why we enabled ACLs in Task 1!

Step-5 : Enable ACLs for the objects in the bucket again , and refresh the error page , you will be getting your website hosted now.

![image](https://github.com/user-attachments/assets/c5bda778-58c3-4bc3-bc5c-500f933741fd)






