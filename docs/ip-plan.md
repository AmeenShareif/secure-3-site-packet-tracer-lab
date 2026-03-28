# IP Plan

The addressing plan stays simple so it is easy to follow in Packet Tracer.

## Addressing standards

- Default subnet mask for user VLANs: `/24`
- WAN point-to-point links: `/30`
- HQ management VLAN: `10.10.99.0/24`
- Branch management VLAN: `10.20.99.0/24`
- DR management VLAN: `10.30.99.0/24`

## Site VLANs

| Site | VLAN | Purpose | Subnet | Gateway |
| --- | --- | --- | --- | --- |
| HQ | 10 | Admin | 10.10.10.0/24 | 10.10.10.1 |
| HQ | 20 | HR | 10.10.20.0/24 | 10.10.20.1 |
| HQ | 30 | Finance | 10.10.30.0/24 | 10.10.30.1 |
| HQ | 40 | IT | 10.10.40.0/24 | 10.10.40.1 |
| HQ | 50 | Servers | 10.10.50.0/24 | 10.10.50.1 |
| HQ | 60 | Guest Wi-Fi | 10.10.60.0/24 | 10.10.60.1 |
| HQ | 99 | Management | 10.10.99.0/24 | 10.10.99.1 |
| Branch | 110 | Users | 10.20.10.0/24 | 10.20.10.1 |
| Branch | 120 | Guest Wi-Fi | 10.20.20.0/24 | 10.20.20.1 |
| Branch | 199 | Management | 10.20.99.0/24 | 10.20.99.1 |
| DR | 210 | IT | 10.30.10.0/24 | 10.30.10.1 |
| DR | 220 | Backup Servers | 10.30.20.0/24 | 10.30.20.1 |
| DR | 299 | Management | 10.30.99.0/24 | 10.30.99.1 |

## WAN links

| Link | Network | Left | Right |
| --- | --- | --- | --- |
| HQ to ISP | 198.51.100.0/30 | R-HQ 198.51.100.2 | R-ISP 198.51.100.1 |
| HQ to Branch | 172.16.0.0/30 | R-HQ 172.16.0.1 | R-BR 172.16.0.2 |
| HQ to DR | 172.16.0.4/30 | R-HQ 172.16.0.5 | R-DR 172.16.0.6 |

## Static hosts

| Device | IP | Notes |
| --- | --- | --- |
| HQ DNS Server | 10.10.50.10 | DNS for internal clients |
| HQ Web Server | 10.10.50.20 | Internal intranet |
| HQ Switch Mgmt | 10.10.99.2 | SW-HQ-CORE |
| HQ Access Switch Mgmt | 10.10.99.3 | SW-HQ-ACCESS |
| Branch Mgmt PC | 10.20.99.10 | Optional management workstation |
| Branch Switch Mgmt | 10.20.99.2 | SW-BR |
| DR Mgmt PC | 10.30.99.10 | Optional management workstation |
| DR Switch Mgmt | 10.30.99.2 | SW-DR |
| Public Server | 203.0.113.10 | Internet simulation, HTTP and DNS |

## DHCP ranges

- HQ Admin: `10.10.10.100-10.10.10.199`
- HQ HR: `10.10.20.100-10.10.20.199`
- HQ Finance: `10.10.30.100-10.10.30.199`
- HQ IT: `10.10.40.100-10.10.40.199`
- HQ Guest: `10.10.60.100-10.10.60.199`
- Branch Users: `10.20.10.100-10.20.10.199`
- Branch Guest: `10.20.20.100-10.20.20.199`
- DR IT: `10.30.10.100-10.30.10.199`
