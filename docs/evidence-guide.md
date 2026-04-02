# Evidence Guide

This page defines what counts as valid Packet Tracer evidence for the portfolio.

## Valid evidence

- Config merge success dialogs that show the device name and the import result
- Interface or VLAN screens that show IP addresses, gateways, or port membership
- `show` command output that clearly proves the device state being documented
- DNS and HTTP service pages that show the configured records or files
- Live workspace link-state screenshots that show the lab is connected as expected
- SSH or CLI sessions that clearly show remote management is working
- ACL, NAT, or port-security proof if the screenshot shows a real result instead of a placeholder

## Evidence record

For each test, record:

- Test name
- Source device
- Destination device
- Command used
- Observed result
- Status
- Screenshot file name

## Example proof shots

- `Router0` merge dialog after loading `configs/R-HQ.txt`
- `show ip interface brief` on `R-HQ`
- DNS server page showing `intranet.corp.lab`
- Web server services page showing the site files
- Workspace list showing green link-state entries
- `SW-DR` `show vlan brief` showing the DR VLANs and access ports

## Presentation format

- One short note about what the screenshot proves
- One screenshot or command output
- One sentence stating the result
- One note about the security meaning of the result
