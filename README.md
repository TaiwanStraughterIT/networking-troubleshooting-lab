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

## Screenshots and evidence

Once the screenshots are uploaded to the `screenshots/` folder, these links will open each step:

1. [Network topology](screenshots/01-network-topology.png)
2. [VLAN configuration](screenshots/02-vlan-configuration.png)
3. [PC IP configuration](screenshots/03-pc-ip-configuration.png)
4. [Switch trunk configuration](screenshots/04-switch-trunk-configuration.png)
5. [Router subinterfaces](screenshots/05-router-subinterfaces.png)
6. [VLAN 10 connectivity test](screenshots/06-vlan10-connectivity-test.png)
7. [Inter-VLAN connectivity](screenshots/07-inter-vlan-connectivity.png)
8. [Failed ping — incorrect gateway](screenshots/08-network-troubleshooting-failed-ping.png)
9. [Connectivity restored — gateway fix](screenshots/09-network-connectivity-restored.png)
10. [Incorrect VLAN assignment](screenshots/10-vlan-misconfiguration.png)
11. [Corrected VLAN assignment](screenshots/11-vlan-misconfiguration-fixed.png)
12. [VLAN connectivity restored](screenshots/12-vlan-connectivity-restored.png)

## Project files (upload pending)

- `Office-Network-Troubleshooting.pkt` — Cisco Packet Tracer project.
- `screenshots/` — 12 numbered screenshots.
- `Networking_Troubleshooting_Lab_Report.docx` — illustrated Word report with descriptions.

## Skills demonstrated
VLAN segmentation · IPv4 addressing · Router-on-a-Stick · 802.1Q trunking · Cisco CLI · ICMP testing · Network troubleshooting · Technical documentation

> This is a simulated educational lab created in Cisco Packet Tracer, not a production deployment.
