# ServerlessArchitecture_Sunil

Uploaded 10 Assignment Answers here, code for each assignment uploaded above.

ASSIGNMENT - 1-----------------------------------------------------------------------------------------------------------------------------------------------------

Setup:

Create two EC2 instances.

Tag one of them as Auto-Stop and the other as Auto-Start.

Lambda Function Creation:

Set up an AWS Lambda function.

Ensure that the Lambda function has the necessary IAM permissions to describe, stop, and start EC2 instances.

Coding:

Using Boto3 in the Lambda function:

Detect all EC2 instances with the Auto-Stop tag and stop them.

Detect all EC2 instances with the Auto-Start tag and start them.

Testing:

Manually invoke the Lambda function.

Confirm that the instance tagged Auto-Stop stops, and the one tagged Auto-Start starts.

Instructions:

EC2 Setup:

Navigate to the EC2 dashboard and create two new t2.micro instances (or any other available free-tier type).

Tag the first instance with a key Action and value Auto-Stop.

Tag the second instance with a key Action and value Auto-Start.

Lambda IAM Role:

In the IAM dashboard, create a new role for Lambda.

Attach the AmazonEC2FullAccess policy to this role. (Note: In a real-world scenario, you would want to limit permissions for better security.)

Lambda Function:

Navigate to the Lambda dashboard and create a new function.

Choose Python 3.x as the runtime.

Assign the IAM role created in the previous step.

Write the Boto3 Python script to:

Initialize a boto3 EC2 client.
Describe instances with Auto-Stop and Auto-Start tags.
Stop the Auto-Stop instances and start the Auto-Start instances.
Print instance IDs that were affected for logging purposes.
Manual Invocation:

After saving your function, manually trigger it.

Go to the EC2 dashboard and confirm that the instances' states have changed according to their tags.




ASSIGNMENT - 2-----------------------------------------------------------------------------------------------------------------------------------------------------

Step 1: S3 Setup
1.1. Navigate to the S3 dashboard and create a new bucket.

1.2. Upload multiple files to this bucket, ensuring that some files are older than 30 days.

Step 2: Lambda IAM Role
2.1. In the IAM dashboard, create a new role for Lambda.

2.2. Attach the AmazonS3FullAccess policy to this role.

Step 3: Lambda Function
3.1. Navigate to the Lambda dashboard and create a new function.

3.2. Choose Python 3.x as the runtime.

3.3. Assign the IAM role created in the previous step.

3.4. Write the Boto3 Python script:

3.5. Save the function.

Step 4: Manual Invocation
4.1. After saving your function, manually trigger it.

4.2. Go to the S3 dashboard and confirm that only files newer than 30 days remain.




ASSIGNMENT - 3-----------------------------------------------------------------------------------------------------------------------------------------------------

Step 1: RDS Setup
Navigate to the RDS dashboard and create a new RDS instance. Note the name of the instance.
Step 2: Lambda IAM Role
In the IAM dashboard, create a new role for Lambda.
Attach the AmazonRDSFullAccess policy to this role.
Step 3: Lambda Function
Navigate to the Lambda dashboard and create a new function.
Choose Python 3.x as the runtime.
Assign the IAM role created in the previous step.

Step 4: Event Source (Bonus)
Attach an event source, like Amazon CloudWatch Events, to trigger the Lambda function every day (or as per your preferred frequency).
Step 5: Manual Invocation
After saving your function, manually trigger it (or wait for the scheduled trigger).
Go to the RDS dashboard and confirm that a snapshot has been taken.


ASSIGNMENT - 4-----------------------------------------------------------------------------------------------------------------------------------------------------

Steps:
1. S3 Setup:
Navigate to the S3 dashboard and create a few buckets. Ensure that a couple of them don't have server-side encryption enabled.

2. Lambda IAM Role:
In the IAM dashboard, create a new role for Lambda.

Attach the AmazonS3ReadOnlyAccess policy to this role.


3. Lambda Function:
Navigate to the Lambda dashboard and create a new function.

Choose Python 3.x as the runtime.

Assign the IAM role created in the previous step.

Write the Boto3 Python script:

4. Manual Invocation:
After saving your function, manually trigger it.

Review the Lambda logs to identify the buckets without server-side encryption.



ASSIGNMENT - 5-----------------------------------------------------------------------------------------------------------------------------------------------------

1. EBS Setup:
Navigate to the EC2 dashboard.
Identify or create an EBS volume to back up.
Note down the volume ID.
2. Lambda IAM Role:
In the IAM dashboard, create a new role for Lambda.
Attach policies like AmazonEC2FullAccess to allow Lambda to create EBS snapshots and delete them.
(Note: In real-world scenarios, it's recommended to be more restrictive)
3. Lambda Function:
Navigate to the Lambda dashboard and create a new function.
Choose Python 3.x as the runtime.
Assign the IAM role created in the previous step.
Write the Boto3 Python script:

4. Event Source (Bonus):
Attach an event source like Amazon CloudWatch Events to trigger the Lambda function at your desired backup frequency.
5. Manual Invocation:
After saving your function, either manually trigger it or wait for the scheduled event.
Go to the EC2 dashboard and confirm that the snapshot is created, and old snapshots are deleted.




ASSIGNMENT - 6-----------------------------------------------------------------------------------------------------------------------------------------------------

Documentation:
1. EC2 Setup:
Ensure you have the capability to launch EC2 instances.
2. Lambda IAM Role:
In the IAM dashboard, create a new role for Lambda.

Attach the AmazonEC2FullAccess policy to this role.


3. Lambda Function:
Navigate to the Lambda dashboard and create a new function.

Choose Python 3.x as the runtime.

Assign the IAM role created in the previous step.

Write the Boto3 Python script:

Save the Lambda function.


4. CloudWatch Events:
Set up a CloudWatch Event Rule to trigger the EC2 instance launch event.

Attach the Lambda function as the target.


5. Testing:
Launch a new EC2 instance.

After a short delay, confirm that the instance is automatically tagged as specified.





ASSIGNMENT - 7-----------------------------------------------------------------------------------------------------------------------------------------------------

1. SNS Setup:
Navigate to the SNS dashboard and create a new topic.
Subscribe your email to this topic.
2. Lambda IAM Role:
In the IAM dashboard, create a new role for Lambda.
Attach policies that allow reading CloudWatch metrics and sending SNS notifications.
3. Lambda Function:
Navigate to the Lambda dashboard and create a new function.
Choose Python 3.x as the runtime.
Assign the IAM role created in the previous step.
Here's a sample Python script for the Lambda function:

4. Event Source (Bonus):
Attach an event source, like Amazon CloudWatch Events, to trigger the Lambda function daily.
5. Testing:
Manually trigger the Lambda function or wait for the scheduled event.
If your billing is over the threshold, you should receive an email alert.
Make sure to replace 'your_sns_topic_arn' with the actual ARN of the SNS topic you created. Also, modify the script according to your specific needs.




ASSIGNMENT - 8-----------------------------------------------------------------------------------------------------------------------------------------------------


Documentation:
1. DynamoDB Setup:
Navigate to the DynamoDB dashboard and create a table named MyTable.
Add a few items to the table.

2. SNS Setup:
Navigate to the SNS dashboard and create a new topic named MyTopic.
Subscribe your email to this topic.

3. Lambda IAM Role:
In the IAM dashboard, create a new role named LambdaDynamoDBRole for Lambda.
Attach policies that allow Lambda to read DynamoDB Streams and send SNS notifications.

4. Lambda Function:
Navigate to the Lambda dashboard and create a new function named DynamoDBChangeAlert.
Choose Python 3.x as the runtime.
Assign the IAM role (LambdaDynamoDBRole) created in the previous step.

5. DynamoDB Stream:
Enable DynamoDB Streams on the MyTable.
Set the view type to "New and old images".
Attach the Lambda function (DynamoDBChangeAlert) to the DynamoDB Stream.

6. Testing:
Update an item in your DynamoDB table.
Confirm that you receive an SNS alert detailing the change.



ASSIGNMENT - 9-----------------------------------------------------------------------------------------------------------------------------------------------------

Step 1: Lambda IAM Role
In the AWS Management Console, navigate to the IAM dashboard.
Click on "Roles" in the left sidebar and then "Create role."
Choose "AWS Lambda" as the use case.
Attach policies like ComprehendReadOnly or create a custom policy with necessary permissions for Amazon Comprehend.
Complete the role creation by providing a meaningful name and description.
Step 2: Lambda Function
Navigate to the Lambda dashboard.
Click on "Create function" and choose "Author from scratch."
Set a name for your function, choose "Python 3.x" as the runtime, and select the IAM role created in step 1.
Click on "Create function."

Step 3: Testing
Manually trigger the Lambda function by clicking on "Test" in the Lambda console.
Provide a sample event with the user review:

{
  "review": "This product is amazing! I love it."
}


Check the Lambda logs for the sentiment analysis results:

Sentiment analysis result for the review: POSITIVE




ASSIGNMENT - 10-----------------------------------------------------------------------------------------------------------------------------------------------------

Step 1: S3 Setup
1.1. Navigate to the AWS S3 Dashboard.

1.2. Create a new S3 bucket.

1.3. Upload a mix of old and new files to this bucket.

Step 2: Lambda IAM Role
2.1. Navigate to the AWS IAM Dashboard.

2.2. Create a new IAM role for Lambda.

2.3. Attach the AmazonS3FullAccess policy to this role.

Step 3: Lambda Function
3.1. Navigate to the AWS Lambda Dashboard.

3.2. Create a new Lambda function.

3.3. Choose Python 3.x as the runtime.

3.4. Assign the IAM role created in Step 2.

3.5. Write the Boto3 Python script:





