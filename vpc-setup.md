# AWS VPC Lab – VPC Setup

## VPC & CIDR Blocks
- **VPC Name**: `shreyas-vpc`
- **CIDR**: `10.0.0.0/16` (provides ~65K IPs)
- **Public Subnet**: `10.0.1.0/24` (256 IPs)
- **Private Subnet**: `10.0.2.0/24`

## Internet Gateway (IGW)
- Created and attached to the VPC
- Enables internet access for public subnet

## Route Tables
- **Public Route Table**:
  - Associated with `public-subnet`
  - Route: `0.0.0.0/0` → Internet Gateway
- **Private Subnet**:
  - No route to IGW
  - (Could use NAT Gateway for internet access)

## Public vs Private Subnet Logic
- **Public Subnet**: 
  - Has route to Internet Gateway
  - EC2s can be accessed from internet
- **Private Subnet**: 
  - No direct internet access
  - Used for backend resources (DBs, internal services)
