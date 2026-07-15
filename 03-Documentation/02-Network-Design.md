# Network Design

## Network Topology

Hub-and-Spoke Architecture

Hub VNet
- Region: Central India
- Address Space: 10.0.0.0/16

Spoke1
- Region: Central India
- Address Space: 10.1.0.0/16
- Windows VM
- Private IP: 10.1.1.4

Spoke2
- Region: East US
- Address Space: 10.2.0.0/16
- Windows VM
- Private IP: 10.2.1.4

---

# Network Connectivity

- Hub connected to Spoke1 using VNet Peering.
- Hub connected to Spoke2 using Global VNet Peering.
- Traffic between spokes is routed through Azure Firewall using User Defined Routes (UDRs).

---

# Routing

Traffic Flow

VM1

↓

Route Table

↓

Azure Firewall

↓

Global VNet Peering

↓

Azure Firewall

↓

VM2

---

# Azure Firewall Rules

## DNAT Rules

| Public Port | Destination VM | Private Port |
|-------------|----------------|--------------|
|8080         |        10.1.1.4|          3389|
|8081         |        10.2.1.4|          3389|

---

## Network Rules

Allow

Source: Spoke1

Destination: Spoke2

Protocol: TCP

Port: 3389

Allow

Source: Spoke2

Destination: Spoke1

Protocol: TCP

Port: 3389