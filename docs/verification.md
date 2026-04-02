# Screenshot Map

This page matches the screenshots listed in `docs/test-results.md`.

The list below is the same proof set used in the results file.

| Proof area | What the screenshot shows | Evidence |
| --- | --- | --- |
| Lab overview | The full Packet Tracer workspace and the device layout. | `evidence/01-topology-overview.png` |
| Live link-state | The workspace list with the links in green. | `evidence/11-workspace-links-live.png` |
| HQ router setup | The HQ router config import succeeded and the router shows the expected interface state. | `evidence/02-hq-router-config-applied.png`, `evidence/03-hq-router-interface-status.png`, `evidence/12-router0-config-merge-success.png` |
| HQ hardware proof | The HQ router physical view shows the serial module installed. | `evidence/04-hq-router-physical-module.png` |
| HQ services proof | The DNS and web server pages show the configured lab services. | `evidence/05-hq-dns-record.png`, `evidence/06-hq-web-server-services.png` |
| HQ switching proof | The HQ core and access switches accepted their config imports and the server ports are in VLAN 50. | `evidence/13-switch0-config-merge-success.png`, `evidence/14-switch1-config-merge-success.png`, `evidence/20-switch0-fa1-vlan50.png`, `evidence/21-switch0-fa2-vlan50.png` |
| Branch proof | The branch router and branch switch accepted their config imports. | `evidence/15-router3-config-merge-success.png`, `evidence/17-switch2-config-merge-success.png` |
| DR proof | The DR router and switch accepted their config imports and the switch state shows the expected VLAN and interface information. | `evidence/07-dr-router-config-applied.png`, `evidence/08-dr-switch-config-applied.png`, `evidence/09-dr-switch-ip-int-brief.png`, `evidence/10-dr-switch-vlan-brief.png`, `evidence/16-router2-config-merge-success.png`, `evidence/18-switch4-config-merge-success.png` |
| Server addressing | The server shows the expected IPv4 address and default gateway. | `evidence/19-server0-ipconfig-only.png` |

## Notes

- The evidence set is only screenshots that show real state, real config, or a real result.
- Every row below is a real screenshot.
