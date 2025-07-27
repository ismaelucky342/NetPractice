# NetPractice - TCP/IP Addressing & Subnetting

## Overview

**NetPractice** is a practical networking project that teaches fundamental TCP/IP concepts through hands-on exercises. This system administration project focuses on **IP addressing**, **subnetting**, **routing tables**, and network configuration. Through 10 progressive levels, you'll master the essential skills needed to configure and troubleshoot network infrastructure.

## Learning Objectives

- Understanding **IPv4 addressing** and network/host portions
- Mastering **subnet masks** and CIDR notation
- Configuring **routing tables** and next-hop addresses
- Working with **switches** and **routers** in network topologies
- Solving **network connectivity** problems systematically
- Applying **subnetting calculations** in real-world scenarios
- Understanding **private vs public IP ranges**

## Key Networking Concepts

### IP Addressing (IPv4)
An **IPv4 address** is a 32-bit number that uniquely identifies a device on a network. It consists of two parts:
- **Network portion**: Identifies the network segment
- **Host portion**: Identifies the specific device within that network

**Example**: `192.168.1.100/24`
- Network: `192.168.1.0`
- Host: `100`
- Subnet mask: `255.255.255.0` (/24)

### Subnet Masks and CIDR
**Subnet masks** determine which portion of an IP address represents the network and which represents the host:

| CIDR | Subnet Mask | Network Bits | Host Bits | Max Hosts |
|------|-------------|--------------|-----------|-----------|
| /24  | 255.255.255.0 | 24 | 8 | 254 |
| /25  | 255.255.255.128 | 25 | 7 | 126 |
| /26  | 255.255.255.192 | 26 | 6 | 62 |
| /27  | 255.255.255.224 | 27 | 5 | 30 |
| /28  | 255.255.255.240 | 28 | 4 | 14 |
| /29  | 255.255.255.248 | 29 | 3 | 6 |
| /30  | 255.255.255.252 | 30 | 2 | 2 |

### Private IP Ranges
Reserved for internal networks (RFC 1918):
- **Class A**: `10.0.0.0/8` (10.0.0.0 - 10.255.255.255)
- **Class B**: `172.16.0.0/12` (172.16.0.0 - 172.31.255.255)
- **Class C**: `192.168.0.0/16` (192.168.0.0 - 192.168.255.255)

### Routing Concepts
- **Default route**: `0.0.0.0/0` - matches all destinations
- **Next hop**: IP address of the next router in the path
- **Network address**: First address in a subnet (all host bits = 0)
- **Broadcast address**: Last address in a subnet (all host bits = 1)

## Project Structure

```
NetPractice/
├── Level_1/           # Basic IP assignment and subnet masks
├── Level_2/           # Subnetting with /30 networks
├── Level_3/           # Switch connectivity
├── Level_4/           # Basic routing introduction
├── Level_5/           # Default routes and next-hop
├── Level_6/           # Internet connectivity
├── Level_7/           # Complex routing scenarios
├── Level_8/           # Multiple router configurations
├── Level_9/           # Advanced subnetting challenges
├── Level_10/          # Complex multi-network topology
└── README.md          # This file
```

## Level-by-Level Solutions

### Level 1: Basic IP Assignment
**Problem**: Configure IP addresses for devices on the same network.

**Key Concepts**:
- Same network devices must share the same network portion
- Host portion must be unique for each device
- Cannot use network or broadcast addresses

**Solution Strategy**:
```
Network: 104.96.23.0/24
- Client A: 104.96.23.1 - 104.96.23.254 (excluding Client B's IP)
- Client B: 104.96.23.12 (given)
- Avoid: 104.96.23.0 (network), 104.96.23.255 (broadcast)
```

---

### Level 2: Subnetting Fundamentals
**Problem**: Work with different subnet masks (/27 and /30).

**Key Concepts**:
- `/27` = 255.255.255.224 (32 hosts per subnet)
- `/30` = 255.255.255.252 (2 hosts per subnet)
- Calculate valid host ranges

**Solution Strategy**:
```
/27 Network example:
- Subnet: 192.168.20.192/27
- Valid hosts: 192.168.20.193 - 192.168.20.222
- Network: 192.168.20.192, Broadcast: 192.168.20.223

/30 Network example:
- Only 2 valid host addresses available
- Perfect for point-to-point links
```

---

### Level 3: Switch Connectivity
**Problem**: Configure devices connected through a switch.

**Key Concepts**:
- Switches operate at Layer 2 (Data Link)
- All devices connected to a switch are on the same network
- Switch doesn't have an IP address

**Solution Strategy**:
- Ensure all connected devices use the same network address
- Apply consistent subnet mask across all interfaces
- Assign unique host addresses to each device

---

### Level 4: Introduction to Routing
**Problem**: First encounter with routing tables.

**Key Concepts**:
- Routing tables determine packet forwarding
- Next-hop must be reachable (same network as interface)
- Default route (0.0.0.0/0) as catch-all

**Solution Strategy**:
- Configure interface IP addresses on different subnets
- Set appropriate next-hop addresses in routing tables
- Ensure routing table entries match network topology

---

### Level 5: Default Routes and Next-Hop
**Problem**: Configure default routing for internet connectivity.

**Key Concepts**:
- Default route: `0.0.0.0/0` matches all destinations
- Next-hop must be on the same subnet as the outgoing interface
- Single default route per device

**Solution Strategy**:
```
Client A Configuration:
- Interface: 54.117.30.125/25
- Route destination: default (0.0.0.0/0)
- Next hop: 54.117.30.126 (router's interface)
```

---

### Level 6: Internet Connectivity
**Problem**: Connect internal networks to the internet.

**Key Concepts**:
- Internet gateway configuration
- Public vs private IP addressing
- NAT concepts (Network Address Translation)

**Solution Strategy**:
- Configure router interfaces for both internal and external networks
- Set up proper routing to internet gateway
- Ensure private networks route through configured gateways

---

### Level 7: Complex Routing Scenarios
**Problem**: Multiple networks with specific routing requirements.

**Key Concepts**:
- Specific route entries vs default routes
- Route precedence (longest prefix match)
- Multi-homed configurations

**Solution Strategy**:
- Analyze required connectivity paths
- Configure specific routes for internal networks
- Use default routes for external connectivity
- Ensure symmetric routing

---

### Level 8: Multiple Router Configuration
**Problem**: Configure routing between multiple routers.

**Key Concepts**:
- Router-to-router connectivity
- Transit networks (typically /30)
- Routing table consistency

**Solution Strategy**:
- Use /30 subnets for router-to-router links
- Configure routing tables on all routers
- Ensure end-to-end connectivity
- Verify no routing loops exist

---

### Level 9: Advanced Subnetting
**Problem**: Complex subnetting with overlapping requirements.

**Key Concepts**:
- VLSM (Variable Length Subnet Masking)
- Efficient IP address allocation
- Avoiding subnet overlap

**Solution Strategy**:
- Calculate required subnet sizes
- Allocate non-overlapping address ranges
- Use appropriate subnet masks for each network
- Verify all devices can communicate as required

---

### Level 10: Complete Network Topology
**Problem**: Design and configure a complete network infrastructure.

**Key Concepts**:
- Integration of all previous concepts
- End-to-end network design
- Scalable addressing scheme

**Solution Strategy**:
- Plan IP addressing scheme systematically
- Configure all devices with appropriate settings
- Implement comprehensive routing solution
- Test connectivity between all required endpoints

---

## Subnetting Calculation Method

### Step-by-Step Subnet Calculation

**Example**: Calculate subnets for `10.20.4.13/29`

1. **Find Subnet Bits**:
   ```
   /29 = 32 - 29 = 3 host bits
   Host bits = 3, Network bits = 29
   ```

2. **Calculate Subnet Size**:
   ```
   2^3 = 8 addresses per subnet
   Block size = 8
   ```

3. **Find Valid Host Range**:
   ```
   Usable hosts = 8 - 2 = 6
   (Subtract network and broadcast addresses)
   ```

4. **Determine Subnet Boundaries**:
   ```
   Subnet increments: 0, 8, 16, 24, 32...
   IP 10.20.4.13 falls in subnet 10.20.4.8/29
   ```

5. **Final Results**:
   ```
   Network address:    10.20.4.8/29
   First host:         10.20.4.9/29
   Last host:          10.20.4.14/29
   Broadcast address:  10.20.4.15/29
   ```

## Common Network Devices

### Switch
- **Function**: Connects devices within the same network (Layer 2)
- **Characteristics**: 
  - No IP address required
  - Forwards frames based on MAC addresses
  - All connected devices share the same broadcast domain

### Router
- **Function**: Connects different networks (Layer 3)
- **Characteristics**:
  - Has IP addresses on each interface
  - Routes packets based on IP addresses
  - Maintains routing tables for path determination
  - Separates broadcast domains

## Troubleshooting Network Issues

### Common Problems and Solutions

1. **Devices can't communicate**:
   - Verify IP addresses are on the same network
   - Check subnet mask consistency
   - Ensure no IP address conflicts

2. **No internet connectivity**:
   - Verify default route configuration
   - Check next-hop reachability
   - Confirm gateway settings

3. **Partial connectivity**:
   - Review routing table entries
   - Check for missing routes
   - Verify symmetric routing

4. **IP address conflicts**:
   - Ensure unique addresses within subnets
   - Avoid using network/broadcast addresses
   - Check DHCP vs static assignment conflicts

## Best Practices

### IP Address Planning
- Document all network assignments
- Use consistent subnetting schemes
- Reserve addresses for infrastructure
- Plan for future growth

### Routing Configuration
- Use specific routes when possible
- Minimize routing table entries
- Implement redundancy where needed
- Document route purposes

### Security Considerations
- Use private IP ranges for internal networks
- Implement proper access controls
- Monitor network traffic patterns
- Maintain configuration backups

## Useful Tools and Commands

### Network Calculation Tools
```bash
# Install IP calculator (macOS)
brew install ipcalc

# Example usage
ipcalc 192.168.1.0/24
```

### Verification Commands
```bash
# Check routing table
route -n
netstat -rn

# Test connectivity
ping <destination>
traceroute <destination>

# Network interface information
ifconfig
ip addr show
```

## Additional Resources

- **Subnet Calculator**: [Calculator.net IP Subnet Calculator](https://www.calculator.net/ip-subnet-calculator.html)
- **RFC 1918**: Private Internet Address Allocation
- **RFC 950**: Internet Standard Subnetting Procedure
- **Cisco Networking Basics**: Comprehensive networking guide

---

**NetPractice** provides hands-on experience with real-world networking scenarios. Master these concepts to build a solid foundation for system administration and network engineering roles.

---
-Born2code
![42madrid](https://github.com/ismaelucky342/Born2code/assets/153450550/3a377f34-9156-4eff-b04b-71c4b128523e)
