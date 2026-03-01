Task 4: ASG and ELB in EC2

Simple Definition
Configure Auto Scaling Group with Load Balancer to achieve high availability and automatic scaling of EC2 instances.

Objective
To understand how Auto Scaling Group works with Elastic Load Balancer for traffic distribution and fault tolerance.

What I Did

Launched an EC2 instance and deployed a website using Nginx

Created an AMI from the configured instance

Created a Launch Template using the AMI

Created a Target Group for health checks

Created an Application Load Balancer and attached the target group

Created an Auto Scaling Group using the Launch Template

Configured scaling policy based on CPU utilization

Verified load balancing and automatic instance scaling

Result

The website is accessible through Load Balancer DNS.
Auto Scaling Group maintains desired instances and replaces unhealthy instances automatically.
