Task 13: Start/Stop EC2 using Lambda + API Gateway 

Objective:
Automate starting and stopping an EC2 instance using a Lambda function triggered via an HTTP API Gateway endpoint.

Steps:

Created IAM role LambdaEC2Role with AmazonEC2FullAccess and AWSLambdaBasicExecutionRole.

Created Lambda function StartStopEC2 with Python 3.11 using the role.

Added API Gateway (HTTP API, Open) as trigger for Lambda.

Tested API endpoint to start/stop EC2 instances successfully
