# Evidence Guide

This page says which screenshots count as proof for the project.

## What counts as proof

- Config merge success dialogs that show the device name and the result
- Interface or VLAN screens that show IP addresses, gateways, or port membership
- `show` command output that clearly shows the device state
- DNS and HTTP service pages that show the configured records or files
- Workspace link-state screenshots that show the lab is connected
- SSH or CLI sessions that show remote management working
- ACL, NAT, or port-security proof if the screenshot shows an actual result

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

- One short note about what the screenshot shows
- One screenshot or command output
- One sentence stating the result
- One note about why the result matters
