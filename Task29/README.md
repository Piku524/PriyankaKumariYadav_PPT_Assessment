# Serverless + Event-Driven Architecture (AWS + Azure)

## Objective
Implement a fully event-driven serverless pipeline using cloud storage triggers, serverless compute, and managed NoSQL databases.

---
## Architecture
AWS:
S3 Bucket --> Lambda Function --> DynamoDB
- S3: Stores uploaded files
- Lambda: Triggered by S3 upload, writes metadata to DynamoDB
- DynamoDB: Stores uploaded file information
- CloudWatch: Monitors Lambda execution

Azure:
Blob Storage --> Function App (Blob Trigger) --> Cosmos DB
- Blob Storage: Stores uploaded files
- Function App: Triggered by blob upload, writes to Cosmos DB
- Cosmos DB: Stores file information

---
## AWS Execution Steps
1. Create S3 bucket: `aws s3 mb s3://my-aws-event-bucket-12345`
2. Create IAM role for Lambda with S3/DynamoDB access.
3. Create DynamoDB table `FileUploads`.
4. Create Lambda function `S3ToDynamo` with Python code.
5. Add S3 trigger for Lambda.
6. Test: Upload a file to S3, check DynamoDB table entries.

---
## Azure Execution Steps
1. Create resource group: `az group create --name RG-Serverless --location eastus`
2. Create Storage Account and container `uploads`.
3. Create App Service Plan (B1 Free-trial compatible)
4. Create Function App `BlobFunctionApp123`.
5. Add Blob Trigger Function `BlobToCosmos`.
6. Add Cosmos DB Output Binding to `FileDB.Uploads`.
7. Add Python code to write blob names to Cosmos DB.
8. Test: Upload file to Blob container → Check Function logs → Verify document in Cosmos DB.

---
## Verification
- AWS: S3 upload → Lambda invoked → DynamoDB contains fileName
- Azure: Blob upload → Function invoked → Cosmos DB document appears
- CloudWatch / Function logs confirm execution
