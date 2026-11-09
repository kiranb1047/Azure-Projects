# Virtual Networking with DNS resolution

This project involved setting up a virtual network for virtual machines (VMs) on Microsoft Azure. I accomplished this by creating a virtual network, deploying the VMs within it, assigning private and public IP addresses to the VMs, setting up network security groups to control access, and finally configuring Azure DNS for both internal and external name resolution.

# Project Details
- The services that were used during the course of this Projects are Powershell, Virtual Networks, Network Security Group, Private DNS Zones and DNS Zones

- Additional information is provided on a seperate document file.

# Steps

- I set up a virtual network(VNet) on Azure. I added it to a group of related resources called a resource group. Finally, I gave the virtual network a range of IPv4 addresses to use, specifically 10.40.0.0/20.

- The ARM Template(JSON) included on this project was used on Powershell.

- I gave each of the two virtual machines a dynamic public internet address. Additionally I assigned each virtual machine a permanent internal address on the network.

- I added a network security group rule that allows Remote Desktop (port 3389) to the virtual machines so I could test connectivity and name resolution. This was a short-lived lab setup. In a real environment I would not expose RDP to the whole internet.

- And then leveraged Azure's "Private DNS Zone" service to establish a private DNS for the virtual network. This enables internal name resolution, allowing the VMs to find each other using custom names rather than IP addresses

- And finally used Azure's "DNS Zone" service to create a public DNS zone. This allows internet access to my virtual machines by entering a custom domain name instead of a complex IP address.
- 
# Security note

Opening port 3389 to any source is acceptable only for a temporary lab. For production I would:
- Restrict the rule's source to specific trusted IP addresses.
- Use Azure Bastion or a VPN instead of public RDP, or just-in-time VM access in Microsoft Defender for Cloud.
- Use network security groups with least-privilege rules and no public IPs on VMs where possible.
  
  # Project background

These projects are hands-on labs I completed while studying for Microsoft's AZ-104 (Azure Administrator) material. The ARM templates (files starting with `az104-`) come from the Microsoft lab content. I deployed them myself in my own Azure subscription, configured the networking, security rules and DNS, and documented the results here.

# Conclusion

Succesfully implemented Internal Name Resoultion and External Name resolution for the Machines on the Virtual network to make it easier to remember domain names instead of hard to remember the Internal and External IP addresses.


