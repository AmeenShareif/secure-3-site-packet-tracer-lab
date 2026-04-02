# Verification Matrix

This matrix matches the captured proof recorded in `docs/test-results.md`.

The repo uses screenshots of real Packet Tracer states instead of placeholder checks, so the evidence and the documentation stay aligned.

| Proof area | What the screenshot shows | Evidence |
| --- | --- | --- |
| Lab overview | The full Packet Tracer workspace and the current device layout. | `evidence/01-topology-overview.png` |
| Live link-state | The workspace list with the connected links in green. | `evidence/11-workspace-links-live.png` |
| HQ router setup | The HQ router config import succeeded and the router shows its expected interface state. | `evidence/02-hq-router-config-applied.png`, `evidence/03-hq-router-interface-status.png`, `evidence/12-router0-config-merge-success.png` |
| HQ hardware proof | The HQ router physical view shows the installed serial module. | `evidence/04-hq-router-physical-module.png` |
| HQ services proof | The DNS and web server pages show the configured lab services. | `evidence/05-hq-dns-record.png`, `evidence/06-hq-web-server-services.png` |
| HQ switching proof | The HQ core and access switches accepted their config imports and the server ports are in VLAN 50. | `evidence/13-switch0-config-merge-success.png`, `evidence/14-switch1-config-merge-success.png`, `evidence/20-switch0-fa1-vlan50.png`, `evidence/21-switch0-fa2-vlan50.png` |
| Branch proof | The branch router and branch switch accepted their config imports. | `evidence/15-router3-config-merge-success.png`, `evidence/17-switch2-config-merge-success.png` |
| DR proof | The DR router and switch accepted their config imports and the switch state shows the expected VLAN and interface information. | `evidence/07-dr-router-config-applied.png`, `evidence/08-dr-switch-config-applied.png`, `evidence/09-dr-switch-ip-int-brief.png`, `evidence/10-dr-switch-vlan-brief.png`, `evidence/16-router2-config-merge-success.png`, `evidence/18-switch4-config-merge-success.png` |
| Server addressing | The server shows the expected IPv4 address and default gateway. | `evidence/19-server0-ipconfig-only.png` |

## Notes

- The evidence set is intentionally focused on screenshots that show real state, real configuration, and real results.
- There are no placeholder rows in this matrix.
