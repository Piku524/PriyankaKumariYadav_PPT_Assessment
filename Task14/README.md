Task 14: CloudWatch Alarm (70% CPU → Auto Stop + Email)

Objective:
Automatically monitor EC2 CPU usage. If CPU exceeds 70%, the instance stops automatically and an email notification is sent via SNS.

Steps:
Created CloudWatch Alarm on CPUUtilization metric for the EC2 instance.

Set threshold: Static, CPU > 70%.

Added action: Stop instance automatically and send SNS email notification.

Created or used existing SNS Topic and subscribed email.

Named alarm HighCPU_Stop_Instance and created it.

Tested with CPU stress tool (stress-ng) → alarm triggered, instance stopped automatically, email received.
