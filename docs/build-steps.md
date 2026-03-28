# Build Steps

This is the order I would use in Packet Tracer.

## 1. Place devices

- 1 HQ router
- 1 HQ core switch
- 1 HQ access switch
- 1 branch router
- 1 branch switch
- 1 DR router
- 1 DR switch
- 1 ISP router
- 1 public server
- 2 HQ servers
- 1 guest AP at HQ
- 1 guest AP at branch
- 1 PC per department and at least 1 test laptop per guest VLAN

## 2. Cable the topology

- Router to switch links should be trunk links where router-on-a-stick is used.
- HQ router `G0/1` connects to the ISP router.
- HQ router `S0/0/0` connects to Branch router `S0/0/0`.
- HQ router `S0/0/1` connects to DR router `S0/0/0`.
- Make the HQ side the DCE end on both serial links so the clock rate lines work.
- Public server connects to the ISP router.

## 3. Configure the ISP side first

- Assign `198.51.100.1/30` to the ISP router.
- Assign `203.0.113.1/24` to the public-side interface.
- Set the public server to `203.0.113.10/24` with gateway `203.0.113.1`.

## 4. Configure HQ routing and VLANs

- Build the HQ VLANs on both HQ switches.
- Create router subinterfaces on `R-HQ`.
- Add the HQ DHCP pools.
- Apply NAT/PAT and the HQ ACLs.

## 5. Configure Branch and DR

- Build each site VLAN set.
- Create subinterfaces on the site router.
- Add local DHCP pools.
- Enable OSPF and verify neighbors.

## 6. Harden switches

- Create local usernames.
- Enable SSH only.
- Configure management SVI addresses.
- Apply port security to access ports.
- Shut down unused ports.

## 7. Configure hosts

- Put user PCs on DHCP.
- Set servers to static addresses.
- Configure the AP SSID and WPA2 key.
- Use the guest VLAN for wireless clients.
- Turn on HTTP and DNS services on the servers listed in `docs/services.md`.

## 8. Finish the lab services

- Set the HQ DNS A record for `intranet.corp.lab`.
- Set the public server as the internet simulation target.
- Confirm guest clients receive the public DNS server.

## 9. Verify

- Ping allowed destinations.
- Confirm blocked destinations fail.
- Validate SSH.
- Validate NAT from internal sites to the public server.
