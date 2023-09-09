# IasCode - Terraform

## Case 3
We will make a vpc peering to connect 2 ec2 instances, each on diferents regions.

  - Authentication with Variables
  - 2 VPC (CIDR 192.168.0.0/16 - 172.16.0.0./16)
  - 2 Subnets (192.168.0.0/24 - 172.16.0.0./24)
  - 2 Route table (Add entry for VPC peering)
  - Security Groups (Allow ping, ssh)
  - EC2 with provisioner
