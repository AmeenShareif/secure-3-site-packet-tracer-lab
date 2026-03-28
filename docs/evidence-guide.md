# Evidence Guide

This page defines what counts as valid Packet Tracer evidence for the portfolio.

## Valid evidence

- Ping results from Packet Tracer PCs
- Browser or web access results
- SSH login sessions to routers and switches
- `show` command output from routers and switches
- ACL hit counts or blocked traffic evidence
- Port-security violation evidence

## Evidence record

For each test, record:

- Test name
- Source device
- Destination device
- Command used
- Observed result
- Status
- Screenshot file name

## Example commands

- `ping 10.10.50.20` from an HQ PC
- `ping 203.0.113.10` from a guest laptop
- `show ip route` on `R-HQ`
- `show ip ospf neighbor` on all routers
- `show ip nat translations` on `R-HQ`
- `show access-lists` on `R-HQ` or `R-BR`
- `show port-security interface fa0/2` on a switch

## Presentation format

- One short note about the test
- One screenshot or command output
- One sentence stating the result
- One note about the security meaning of the result
