# Cloud Launchpad: VPC + EC2

A small, beginner-friendly CloudFormation template for the AWS re/Start lab. It builds a basic network and one EC2 instance so you can practice Infrastructure as Code without extra complexity.

## What it creates
- VPC with DNS enabled
- Internet Gateway attached to the VPC
- Private subnet (no public IPs on launch)
- Security group allowing SSH on port 22 for the lab
- EC2 t3.micro using the latest Amazon Linux 2 AMI via SSM

Note: You do not need to SSH into the instance to complete the lab.

## Quick start
1. Open AWS Console and go to CloudFormation.
2. Create stack with new resources.
3. Upload `template.yaml`.
4. Name the stack (for example, `cloud-launchpad`) and create it.
5. Wait for status `CREATE_COMPLETE`.

## Verify
- VPC named `cloud-launchpad-vpc`
- Subnet named `cloud-launchpad-private-subnet`
- EC2 named `cloud-launchpad-ec2`
- Outputs tab shows VPC ID, Subnet ID, Security Group ID, and Instance ID

## Parameters
- `ProjectName` used in Name tags (default `cloud-launchpad`)
- `InstanceType` `t3.micro` default or `t2.micro`
- `LatestAmazonLinuxAMI` SSM path for the latest Amazon Linux 2 AMI

## Clean up
Delete the stack in CloudFormation to remove all resources.

Author: Eskinder Kassahun · GitHub: https://github.com/Eskinder185