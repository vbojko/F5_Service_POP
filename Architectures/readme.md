*Welcome to the Architecture use cases.*

The use cases are self contained with all relevant documentation.

Here is a list of use cases with a short description:

**Usecase-1_12.1**
This Architecture deploys 2 BIG-IP DNS and 2 BIG-IP LTM.
All instances are behind a firewall and NAT happens at the Firewall level.
This deployment assumes that all instances use private RFC1918 IP Addresses.
All instances can communicate with each other over private RFC1918 IP addresses.
The communication happens over the external facing data interface, not over the
management interfaces.
