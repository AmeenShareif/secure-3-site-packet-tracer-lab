# Verification Matrix

This checklist matches the validation snapshot in `docs/test-results.md`.

Use `docs/test-results.md` to record the actual output, status, and evidence after you run the tests in Packet Tracer.

| Test | Source | Destination | Expected result |
| --- | --- | --- | --- |
| Internal web access | HQ Admin PC | HQ Web Server `10.10.50.20` | Success |
| HR isolation | HQ HR PC | Finance PC `10.10.30.x` | Fail |
| Finance isolation | HQ Finance PC | HR PC `10.10.20.x` | Fail |
| Guest isolation | HQ Guest laptop | HQ DNS Server `10.10.50.10` | Fail |
| Guest internet | HQ Guest laptop | Public Server `203.0.113.10` | Success |
| Branch internet | Branch user PC | Public Server `203.0.113.10` | Success |
| Branch internal restriction | Branch user PC | HQ Admin subnet `10.10.10.0/24` | Fail |
| Branch server access | Branch user PC | HQ Web Server `10.10.50.20` | Success |
| DR IT access | DR IT PC | HQ Web Server `10.10.50.20` | Success |
| SSH management | HQ Admin or IT PC | Router or switch VTY | Success via SSH |
| Telnet ban | Any user PC | Router or switch VTY | Fail |
| Port security | Rogue device on access port | Access switch | Violation logged / restricted |

## Validation evidence

- `show ip ospf neighbor`
- `show ip route`
- `show ip nat translations`
- `show access-lists`
- `show port-security interface`
- Screenshots of successful and failed pings
- SSH session screenshot
