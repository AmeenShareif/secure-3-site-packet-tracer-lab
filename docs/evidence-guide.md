# Evidence Guide

This is how I would show the actual results of the Packet Tracer lab.

## What counts as actual results

- Ping results from Packet Tracer PCs
- Browser or web access results
- SSH login sessions to routers and switches
- `show` command output from routers and switches
- ACL hit counts or blocked traffic evidence
- Port-security violation evidence

## What to capture for each test

For each test, I would record:

- Test name
- Source device
- Destination device
- Command used
- What actually happened
- Pass or fail
- Screenshot file name

## Good evidence examples

- `ping 10.10.50.20` from an HQ PC
- `ping 203.0.113.10` from a guest laptop
- `show ip route` on `R-HQ`
- `show ip ospf neighbor` on all routers
- `show ip nat translations` on `R-HQ`
- `show access-lists` on `R-HQ` or `R-BR`
- `show port-security interface fa0/2` on a switch

## Suggested screenshot names

- `evidence/01-hq-admin-to-web.png`
- `evidence/04-guest-blocked-from-dns.png`
- `evidence/05-guest-internet.png`
- `evidence/10-ssh-session.png`
- `evidence/13-ospf-neighbors.png`
- `evidence/15-nat-translations.png`

## How I would present it

I would keep the evidence simple:

1. One short explanation of the test
2. One screenshot or command output
3. One sentence saying whether it passed
4. One note about why the result matters for security
