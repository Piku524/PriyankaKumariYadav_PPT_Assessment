Task 11: S3 Upload Email Notification (Lambda + SNS)

Objective: Trigger an email notification whenever a file is uploaded to an S3 bucket using Lambda and SNS.

Steps Performed:
1. Created IAM role LambdaSNSRole with AWSLambdaBasicExecutionRole and AmazonSNSFullAccess.
2. Created Lambda function S3UploadNotifier with runtime Python 3.14 using the above role.
3. Added S3 trigger for all object create events.
4. Created SNS topic S3UploadNotification and added email subscription.
5. Tested upload of file to S3 bucket and confirmed email notification.
