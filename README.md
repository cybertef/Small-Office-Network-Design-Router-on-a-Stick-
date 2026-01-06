# Small Office Network Design-(Router on a Stick)
A very basic design and configuration of a small office network using VLANs and ROAS for inter-VLAN routing. The network is designed to support multiple departments with proper IP addressing, traffic segmentation, and basic security considerations. Implemented using Cisco Packet Tracer to validate network logic, connectivity, and configuration.

Network Objectives
- Segment the network into multiple VLANs by department
- Implement inter-VLAN routing using a single router interface
- Apply structured IP addressing using VLSM
- Provide a scalable design suitable for a small office environment
- Maintain a clean and readable network topology
 
VLAN Design
| VLAN ID | Department | Purpose |
|-------|-----------|--------|
| 10 | Sales | Sales and operations |
| 20 | Admin | Administrative systems |
| 30 | HR | Human resources systems |
| 40 | IT | IT support and management |

IP Addressing
The network uses the private address block 192.168.10.0/24, subnetted using VLSM to meet departmental host requirements.

Each VLAN is assigned a dedicated subnet, and the default gateway for each VLAN is configured on a router subinterface.

Detailed IP information is available in the 'ip-addressing table' down below.

Inter-VLAN Routing
Inter-VLAN routing is implemented using Router-on-a-Stick:
- A single router interface is configured with multiple subinterfaces
- Each subinterface is associated with a VLAN using IEEE 802.1Q encapsulation
- The router serves as the default gateway for all VLANs
- Switch Configuration
VLANs were created and assigned to access ports based on department. Trunk links were configured between switches and between the switch and router to carry multiple VLANs using IEEE 802.1Q.

Topology Notes
- For clarity and simplicity, a limited number of end devices (PCs and printers) are deployed per VLAN in the Packet Tracer simulation
- The IP addressing plan and subnet sizes reflect the intended full network capacity, not just the simulated endpoints
- VLAN trunking is used between switches and the router

Skills Demonstrated
- VLAN configuration and segmentation
- Router-on-a-Stick inter-VLAN routing
- IP subnetting and VLSM
- Basic network design principles
- Network documentation and planning

Future Improvements
- Implement DHCP for dynamic IP allocation
- Apply access control lists (ACLs) for inter-VLAN security
- Add redundancy and observe STP behavior
- Expand the topology with wireless access

 Author
Cybertef  
(Network Support Engineer in Training)


 IP Addressing Plan

| VLAN ID | VLAN Name | Network Address | Subnet Mask       | Default Gateway | Device Range           |
|--------|-----------|-----------------|-------------------|-----------------|------------------------|
| 10     | Sales     | 192.168.10.0/27 | 255.255.255.224   | 192.168.10.1    | 192.168.10.2  - .30    |
| 20     | HR        | 192.168.10.32/28| 255.255.255.240   | 192.168.20.33   | 192.168.10.34 - .46    |
| 30     | Sales     | 192.168.10.48/28| 255.255.255.240   | 192.168.30.49   | 192.168.10.50 - .62    |
| 40     | IT        | 192.168.10.64/28| 255.255.255.240   | 192.168.40.65   | 192.168.40.66 - .78    |
