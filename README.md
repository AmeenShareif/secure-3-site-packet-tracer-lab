# Secure 3-Site Packet Tracer Lab

This repository contains a Cisco Packet Tracer lab for a cybersecurity portfolio. The network uses a fictional company so the design can demonstrate segmentation, access control, secure management, routing, NAT, and validation without referencing a real business.

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
- `docs/portfolio-writeup.md` - short portfolio summary
- `docs/portfolio-visuals.md` - diagrams and charts for the project
- `docs/project-status.md` - repository snapshot summary
- `docs/evidence-guide.md` - evidence capture format
- `docs/test-results.md` - validation snapshot and command output
- `evidence/` - screenshots and exported proof
- `configs/` - IOS configs for each router and switch
- `cybersecurity-portfolio-lab.pkt` - the live Packet Tracer save file for this lab

## Current snapshot

- The repo includes the Packet Tracer save file, device configs, service settings, and screenshots used in the portfolio.
- `docs/test-results.md` records the captured validation results and live command output.
- `docs/project-status.md` summarizes the repository in a clean, review-ready format.
- `evidence/` contains the screenshots referenced by the documentation.

## Portfolio angle

This project is presented as a security and networking lab, not just a basic Packet Tracer build. The main idea is:

- guests are isolated from internal systems
- departments are segmented
- only approved users can manage network devices
- branch and DR sites are reachable through controlled routing
- internet access works through NAT, but internal traffic is still restricted

## Project title

`Secure Multi-Site Enterprise Network with Segmentation and Access Control`

## How to use this kit

1. Review the topology in `docs/topology.md`.
2. Check the IP plan in `docs/ip-plan.md`.
3. Review the configs in `configs/`.
4. Compare the validation checklist in `docs/verification.md` with the captured results in `docs/test-results.md`.
5. Open the screenshots in `evidence/`.
6. Use `docs/project-status.md` as the repository snapshot summary.
