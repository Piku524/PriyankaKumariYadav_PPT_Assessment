Task 3: IAM + RBAC + Least Privilege (AWS + Azure)

Objective:
Implement role-based access control (RBAC) with least privilege policy 
in AWS IAM and Azure Entra ID.

---

PART 1: AWS IAM

Step 1: Add a User
1. Login to AWS Management Console.
2. Go to Services → IAM → Users → Add users.
3. User name: Developer
4. Access type: 
   - AWS Management Console access (for portal login)
   - Programmatic access (for CLI/API)
5. Click Next: Permissions

Step 2: Attach EC2 Full Access
1. Select "Attach existing policies directly"
2. Search: AmazonEC2FullAccess
3. Check the policy → Next: Tags → Next: Review → Create user

Step 3: Create Custom Policy to Deny S3 Delete
1. Go to IAM → Policies → Create policy → JSON tab
2. Paste JSON:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": [
        "s3:DeleteObject",
        "s3:DeleteObjectVersion"
      ],
      "Resource": "*"
    }
  ]
}

3. Review policy → Name: DenyS3Delete → Create policy

Step 4: Attach Custom Policy to User
1. IAM → Users → Developer → Add permissions
2. Attach policies directly → Search DenyS3Delete → Add permissions

Step 5: Test Permissions
1. Login as Developer
2. EC2: Launch/start/stop instance → Should work
3. S3: Delete object → Should fail ("Access Denied")

---

PART 2: Azure Entra ID

Step 6: Open Azure Portal and Go to Entra ID
1. Login to https://portal.azure.com
2. Search "Microsoft Entra ID" → Users

Step 7: Create New User
1. Click + New user → Create user
2. Name: Developer
3. Username: developer@yourdomain.onmicrosoft.com
4. Password: auto-generate or custom
5. Click Create

Step 8: Assign Reader Role on Resource Group
1. Go to Resource Groups → Select the RG
2. Access control (IAM) → + Add → Add role assignment
3. Role: Reader
4. Assign access to: User → Select Developer → Review + Assign
5. Test: Developer can view all resources in RG, cannot modify/delete

Step 9: Assign Contributor Role on Specific VM
1. Go to Virtual Machines → Select VM
2. Access control (IAM) → + Add → Add role assignment
3. Role: Contributor
4. Assign access to: User → Select Developer → Review + Assign
5. Test: Developer can start/stop/restart this VM only, cannot modify others

Step 10: Verify All Permissions
1. Login as Developer
2. Resource Group: View resources → allowed
3. VM: Start/Stop → allowed
4. Other resources: Modify/Delete → denied

---
