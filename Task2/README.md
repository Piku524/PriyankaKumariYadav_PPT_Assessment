Task 2: Disk Partitioning (Ubuntu – MBR & Windows – GPT)

## Simple Definition

Disk partitioning is the process of dividing a disk into separate sections for storage management.
MBR is used in Ubuntu and GPT is used in Windows.

## Objective

To understand disk management and storage structure using MBR in Ubuntu and GPT in Windows.

## Ubuntu (MBR)

### Steps

1. Create an Ubuntu EC2 instance.
2. Create and attach a Data Volume to the instance.
3. Connect to the instance using SSH.
4. Create partition using `fdisk`.
5. Format the partition with ext4 file system.
6. Mount the partition to `/mnt/myvol`.
7. Create and verify a file in the mounted directory.

### Verification

* `lsblk`
* `fdisk -l`

## Windows (GPT)

### Steps

1. Create a Windows EC2 instance.
2. Create and attach an EBS volume (10 GB).
3. Connect to the instance using RDP.
4. Open Disk Management.
5. Initialize disk using GPT.
6. Create a new simple volume and assign a drive letter.

## Conclusion

Disk partitioning was successfully performed using MBR in Ubuntu and GPT in Windows.
