# Test Results

This is where I record the actual Packet Tracer results after building the lab.
I have verified the HQ router setup so far, and I will keep adding the rest of the lab as I test it.

## Verified so far

| Check | Actual result | Status | Evidence |
| --- | --- | --- | --- |
| Topology overview | Packet Tracer is open with the HQ topology visible and the Router0 to Switch1 link active. | Pass | `evidence/01-topology-overview.png` |
| HQ router config | `R-HQ` accepted the pasted config and came up as the active router hostname. | Pass | `evidence/02-hq-router-config-applied.png` |
| HQ router interfaces | `show ip interface brief` shows the HQ subinterfaces up/up, `GigabitEthernet0/1` up/down, and the serial interfaces present on the 1941. | Pass | `evidence/03-hq-router-interface-status.png` |
| HQ router module install | The HWIC serial module is installed in the router physical view. | Pass | `evidence/04-hq-router-physical-module.png` |
| HQ DNS server | `Server0` is configured with `10.10.50.10/24`, gateway `10.10.50.1`, and the `intranet.corp.lab` A record points at `10.10.50.20`. | Pass | `evidence/05-hq-dns-record.png` |
| HQ web server | `Server1` is configured with `10.10.50.20/24`, gateway `10.10.50.1`, and the HTTP service page is visible with the site files. | Pass | `evidence/06-hq-web-server-services.png` |
| DR router config | `R-DR` accepted the pasted config, created the DR subinterfaces and OSPF settings, and returned to the `R-DR#` prompt. | Pass | `evidence/07-dr-router-config-applied.png` |
| DR switch config | `SW-DR` accepted the pasted config, created the DR VLANs, and returned to the `SW-DR#` prompt. | Pass | `evidence/08-dr-switch-config-applied.png` |
| DR switch interfaces | `show ip interface brief` on `SW-DR` shows `Vlan299` at `10.30.99.2` and `up/up`, with the unused access ports still shut down. | Pass | `evidence/09-dr-switch-ip-int-brief.png` |
| DR switch VLANs | `show vlan brief` on `SW-DR` shows VLANs `210`, `220`, and `299` created with the expected access-port assignments. | Pass | `evidence/10-dr-switch-vlan-brief.png` |

## Results log

| Test | Source | Destination | Expected result | Actual result | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| Internal web access | HQ Admin PC | HQ Web Server `10.10.50.20` | Success | To capture | Pending | `evidence/01-hq-admin-to-web.png` |
| HR isolation | HQ HR PC | Finance PC `10.10.30.x` | Fail | To capture | Pending | `evidence/02-hr-isolation.png` |
| Finance isolation | HQ Finance PC | HR PC `10.10.20.x` | Fail | To capture | Pending | `evidence/03-finance-isolation.png` |
| Guest isolation | HQ Guest laptop | HQ DNS Server `10.10.50.10` | Fail | To capture | Pending | `evidence/04-guest-blocked-from-dns.png` |
| Guest internet | HQ Guest laptop | Public Server `203.0.113.10` | Success | To capture | Pending | `evidence/05-guest-internet.png` |
| Branch internet | Branch user PC | Public Server `203.0.113.10` | Success | To capture | Pending | `evidence/06-branch-to-internet.png` |
| Branch internal restriction | Branch user PC | HQ Admin subnet `10.10.10.0/24` | Fail | To capture | Pending | `evidence/07-branch-blocked-from-hq-admin.png` |
| Branch server access | Branch user PC | HQ Web Server `10.10.50.20` | Success | To capture | Pending | `evidence/08-branch-to-hq-web.png` |
| DR IT access | DR IT PC | HQ Web Server `10.10.50.20` | Success | To capture | Pending | `evidence/09-dr-it-to-hq-web.png` |
| SSH management | HQ Admin or IT PC | Router or switch VTY | Success via SSH | To capture | Pending | `evidence/10-ssh-session.png` |
| Telnet ban | Any user PC | Router or switch VTY | Fail | To capture | Pending | `evidence/11-telnet-blocked.png` |
| Port security | Rogue device on access port | Access switch | Violation logged / restricted | To capture | Pending | `evidence/12-port-security-violation.png` |

## Command output log

| Command | Device | Purpose | Actual result | Evidence |
| --- | --- | --- | --- | --- |
| `show ip interface brief` | `R-HQ` | Confirm HQ interfaces and subinterfaces | `GigabitEthernet0/0.10-0.99` are up/up, `GigabitEthernet0/1` is up/down, and the serial interfaces are present but not yet connected to peers. | `evidence/03-hq-router-interface-status.png` |
| `show ip ospf neighbor` | Routers | Confirm routing neighbors | To capture | `evidence/13-ospf-neighbors.png` |
| `show ip route` | `R-HQ` | Confirm routing table | To capture | `evidence/14-hq-route-table.png` |
| `show ip nat translations` | `R-HQ` | Confirm NAT works | To capture | `evidence/15-nat-translations.png` |
| `show access-lists` | `R-HQ` and `R-BR` | Confirm ACL hits | To capture | `evidence/16-acl-hit-counters.png` |
| `show port-security interface` | Access switches | Confirm port hardening | To capture | `evidence/17-port-security-status.png` |
| `show ip interface brief` | `SW-DR` | Confirm DR management SVI | `Vlan299` is `10.30.99.2` and `up/up`; unused FastEthernet ports remain administratively down. | `evidence/09-dr-switch-ip-int-brief.png` |
| `show vlan brief` | `SW-DR` | Confirm DR VLAN creation | VLANs `210`, `220`, and `299` are present with the expected port memberships. | `evidence/10-dr-switch-vlan-brief.png` |

## Live tests run

These are the Packet Tracer tests I ran most recently while checking real connectivity. I kept the results here even when they failed so the repo shows the actual state of the lab.

| Test | Source | Destination | Result | Evidence |
| --- | --- | --- | --- | --- |
| PC6 ping to HQ web server | `PC6` | `10.10.50.20` | Fail, all 4 packets timed out | `evidence/11-pc6-live-command-results.png` |
| PC6 local loopback | `PC6` | `127.0.0.1` | Success, 4 replies received | `evidence/11-pc6-live-command-results.png` |
| PC6 SSH attempt | `PC6` | `10.10.50.10` | Fail, remote host not responding | `evidence/11-pc6-live-command-results.png` |
| PC6 address check | `PC6` | Local IP config | Shows APIPA `169.254.48.39` and no default gateway | `evidence/13-pc6-ipconfig.png` |
| Server0 ping to HQ web server | `Server0` | `10.10.50.20` | Fail, all 4 packets timed out | `evidence/12-server0-ping-results.png` |
| Server0 ping to its own IP | `Server0` | `10.10.50.10` | Fail, request timed out | `evidence/12-server0-ping-results.png` |
