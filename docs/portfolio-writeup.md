# Portfolio Write-Up

I built this Cisco Packet Tracer lab to practice secure network design and to have something stronger for my cybersecurity portfolio. I used a fictional company so I could keep the network realistic without tying it to a real business.

The lab has three sites: a headquarters, a branch office, and a disaster recovery site. I separated the network into VLANs for admin, HR, finance, IT, servers, guest Wi-Fi, and management. I also added OSPF for routing, DHCP for clients, NAT/PAT for internet access, ACLs to limit traffic, SSH for management, and port security on switch ports.

What I wanted to show with this project is that I understand more than basic connectivity. I wanted the network to show security thinking, like least privilege, segmentation, and controlled access between different parts of the network.

I have already verified the HQ router inside Packet Tracer and captured screenshots of the real device state. I am still building out the remaining sites and test cases, so the repo shows real progress instead of pretending everything is finished.

### What I practiced

- VLAN design
- Router-on-a-stick
- OSPF
- DHCP
- NAT/PAT
- ACLs
- SSH-only management
- Switch port security

### What I learned

- Breaking a network into smaller trust zones makes it easier to protect.
- ACL order matters and can change the result of a test.
- Documentation is part of the project, not something extra at the end.
- A clean network story is just as important as the configs.
