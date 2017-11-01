

Deployment Requirements in AWS:
===============================

#. 1 VPC with 2 Availability Zones (AZ) and 3 subnets per AZ.
  - subnet 1: mgmt subnet. This subnet needs outgoing internet connection only
  for licensing. If BIG-IQ licensing manager is available then no internet
  connection is needed.
  - subnet 2: public subnet .
  - subnet 3: private subnet - this subnet has no internet access.

  For a quick deployment of the VPC use the Cloud Formation Template (CFT)
  "VPC_with_MGMT_SG_with_IP_wizard-16subnets-withAZ2_v4.txt" in the Postman
  folder of the Use case. This CFT will deploy eigth subnets per AZ. This setup
  requires only three subnets per AZ. The additional subnets are for Server
  deployments. It may be considered for future use.

#. Every BIG-IP DNS will be deployed with 2 NICs
  - Eth0 - mgmt subnet
  - Eth1 - public subnet
  - 1 * Elastic IP (EIP) that will be associated with the public selfIP of each
    BIG-IP DNS.

#. Every BIG-IP LTM will be deployed with 3 NICs.
  - Eth0 - mgmt subnet
  - Eth1 - public subnet
  - Eth2: private subnet

.. Note:: LTM could be deployed with 2 NIC too, but most customers like to have
 a logical external and a logical internal interface.

.. Note:: A step by step description how to deploy a BIG-IP VE in AWS can be
found here: http://clouddocs.f5.com/cloud/public/v1/aws/AWS_multiNIC.html

.. Note:: HA between BIG-IP LTM is performed over BIG-IP DNS Global
Server Load Balancing, utilizing DNS.
