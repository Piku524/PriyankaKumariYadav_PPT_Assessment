Task 6: S3 Replication and Lifecycle Policy

Simple Definition
Configure replication and lifecycle rules in S3 to optimize cost and maintain backups.

Objective
Understand how S3 versioning, replication, and lifecycle policies can be used for backup strategy and cost optimization.

What I Did

Created two S3 buckets (source and destination)

Enabled versioning on both buckets

Configured replication from source to destination bucket

Created IAM role for replication permissions

Configured lifecycle rule to manage objects (e.g., transition to Infrequent Access, auto-delete)

Verified replication and lifecycle actions

Result
Changes in the source bucket replicate automatically to the destination bucket.
Objects are managed automatically by lifecycle rules for cost optimization and retention.
