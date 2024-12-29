# 2.12
assignment 2.12

Given a Lambda function that is triggered upon the creation of files in an S3 bucket, answer the following: 

1.	What is the purpose of the execution role on the Lambda function?

The execution role in an AWS Lambda function defines the permissions that the Lambda function has to interact with other AWS services and resources. When you configure a Lambda function, you need to assign it an IAM (Identity and Access Management) role, known as the execution role, which allows it to perform specific actions within your AWS environment. It ensures that your Lambda function has the necessary permissions to execute properly while maintaining security through the principle of least privilege. 


2.	What is the purpose of the resource-based policy on the Lambda function? 

The resource-based policy on an AWS Lambda function controls who can invoke or access the Lambda function, specifically defining which AWS services, users, or accounts can trigger the function. This policy is applied directly to the Lambda function itself and govern access to the function.


3.	If the function is needed to upload a file into an S3 bucket, describe (i.e no need for the actual policies)
- What is the needed update on the execution role? 

To upload a file to an Amazon S3 bucket, the AWS Lambda execution role must have the appropriate permissions to access S3. Specifically, the role needs permissions that allow it to perform the s3:PutObject action on the relevant S3 bucket.

Steps to Update the Execution Role:

a.	Identify the IAM role associated with the execution environment
b.	Add S3 Permissions:

Go to the IAM Console.
Select Roles from the sidebar.
Find and select the execution role.
Under the Permissions tab, click Add permissions.

c.	Attach Policy for S3 Access: You can either:

i.	Attach an existing policy such as AmazonS3FullAccess (or a more restrictive custom policy if you want to limit the scope), or
ii.	Create a custom policy that grants the s3:PutObject permission.


d.	 Once the policy is attached, save and apply the changes.
To ensure that an AWS Lambda function has the necessary permissions to access the resources it interacts with, you may need to update its execution role. The updates depend on the specific actions your Lambda function needs to perform.


- What is the new resource-based policy that needs to be added? To which resource? 

For a S3 bucket to trigger your Lambda function, you would add a resource-based policy to the Lambda function that grants the S3 service permission to invoke it.

Via the AWS Management Console:
   - Open the Lambda console.
   - Select the Lambda function for which you want to modify the permissions.
   - Go to the Permissions tab.
   - Scroll down to the Resource-based policy section.
   - Add or modify the policy to allow the necessary AWS service or account to invoke your Lambda function.

