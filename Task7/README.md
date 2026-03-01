Task 7: Create EFS and Connect to Multiple Ubuntu Instances

Simple Definition
Create a shared scalable file system (EFS) and mount it on multiple Ubuntu EC2 instances to enable shared storage access.

Objective
Learn how AWS EFS can be used for multi-instance file sharing and scalable storage.

What I Did

Created an EFS file system with encryption and automatic backups

Launched multiple Ubuntu EC2 instances in the same VPC

Installed NFS utilities on each instance

Mounted EFS on all Ubuntu instances at /mnt/efs

Verified shared access by creating and reading files from multiple instances

Configured optional auto-mount on reboot using /etc/fstab

Result
Files created on one Ubuntu instance are visible and editable on other instances, demonstrating a shared, scalable storage solution.
