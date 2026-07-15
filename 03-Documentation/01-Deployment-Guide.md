# Azure Hub-and-Spoke Network Architecture Deployment Guide

## Project Overview

This project demonstrates a secure Hub-and-Spoke network architecture in Microsoft Azure using Azure Firewall as the centralized security solution.

The solution enables secure communication between virtual machines located in different Virtual Networks (VNets) without exposing them directly to the Internet.

The Windows Virtual Machines are accessed securely through Azure Firewall DNAT rules.

---

# Architecture Summary

| Component | Configuration |
|-----------|---------------|
| Hub Region | Central India |
| Spoke 1 Region | Central India |
| Spoke 2 Region | East US |
| Hub Address Space | 10.0.0.0/16 |
| Spoke 1 Address Space | 10.1.0.0/16 |
| Spoke 2 Address Space | 10.2.0.0/16 |
| VM1 Private IP | 10.1.1.4 |
| VM2 Private IP | 10.2.1.4 |

---

# Azure Services Used

- Azure Resource Group
- Azure Virtual Network
- Azure Firewall
- Azure Firewall Policy
- Azure Public IP
- Azure Route Tables (UDR)
- Azure Network Security Groups
- Azure Virtual Machines
- Azure VNet Peering

---

# Deployment Steps

1. Create Resource Group
2. Create Hub Virtual Network
3. Deploy Azure Firewall
4. Create Spoke1 Virtual Network
5. Create Spoke2 Virtual Network
6. Configure Global VNet Peering
7. Create Route Tables
8. Associate UDRs with Subnets
9. Configure Azure Firewall Network Rules
10. Configure DNAT Rules
11. Deploy Windows Virtual Machines
12. Test RDP Connectivity
13. Verify Private VM Communication

---

# Project Outcome

- Centralized network security
- Secure VM communication
- No Public IP assigned to Virtual Machines
- Secure Remote Desktop through Azure Firewall