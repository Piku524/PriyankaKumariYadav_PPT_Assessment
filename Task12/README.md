Task 12: Website Down Alert using Lambda + SNS

Objective
Automatically monitor a website and receive email alerts if it goes down.

Steps
1. Created IAM Role LambdaWebsiteMonitorRole with policies:
   - AWSLambdaBasicExecutionRole
   - AmazonSNSFullAccess
   - CloudWatchFullAccess
2. Created Lambda function WebsiteMonitor (Python) with the role attached.
3. Added EventBridge trigger to run Lambda every 5 minutes.
4. Created SNS Topic WebsiteDownAlert and subscribed email.
5. Created CloudWatch Alarm on WebsiteUp metric; triggers SNS on failure.
6. Tested with invalid URL; email alert received.
