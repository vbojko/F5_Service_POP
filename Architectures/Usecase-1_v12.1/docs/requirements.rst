

**Deployment Requirements in AWS:**
- 1 VPC with 2 Availability Zones (AZ) and 3 subnets per AZ.
  - subnet 1: mgmt subnet. This subnet needs outgoing internet connection only
  for licensing. If BIG-IQ licensing manager is available then no internet
  connection is needed.
  - subnet 2: public subnet .
  - subnet 3: private subnet - this subnet has no internet access.
- Every BIG-IP DNS will be deployed with 2 NICs.
  - Eth0 - mgmt subnet
  - Eth1 - public subnet
  - 1 * Elastic IP (EIP) that will be associated with the public selfIP of each
    BIG-IP DNS.
- Every BIG-IP LTM will be deployed with 3 NICs.
  - Eth0 - mgmt subnet
  - Eth1 - public subnet
  - Eth2: private subnet

Note:
LTM could be deployed with 2 NIC too, but most customers like to have a logical
external interface and a logical internal interface.

HA between BIG-IP LTM is performed over BIG-IP DNS Global
Server Load Balancing, utilizing
