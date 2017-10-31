*Classical deployment of BIG-IP DNS and BIG-IP LTM behind a NAT device.*

This use case applies to deployments of BIG-IP DNS and LTM in public cloud
provider infrastructure, like AWS. This specific use case would deploy in AWS
in one VPC in two Availability Zones (AZ). Each AZ contains one BIG-IP DNS and
one BIG-IP LTM.

The documentation can be found here
http://f5-gslb-in-aws.readthedocs.io/en/latest/

The REST API collection for this use case works with BIG-IP version 12.1.2.
For BIG-IP version 13.0 the REST API for BIG-IP DNS has changed.
The use case for 13.0 can be found here:  
*REF: ../Usecase-1_v13.0/*
