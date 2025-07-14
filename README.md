# MPLS-Dual-Wan-Lab

# Multi-Site MPLS and Internet Lab – README

## 📘 Overview
This lab project simulates a multi-site enterprise network connected through two paths: MPLS backbone and public Internet. It demonstrates BGP peering across autonomous systems, dynamic routing with OSPF, GRE tunneling for extended communication, and MPLS label forwarding — showcasing redundancy, segmentation, and service provider-grade infrastructure.

## 🏗 Topology Summary
The environment includes two major sites (Site A and Site B), each with internal routers and VPCs. Connectivity is provided via:

- A simulated **MPLS cloud** with Provider Edge (PE) and Provider (P) routers.
- A routed **Internet segment** via ISPs and edge routers.
- A **GRE tunnel over the Internet** between sites to ensure multicast compatibility and secure encapsulation of internal traffic.

Routing protocols:
- **BGP AS 5** connects Site A to MPLS edge
- **BGP AS 100** handles MPLS core transit
- **BGP AS 10** connects Site B to MPLS edge
- **OSPF** used internally for each site’s routing

## ⚙️ Key Components
- **Site A Routers**: R5 and R4  
- **MPLS Backbone**: R10 (PE), R11 (P), R12 (PE)  
- **Site B Routers**: R6 and R7  
- **Internet Path**: ISP-1, ISP-3, Transit Router  
- **GRE Tunnel**: Configured over Internet segment between Site A and Site B to support encapsulated traffic with routing protocol payload

## 🚧 Configuration Highlights
- BGP neighbor relationships are built between CE and PE routers across sites
- MPLS label distribution configured via LDP across R10 ↔ R11 ↔ R12
- GRE tunnel applied over Internet link for secure and flexible site-to-site routing
- Dual access for Site A and Site B: MPLS via PE routers and Internet via ISP routers
- OSPF used within Site A and Site B for internal connectivity
- Simulated traffic failover tested between MPLS and Internet paths

## ✅ Achievements
- Verified end-to-end connectivity between VPCs at Site A and Site B through both MPLS and GRE-enabled Internet routes
- Established route redistribution between BGP and OSPF with controlled propagation
- Demonstrated failover between Internet and MPLS backbone
- Enhanced understanding of multi-protocol integration, inter-AS communication, and tunneling techniques for real-world enterprise use

## 📎 Use Case
practicing real-world ISP infrastructure scenarios, CCNP/CCIE studies, and validating routing behaviors under multi-path environments.
