Task 9: Access S3 from Ubuntu using IAM Roles & Policies

Objective: Learn role-based access to S3 from EC2 without using AWS keys.

Steps Performed:
1. Created IAM policy S3FullAccessPolicy with all S3 permissions.
2. Created IAM role S3AccessRole for EC2 and attached the policy.
3. Launched Ubuntu EC2 instance with the IAM role attached.
4. Connected via SSH and verified S3 access using AWS CLI.
5. Uploaded a test file to S3 to confirm permissions
