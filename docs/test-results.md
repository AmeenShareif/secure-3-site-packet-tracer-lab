# Test Results

This is the place where I would record the actual Packet Tracer results after building the lab.

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
| `show ip ospf neighbor` | Routers | Confirm routing neighbors | To capture | `evidence/13-ospf-neighbors.png` |
| `show ip route` | `R-HQ` | Confirm routing table | To capture | `evidence/14-hq-route-table.png` |
| `show ip nat translations` | `R-HQ` | Confirm NAT works | To capture | `evidence/15-nat-translations.png` |
| `show access-lists` | `R-HQ` and `R-BR` | Confirm ACL hits | To capture | `evidence/16-acl-hit-counters.png` |
| `show port-security interface` | Access switches | Confirm port hardening | To capture | `evidence/17-port-security-status.png` |
