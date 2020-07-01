# AWS : how to launch a EC2 and ping with the instance

First goal is to create an instance on AWS edu
https://console.aws.amazon.com/console/
- Chose EC2
- Launch instance
- Choose Amazon Linux 2 AMI (HVM), SSD Volume Type
- Choose General purpose / t2.micro (Free tier eligible)
- "Configure instance details", to be able to custom it as we want
-  modify "Network" (VPC) to refer to my VPN
-  modify "Subnet" to refer to my public VPN
-  modify Auto-assign Public IP > 'Enable'

while on "Network" (VPC) > create new VPC ! with IPv4 CIDR 10.0.0.0/16
- Subnet : create 2 > One private (IPv4 CIDR 10.0.2.0/24), one public (IPv4 CIDR 10.0.1.0/24)
- Route Tables : create a private one to link to the private Subnet
- Internet Gateway (IGW) : create a new one to link to the VPC created
- Security Groups : create a new one, with SSH	TCP	22	0.0.0.0/0 
- to be able to ping the instance later on, need to add new rule with Inbound Custom ICMP - IPv4	Echo Request	N/A	My IP
