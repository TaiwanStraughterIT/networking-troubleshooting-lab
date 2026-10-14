# Networking & Connectivity Troubleshooting Lab

**Platform:** Cisco Packet Tracer  
**Focus:** IT Support / Network Technician fundamentals  
**Project type:** Simulated office network and troubleshooting exercises

## Project overview
Built a small office network with a Cisco 2911 router, Cisco 2960 switch, and four PCs. Segmented the network into IT Support and HR VLANs, configured router-on-a-stick inter-VLAN routing, and practiced troubleshooting common connectivity faults.

## Network addressing

| Department | VLAN | Devices | Network | Gateway |
|---|---:|---|---|---|
| IT Support | 10 | PC0: `192.168.10.10`, PC1: `192.168.10.11` | `192.168.10.0/24` | `192.168.10.1` |
| HR | 20 | PC2: `192.168.20.10`, PC3: `192.168.20.11` | `192.168.20.0/24` | `192.168.20.1` |

## Configuration performed

- Created VLAN 10 (`IT-Support`) and VLAN 20 (`HR-Department`).
- Assigned switch access ports Fa0/1–2 to VLAN 10 and Fa0/3–4 to VLAN 20.
- Configured switch Gi0/1 as an 802.1Q trunk carrying VLANs 10 and 20.
- Configured router Gi0/0.10 (`192.168.10.1/24`) and Gi0/0.20 (`192.168.20.1/24`) with 802.1Q encapsulation.
- Assigned static IPv4 addresses and default gateways to four PCs.
- Used `ping`, `show vlan brief`, `show interfaces trunk`, and `show ip interface brief` for verification and troubleshooting.

## Troubleshooting scenarios

### Scenario 1: Incorrect default gateway
**Symptom:** A PC could not reach a host on another VLAN.  
**Fault introduced:** PC2's gateway was changed to `192.168.20.254`.  
**Diagnosis:** Checked the host IP settings and tested connectivity with `ping`.  
**Resolution:** Restored the gateway to `192.168.20.1` and retested.

### Scenario 2: Incorrect VLAN assignment
**Symptom:** An IT PC could not communicate as expected with its department's network.  
**Fault introduced:** Switch Fa0/2 (PC1) was moved from VLAN 10 to VLAN 20.  
**Diagnosis:** Used `show vlan brief` to inspect port membership.  
**Resolution:** Reassigned Fa0/2 to VLAN 10 and retested connectivity.

## Project deliverables

- **[Open the illustrated lab report](Networking_Troubleshooting_Lab_Report.docx)** — Word document with 12 labeled screenshots and descriptions of the network setup, testing, and troubleshooting.
- **[Download the Packet Tracer project](Office-Network-Troubleshooting.pkt)** — open the working topology and device configurations in Cisco Packet Tracer.

### Screenshot guide
The illustrated Word report contains these 12 pieces of evidence:

| # | Evidence | What it demonstrates |
|---|---|---|
| 01 | Network topology | Router, switch, and four-PC office layout |
| 02 | VLAN configuration | Department-based network segmentation |
| 03 | PC IP configuration | Static IPv4 addressing and default gateway |
| 04 | Switch trunk configuration | 802.1Q trunk verification |
| 05 | Router subinterfaces | Router-on-a-stick interfaces and IPs |
| 06 | VLAN 10 connectivity | Same-VLAN ICMP testing |
| 07 | Inter-VLAN connectivity | Routing between IT and HR |
| 08 | Failed ping | Incorrect default gateway symptom |
| 09 | Connectivity restored | Corrected default gateway |
| 10 | VLAN misconfiguration | Wrong switch access VLAN diagnosis |
| 11 | VLAN correction | Restored port to VLAN 10 |
| 12 | Connectivity restored | Verification after VLAN fix |

## Skills demonstrated
VLAN segmentation · IPv4 addressing · Router-on-a-Stick · 802.1Q trunking · Cisco CLI · ICMP testing · Network troubleshooting · Technical documentation

> This is a simulated educational lab created in Cisco Packet Tracer, not a production deployment.
