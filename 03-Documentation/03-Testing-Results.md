# Testing Results

## Test 1

RDP to VM1

Status

✅ Success

---

## Test 2

RDP to VM2

Status

✅ Success

---

## Test 3

Ping VM1 → VM2

Status

✅ Success

Private IP

10.2.1.4

---

## Test 4

Ping VM2 → VM1

Status

✅ Success

Private IP

10.1.1.4

---

## Test 5

Test-NetConnection

Port 3389

Status

✅ Success

---

## Test 6

Azure Firewall DNAT

Status

✅ Success

Port Mapping

8080 → 10.1.1.4:3389

8081 → 10.2.1.4:3389

---

# Validation

✔ Hub and Spoke connectivity verified

✔ Global VNet Peering working

✔ Azure Firewall inspecting traffic

✔ User Defined Routes working correctly

✔ Windows Virtual Machines communicating privately

✔ No Public IP assigned to Virtual Machines

✔ Secure RDP through Azure Firewall