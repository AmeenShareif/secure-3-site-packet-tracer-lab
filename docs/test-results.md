# Test Results

This file records the live Packet Tracer proof captured for the portfolio repo.

Every row points to a screenshot in `evidence/`, and every screenshot shows a real state change, configuration value, or live result.

## Whole-lab proof

| Check | Actual result | Status | Evidence |
| --- | --- | --- | --- |
| Lab overview | The Packet Tracer workspace shows the full lab layout and device placement. | Pass | `evidence/01-topology-overview.png` |
| Live link-state | The workspace list shows the connected links in green where expected. | Pass | `evidence/11-workspace-links-live.png` |

## HQ proof

| Check | Actual result | Status | Evidence |
| --- | --- | --- | --- |
| HQ router config import | `Router0` accepted the HQ config merge and returned the success dialog. | Pass | `evidence/02-hq-router-config-applied.png`, `evidence/12-router0-config-merge-success.png` |
| HQ router interface state | `R-HQ` shows the expected subinterfaces and up/up status in `show ip interface brief`. | Pass | `evidence/03-hq-router-interface-status.png` |
| HQ router hardware | The router physical view shows the serial module installed. | Pass | `evidence/04-hq-router-physical-module.png` |
| HQ DNS service | The DNS server includes the `intranet.corp.lab` A record. | Pass | `evidence/05-hq-dns-record.png` |
| HQ web service | The web server services page shows the site files loaded. | Pass | `evidence/06-hq-web-server-services.png` |
| HQ core switch config import | `Switch0` accepted the core switch config merge and returned the success dialog. | Pass | `evidence/13-switch0-config-merge-success.png` |
| HQ access switch config import | `Switch1` accepted the access switch config merge and returned the success dialog. | Pass | `evidence/14-switch1-config-merge-success.png` |
| HQ server addressing | `Server0` shows IPv4 `10.10.50.10` with default gateway `10.10.50.1`. | Pass | `evidence/19-server0-ipconfig-only.png` |
| HQ server VLAN ports | `Switch0` FastEthernet0/1 and FastEthernet0/2 are access ports in VLAN 50. | Pass | `evidence/20-switch0-fa1-vlan50.png`, `evidence/21-switch0-fa2-vlan50.png` |

## Branch and DR proof

| Check | Actual result | Status | Evidence |
| --- | --- | --- | --- |
| Branch router config import | `Router3` accepted the branch router config merge and returned the success dialog. | Pass | `evidence/15-router3-config-merge-success.png` |
| Branch switch config import | `Switch2` accepted the branch switch config merge and returned the success dialog. | Pass | `evidence/17-switch2-config-merge-success.png` |
| DR router config import | `Router2` accepted the DR router config merge and returned the success dialog. | Pass | `evidence/07-dr-router-config-applied.png`, `evidence/16-router2-config-merge-success.png` |
| DR switch config import | `Switch4` accepted the DR switch config merge and returned the success dialog. | Pass | `evidence/08-dr-switch-config-applied.png`, `evidence/18-switch4-config-merge-success.png` |
| DR switch interface state | `SW-DR` shows `Vlan299` up/up in `show ip interface brief`. | Pass | `evidence/09-dr-switch-ip-int-brief.png` |
| DR VLAN membership | `SW-DR` shows the expected DR VLANs and access ports in `show vlan brief`. | Pass | `evidence/10-dr-switch-vlan-brief.png` |

## Reading the snapshot

- The repo now records real config-import proof, service pages, port/VLAN state, server addressing, and workspace link-state evidence.
- The screenshots are focused on what Packet Tracer actually showed on screen, so the documentation and evidence stay aligned.
