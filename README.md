# Hands-On Experience

Documentation of my practical networking and cybersecurity work during SIWES and personal labs.

---

## Multi-Network Topology with Two Routers

### Overview
Configured two Cisco routers (2911) in Packet Tracer to interconnect multiple networks. Devices on different subnets communicate through the routers acting as default gateways.

### Topology Summary

**Router 1 (2911)**
- Connected to Access Point → 192.168.10.0/24 (wireless network with laptops)
- Connected to Switch (2960-24TT) → 192.168.20.0/24 (two PCs: PC1 and PC2)
- Point-to-point link to Router 2: 10.10.10.0/30

**Router 2 (2911)**
- Connected to Internal Server 0: 172.16.10.0/24
- Connected to Internal Server 1: 172.16.20.0/24
- Point-to-point link back to Router 1: 10.10.10.0/30

### What I Configured
- Assigned IP addresses to router interfaces using CLI
- Brought the interfaces up with `no shutdown`
- Set the router interface IPs as default gateways for the devices in each network
- Interconnected the two networks so devices can reach across routers

### Key Concepts Practiced
- Basic router interface configuration via CLI
- Using routers as default gateways
- Connecting different networks (LANs) through a point-to-point link
- Understanding subnetting (/24 and /30)

### Result
Devices on the 192.168.10.0/24 and 192.168.20.0/24 networks could communicate with each other and reach the servers on the Router 2 side through the interconnected routers.

---

*More labs and configurations will be added as I progress through SIWES and personal practice.*
