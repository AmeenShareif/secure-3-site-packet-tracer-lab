# Services

These are the services I turned on in Packet Tracer.

## HQ DNS server

- IP: `10.10.50.10`
- Subnet mask: `255.255.255.0`
- Default gateway: `10.10.50.1`
- DNS service: on
- Add an A record for `intranet.corp.lab` pointing to `10.10.50.20`

## HQ web server

- IP: `10.10.50.20`
- Subnet mask: `255.255.255.0`
- Default gateway: `10.10.50.1`
- HTTP service: on
- Optional web page title: `Northstar Logistics Intranet`

## Public server

- IP: `203.0.113.10`
- Subnet mask: `255.255.255.0`
- Default gateway: `203.0.113.1`
- HTTP service: on
- DNS service: on
- Optional public A record: `www.northstar-public.net` -> `203.0.113.10`

## Guest Wi-Fi

- HQ SSID: `NS-GUEST-HQ`
- Branch SSID: `NS-GUEST-BR`
- Security: WPA2-PSK
- Pre-shared key: `Guest@2026!`

## Host behavior

- Corporate PCs in HQ, Branch, and DR should use DHCP.
- Management PCs can use static addresses from the management VLANs.
- Guest laptops should use DHCP and the public DNS server.
