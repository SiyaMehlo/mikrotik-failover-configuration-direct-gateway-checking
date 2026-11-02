# mikrotik-failover-configuration-direct-gateway-checking
Failover Configuration (Direct Gateway Checking)
# Project Overview
This repository contains the configuration and documentation for implementing **Direct Gateway Checking** (standard ICMP ping-based link monitoring) on a MikroTik RouterOS device. This lab demonstrates how to set up an active/backup dual-WAN failover topology where the router monitors its immediate next-hop ISP gateways to automatically reroute traffic during an outage.

---

# Configuration Architecture

The setup utilizes two static default routes with distinct distance metrics and built-in health checking:

* **Primary Link (`Zynolinx` - Gateway: `192.168.244.2`)**
  * **Distance:** `1` (Preferred active path)
  * **Health Check:** `check-gateway=ping` (Actively pings the immediate ISP gateway)
* **Secondary Link (`Ten74 Telecoms` - Gateway: `192.168.42.1`)**
  * **Distance:** `2` (Automatic standby backup path)

---
