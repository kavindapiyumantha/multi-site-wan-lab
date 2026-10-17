# Small Office Network Architecture & Configuration

**Status: In progress — configuration templates prepared; Packet Tracer implementation and testing pending.**

An educational Cisco Packet Tracer project to design and configure a small office network with department VLANs, router-on-a-stick inter-VLAN routing, and DHCP. Security controls and simulated internet connectivity are planned extensions.

This Packet Tracer lab is separate from the repository's GNS3 multi-site WAN lab.

## Equipment
- 1 Cisco 2911 router: R1
- 1 Cisco 2960 switch: SW1
- 6 PCs: two each for Admin, IT, and Sales
- Copper straight-through cables

## Addressing

| Department | VLAN | Subnet | Gateway |
|---|---|---|---|
| Admin | 10 | 192.168.10.0/24 | 192.168.10.1 |
| IT | 20 | 192.168.20.0/24 | 192.168.20.1 |
| Sales | 30 | 192.168.30.0/24 | 192.168.30.1 |

Addresses .1–.20 in each subnet are reserved; the remaining usable addresses are available through DHCP.

## Connections

| Device port | SW1 port |
|---|---|
| R1 Gi0/0 | Gi0/1 (trunk) |
| Admin-PC1 Fa0 | Fa0/1 |
| Admin-PC2 Fa0 | Fa0/2 |
| IT-PC1 Fa0 | Fa0/3 |
| IT-PC2 Fa0 | Fa0/4 |
| Sales-PC1 Fa0 | Fa0/5 |
| Sales-PC2 Fa0 | Fa0/6 |

## Build instructions
1. Place and cable the listed devices in Packet Tracer.
2. Open each network device's CLI. Decline the initial configuration dialog if prompted.
3. Paste [SW1 configuration](configs/SW1.txt) into the switch and [R1 configuration](configs/R1.txt) into the router, starting from the user EXEC prompt.
4. Press Enter when asked to accept the startup configuration filename.
5. On every PC, choose **Desktop → IP Configuration → DHCP**.
6. Complete the checks below.
7. Save the topology as `Small_Office_Network.pkt` and upload it to this folder.

## Validation checklist
These checks have not yet been performed in Packet Tracer.

- [ ] `show vlan brief` on SW1 shows the correct access ports.
- [ ] `show interfaces trunk` on SW1 shows Gi0/1 carrying VLANs 10,20,30.
- [ ] `show ip interface brief` on R1 shows Gi0/0 and its subinterfaces up/up.
- [ ] `show ip dhcp binding` on R1 shows the PC leases.
- [ ] Each PC receives the correct subnet mask, address, and gateway.
- [ ] Each PC can ping its gateway.
- [ ] PCs in the same VLAN can ping each other.
- [ ] PCs in different VLANs can ping each other.
- [ ] Save, reopen, and verify the Packet Tracer project.

Use `ipconfig` on each PC to identify its assigned address before testing. An initial ping can time out while ARP resolves; repeat it.

## Security scope
The initial configuration permits communication between all three departments. VLANs separate broadcast domains; they do not prevent routed access. This baseline is not a completed secure deployment.

Planned extensions:
- [ ] ACLs with a documented department access policy
- [ ] SSH management
- [ ] Switch port security
- [ ] Shutdown of unused switch ports
- [ ] ISP simulation, default route, and NAT/PAT
- [ ] Positive and negative tests for access restrictions

## Evidence to add
- `Small_Office_Network.pkt`
- Topology screenshot
- DHCP and VLAN verification screenshots
- Ping results, including expected blocked traffic after ACLs are added

No completed simulation or successful test results are claimed until evidence is added.
