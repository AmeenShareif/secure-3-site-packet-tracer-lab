# Portfolio Visuals

This page collects the diagrams and charts used to explain the project.

## Network topology

```mermaid
flowchart LR
  ISP["R-ISP / Internet"]
  HQR["R-HQ"]
  BRR["R-BR"]
  DRR["R-DR"]
  HQC["SW-HQ-CORE"]
  HQA["SW-HQ-ACCESS"]
  BRS["SW-BR"]
  DRS["SW-DR"]
  PUB["Public Server"]
  HQS["HQ Servers VLAN 50"]
  HGG["HQ Guest VLAN 60"]
  HQM["HQ Management VLAN 99"]
  BRU["Branch Users VLAN 110"]
  BRG["Branch Guest VLAN 120"]
  DRI["DR IT VLAN 210"]
  DRB["DR Backup VLAN 220"]

  HQR -->|"198.51.100.0/30 NAT edge"| ISP
  ISP -->|"203.0.113.0/24"| PUB
  HQR -->|"172.16.0.0/30 OSPF"| BRR
  HQR -->|"172.16.0.4/30 OSPF"| DRR
  HQR -->|"trunk"| HQC
  HQC -->|"trunk"| HQA
  HQC -->|"access"| HQS
  HQA -->|"access"| HGG
  HQA -->|"access"| HQM
  BRR -->|"trunk"| BRS
  BRS -->|"access"| BRU
  BRS -->|"access"| BRG
  DRR -->|"trunk"| DRS
  DRS -->|"access"| DRI
  DRS -->|"access"| DRB
```

## Security zones

```mermaid
flowchart LR
  G["Guest"]
  U["User VLANs"]
  S["Server VLAN"]
  M["Management VLAN"]
  NET["Internet"]

  G -->|"Internet only"| NET
  U -->|"Approved access"| S
  M -->|"SSH and admin access"| U
  M -->|"SSH and admin access"| S
  G -. "Blocked by ACLs" .-> U
  G -. "Blocked by ACLs" .-> S
  G -. "Blocked by ACLs" .-> M
```

## Project workflow

```mermaid
stateDiagram-v2
  [*] --> Planning
  Planning --> Design
  Design --> Build
  Build --> Test
  Test --> Document
  Document --> Publish
  Publish --> [*]
```

## Milestone summary

```mermaid
flowchart LR
  A["Scope and story"] --> B["IP plan"]
  B --> C["Device configs"]
  C --> D["Evidence capture"]
  D --> E["Validation log"]
  E --> F["Write-up"]
```
