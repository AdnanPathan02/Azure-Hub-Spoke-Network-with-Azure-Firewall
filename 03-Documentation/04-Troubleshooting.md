# Troubleshooting Guide

## Problem 1

VM1 cannot communicate with VM2.

Possible Causes

- VNet Peering missing
- Route Table not associated
- Azure Firewall Network Rule missing

Solution

- Verify VNet Peering
- Verify User Defined Routes
- Verify Firewall Network Rules

---

## Problem 2

RDP not working.

Possible Causes

- DNAT Rule missing
- Windows Firewall blocking RDP
- Network Security Group blocking TCP 3389

Solution

- Verify DNAT Rules
- Enable Remote Desktop
- Allow TCP 3389 in Windows Firewall
- Verify NSG Rules

---

## Problem 3

Ping failed.

Possible Causes

- ICMP blocked by Windows Firewall
- Route Table configuration issue

Solution

- Enable File and Printer Sharing (Echo Request - ICMPv4-In)
- Verify Azure Firewall Network Rules
- Verify UDR configuration

---

## Problem 4

Global VNet Peering not working.

Possible Causes

- Incorrect Peering configuration
- Different Address Spaces overlapping

Solution

- Verify both Peerings
- Verify Address Spaces
- Confirm "Allow forwarded traffic" is enabled where required

---

# Best Practices

- Avoid assigning Public IP addresses directly to Virtual Machines.
- Use Azure Firewall as the centralized security appliance.
- Use User Defined Routes to force traffic through Azure Firewall.
- Restrict RDP access using DNAT Rules.
- Monitor Firewall logs using Azure Monitor and Log Analytics.