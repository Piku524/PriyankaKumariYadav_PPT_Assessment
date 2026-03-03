Task 3: Attach EBS Volume from Different AZ using Snapshot

Objective
To move an EBS volume from one Availability Zone to another using snapshot and attach it to a different EC2 instance.

Steps Summary

Launch Source EC2 in AZ-1

Create and attach EBS volume to Source EC2

Mount the volume and create a test file

Create snapshot of the volume

Launch Target EC2 in AZ-2

Create new volume from snapshot in AZ-2

Attach new volume to Target EC2

Mount the volume and verify data

Verification
cat /data/test.txt
Output: Hello Snapshot

Result
The EBS snapshot was restored as a new volume in a different Availability Zone and successfully attached to another EC2 instance with data preserved.

Conclusion
EBS snapshots are region-wide and help in migrating storage across Availability Zones for backup and disaster recovery.
