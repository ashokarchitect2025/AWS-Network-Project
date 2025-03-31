# AWS-Network-Project
**Secure VPC Infrastructure**

**VPC: Virtual Private Cloud**
**Definition**
A Virtual Private Cloud (VPC) is a virtual network within the AWS cloud dedicated to your AWS account. It provides a logically isolated environment for your AWS resources.

**Configuration:**
VPCs are created with a specified range of IP addresses using CIDR block notation.
AWS supports IPv4 CIDR blocks between /16 and /28 netmask.
Can add up to 5 CIDR Ranges Within a Single VPC.

**Maximum VPCs per Region:**
The default limit is 5 per region, which can be increased upon request.

===========================================================================================

**Subnets**
**Definition**
A subnet is a segmented portion of a VPC's IP address range that allows for the organized allocation of IP addresses.

**Configuration:**
Subnets are created within Availability Zones (AZs)

**Subnets per VPC**
The default limit is 200

===========================================================================================

**Public Subnet**
**Definition**
Subnet that's accessible from the internet

**Usage:**
Typically for web servers and load balancers

**Points to Consider:**
Requires an Internet Gateway for internet access

===========================================================================================

**Private Subnet**
**Definition**
Subnet not accessible from the internet

**Usage:**
Ideal for sensitive applications like databases

**Points to Consider:**
Requires a NAT Gateway for outbound internet access

===========================================================================================

**Internet Gateway**
**Role**
Connects AWS VPC to the internet

**Configuration**
Attached to VPC and routes traffic to/from the internet

**Points to Consider** 
Public IP Is Necessary for resources in the public subnet to communicate with the internet.

===========================================================================================

**NAT Gateway**
**Role**
Enables instances in a private subnet to access the internet for updates and downloads

**Configuration**
Placed in a public subnet with an Elastic IP address

**Points to Consider**
No inbound internet traffic allowed to private subnet through NAT
Each NAT Gateway supports up to 55,000 simultaneous connections

**Bandwidth:** Up to 45 Gbps, depending on the instance typec

===========================================================================================

**Route Tables**
Role 
Controls where network traffic is directed

**Configuration**
Main Route Table: Automatically created, manages default routing for all subnet
Custom Route Tables created manually for specific routing needs.

**Points to Consider**
Define rules to determine network traffic direction
Route Tables per VPC: Default limit is 200
Routes per Route Table: 50
