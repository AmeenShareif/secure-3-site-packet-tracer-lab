# Secure 3-Site Packet Tracer Lab

This is a Cisco Packet Tracer lab I made for my cybersecurity portfolio. I set it up as a fictional company network so I could show segmentation, access control, secure management, routing, NAT, and testing in a way that feels realistic.

## What is included

- 3 sites: HQ, Branch, and DR
- VLAN segmentation for users, guests, servers, and management
- Inter-VLAN routing with router-on-a-stick
- OSPF between all sites
- DHCP pools for each user network
- NAT/PAT at the HQ edge
- ACLs for guest isolation and department restrictions
- SSH-only device management
- Switch port security and unused-port shutdown
- Internet simulation through an ISP router and public server

## Folder guide

- `docs/topology.md` - network story and topology diagram
- `docs/ip-plan.md` - VLANs, subnets, gateways, and host addressing
- `docs/security-controls.md` - control-by-control security summary
- `docs/build-steps.md` - Packet Tracer build order
- `docs/services.md` - DNS, web, and Wi-Fi service settings
- `docs/verification.md` - test matrix and expected outcomes
- `docs/portfolio-writeup.md` - short first-person summary for a portfolio
- `docs/portfolio-visuals.md` - diagrams and charts for the project
- `docs/project-status.md` - work-in-progress tracker
- `docs/evidence-guide.md` - how to capture real Packet Tracer proof
- `docs/test-results.md` - results log with expected and actual columns
- `evidence/` - place for screenshots and exported proof
- `configs/` - IOS configs for each router and switch
- `cybersecurity-portfolio-lab.pkt` - the live Packet Tracer save file for this lab

## Current progress

- I have already verified the HQ router in Packet Tracer and saved screenshots in `evidence/`.
- The HQ switches are configured and the HQ DNS and web servers are now being built out and documented.
- The DR router and DR switch are now configured and verified in Packet Tracer with real CLI output and screenshots.
- I also ran live Packet Tracer ping and SSH tests from a PC and a server. The loopback ping works, but the real network targets are still timing out, which tells me the host addressing or wiring is not finished yet.
- The branch site and the remaining WAN and test cases are still being built, so the repo shows real progress instead of a fake finished lab.

## Portfolio angle

I would present this as a security and networking project, not just a basic Packet Tracer lab. The main idea is:

- guests are isolated from internal systems
- departments are segmented
- only approved users can manage network devices
- branch and DR sites are reachable through controlled routing
- internet access works through NAT, but internal traffic is still restricted

## Suggested title

`Secure Multi-Site Enterprise Network with Segmentation and Access Control`

## How to use this kit

1. Build the physical Packet Tracer topology from `docs/topology.md`.
2. Apply the IP addressing plan from `docs/ip-plan.md`.
3. Paste the device configs from `configs/`.
4. Validate the lab with `docs/verification.md`.
5. Capture screenshots and add them to your portfolio write-up.
6. Use `docs/project-status.md` to show what is finished and what is still in progress.
7. Fill in `docs/test-results.md` after you run the Packet Tracer tests.
