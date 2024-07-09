# Virtual Networking with DNS resolution

This project involved setting up a virtual network for virtual machines (VMs) on Microsoft Azure. I accomplished this by creating a virtual network, deploying the VMs within it, assigning private and public IP addresses to the VMs, setting up network security groups to control access, and finally configuring Azure DNS for both internal and external name resolution.

# Project Details
- The services that were used during the course of this Projects are Powershell, Virtual Networks, Network Security Group, Private DNS Zones and DNS Zones

- Additional information is provided on a seperate document file.

# Steps

- I set up a virtual network(VNet) on Azure. I added it to a group of related resources called a resource group. Finally, I gave the virtual network a range of IPv4 addresses to use, specifically 10.40.0.0/20.

- The ARM Template(JSON) included on this project was used on Powershell.

- I gave each of the two virtual machines a dynamic public internet address. Additionally I assigned each virtual machine a permanent internal address on the network.

- I set up a security rule to allow anyone on the internet to remotely access the virtual machines using Remote Desktop. This remote access uses port 3389.

- And then leveraged Azure's "Private DNS Zone" service to establish a private DNS for the virtual network. This enables internal name resolution, allowing the VMs to find each other using custom names rather than IP addresses

- And finally used Azure's "DNS Zone" service to create a public DNS zone. This allows internet access to my virtual machines by entering a custom domain name instead of a complex IP address.

# Conclusion

Succesfully implemented Internal Name Resoultion and External Name resolution for the Machines on the Virtual network to make it easier to remember domain names instead of hard to remember the Internal and External IP addresses.
