# Test Results

This file records the final Packet Tracer validation captured for the portfolio repo.

## Captured setup evidence

| Check | Actual result | Status | Evidence |
| --- | --- | --- | --- |
| Topology overview | Packet Tracer workspace shows the HQ topology and the Router0 to Switch1 link. | Pass | `evidence/01-topology-overview.png` |
| HQ router config | `R-HQ` accepted the pasted config and returned to the router prompt. | Pass | `evidence/02-hq-router-config-applied.png` |
| HQ router interfaces | `show ip interface brief` shows the HQ subinterfaces up/up, `GigabitEthernet0/1` up/down, and the serial interfaces present on the 1941. | Pass | `evidence/03-hq-router-interface-status.png` |
| HQ router module install | The HWIC serial module is installed in the router physical view. | Pass | `evidence/04-hq-router-physical-module.png` |
| HQ DNS server | `Server0` is configured with `10.10.50.10/24`, gateway `10.10.50.1`, and the `intranet.corp.lab` A record points at `10.10.50.20`. | Pass | `evidence/05-hq-dns-record.png` |
| HQ web server | `Server1` is configured with `10.10.50.20/24`, gateway `10.10.50.1`, and the HTTP service page is visible. | Pass | `evidence/06-hq-web-server-services.png` |
| DR router config | `R-DR` accepted the pasted config, created the DR subinterfaces and OSPF settings, and returned to the `R-DR#` prompt. | Pass | `evidence/07-dr-router-config-applied.png` |
| DR switch config | `SW-DR` accepted the pasted config, created the DR VLANs, and returned to the `SW-DR#` prompt. | Pass | `evidence/08-dr-switch-config-applied.png` |
| DR switch interfaces | `show ip interface brief` on `SW-DR` shows `Vlan299` at `10.30.99.2` and `up/up`. | Pass | `evidence/09-dr-switch-ip-int-brief.png` |
| DR switch VLANs | `show vlan brief` on `SW-DR` shows VLANs `210`, `220`, and `299` created with the expected port memberships. | Pass | `evidence/10-dr-switch-vlan-brief.png` |

## Final validation

| Test | Source | Destination | Result | Evidence |
| --- | --- | --- | --- | --- |
| Guest gateway ping | `PC6` | `10.10.60.1` | Success, 4 replies received | `evidence/11-pc6-ping-gateway-success.png` |
| Guest private-network block | `PC6` | `10.10.50.10` | Blocked, destination host unreachable | `evidence/12-pc6-ping-private-blocked.png` |
| Secure management SSH | `Router0` | `10.10.99.3` | Success, SSH session reached `SW-HQ-ACCESS#` and returned `show ip interface brief` output | `evidence/13-router0-ssh-switch1.png` |

## Reading the snapshot

- The setup evidence confirms the HQ and DR portions of the lab that are already documented in the repo.
- The final validation section shows the completed security story: guest traffic can reach only the gateway, private internal traffic is blocked, and authenticated management access works over SSH.
