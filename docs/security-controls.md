# Security Controls

These are the main controls demonstrated in the lab.

## Segmentation

- Separate VLANs for each major trust zone.
- Guest wireless is isolated from internal subnets.
- Servers sit in their own VLAN instead of being mixed with user devices.
- Management uses dedicated VLANs at each site.

## Access control

- HR and Finance can only reach the approved HQ server VLAN and the public internet.
- Guest VLANs are blocked from internal private networks.
- Branch users can reach HQ services and the internet, but not arbitrary internal networks.
- SSH is allowed for network device management; Telnet is not.

## Device hardening

- Local user accounts and enable secrets are configured.
- RSA keys and SSHv2 are enabled.
- Unused switch ports are shut down.
- Access ports use port security with sticky MAC learning.
- Trunks are restricted to the VLANs they actually need.

## Routing and edge security

- OSPF advertises site reachability without manual static route sprawl.
- HQ originates the default route toward branch and DR.
- NAT/PAT on HQ hides internal RFC1918 sources from the public side.

## What this lab demonstrates in a portfolio

- You understand trust boundaries.
- You can enforce least privilege with ACLs.
- You can separate management from user traffic.
- You can show operational validation, not just configuration.
