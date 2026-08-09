# Hands-On Experience

Documentation of my practical networking and cybersecurity work during SIWES and personal labs.

---

## 1. Multi-Network Topology with Two Routers (Static Routing)

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

## 2. DHCP + Default Routing (SIWES Update)

### Overview
Extended the previous multi-router lab by implementing DHCP for automatic IP assignment and default routing for simpler traffic forwarding.

### What I Configured

**DHCP**
- Created IP pools on the routers
- Configured DHCP services so end devices (PCs and laptops) automatically receive IP addresses, subnet masks, and default gateways

**Default Routing**
- Used the command:
  ```
  ip route 0.0.0.0 0.0.0.0 <next-hop-ip>
  ```
- This sets a default route so the router forwards traffic for any unknown destination to the specified next-hop (usually the other router or exit interface)

### Key Concepts Practiced
- DHCP pool configuration and IP address assignment
- Default routes (`0.0.0.0/0`) vs specific static routes
- How routers use the default route when no more specific match exists in the routing table
- Practical difference between static routing and default routing in small topologies

### Result
End devices now receive their IP configuration automatically via DHCP instead of manual static assignment. Routers can forward traffic to unknown networks using the default route, simplifying the configuration compared to writing individual static routes for every network.

---

*More labs and configurations will be added as I progress through SIWES and personal practice.*
