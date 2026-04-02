# Evidence Folder

This folder contains the Packet Tracer screenshots and command outputs referenced in the portfolio docs.

## Evidence index

- `01-topology-overview.png` - main Packet Tracer workspace with the HQ router and switch link visible
- `02-hq-router-config-applied.png` - HQ router config paste and interface state messages
- `03-hq-router-interface-status.png` - `show ip interface brief` on `R-HQ`
- `04-hq-router-physical-module.png` - HQ router physical view with the serial module installed
- `05-hq-dns-record.png` - HQ DNS server configured with the `intranet.corp.lab` A record
- `06-hq-web-server-services.png` - HQ web server services page with the site files visible
- `07-dr-router-config-applied.png` - DR router config paste output and completed `R-DR#` prompt
- `08-dr-switch-config-applied.png` - DR switch config paste output and completed `SW-DR#` prompt
- `09-dr-switch-ip-int-brief.png` - DR switch `show ip interface brief` showing `Vlan299` up/up
- `10-dr-switch-vlan-brief.png` - DR switch `show vlan brief` showing the DR VLANs and port membership
- `11-pc6-ping-gateway-success.png` - PC6 command prompt showing successful ping replies from the guest gateway
- `12-pc6-ping-private-blocked.png` - PC6 command prompt showing the blocked ping to the private HQ server subnet
- `13-router0-ssh-switch1.png` - Router0 SSH session to `SW-HQ-ACCESS` showing the live remote management shell

The file names match the validation log in `docs/test-results.md`.
