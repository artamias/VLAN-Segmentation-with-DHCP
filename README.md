## This project simulates enterprise network segmentation using VLAN, DHCP server, trunk and access port configuration.


## Network Topology Diagram

<img width="663" height="769" alt="image" src="https://github.com/user-attachments/assets/ba7c4c61-7c1a-4fc5-8bcb-92cba606ce0b" />

## IP Addressing Table

| Device        | Interface | USED   | IP Address        | Description              |
|--------------|------------|--------|-------------------|--------------------------|
| MikroTik     | ether1     | WAN    | 192.168.65.130/24 | Internet Access          |
| MikroTik     | ether2     | LAN    | 192.168.65.130/24 | Internet Access          |
| MikroTik     | Vlan10     | VLAN   | 192.168.2.1/24    | Gateway VLAN 10          |
| MikroTik     | Vlan20     | VLAN   | 192.168.3.1/24    | Gateway VLAN 20          |
| Cisco Switch | e0/0       | TRUNK  | -                 | Trunk to MikroTik        |
| Cisco Switch | e0/1       | ACCESS | -                 | Access VLAN 10           |
| Cisco Switch | e0/2       | ACCESS | -                 | Access VLAN 20           |
| PC Ops       | eth0       | VLAN   | DHCP              | Client VLAN 10           |
| PC Cust      | eth0       | VLAN   | DHCP              | Client VLAN 20           |

## VLAN Mapping

| VLAN ID | VLAN Name    | Network Address    | Gateway          | DHCP Range                   |
|---------|--------------|--------------------|------------------|------------------------------|
| 10      | OPERASIONAL  | 192.168.2.0/24     | 192.168.2.1      | 192.168.2.2 – 192.168.2.254  |
| 20      | CUSTOMER     | 192.168.3.0/24     | 192.168.3.1      | 192.168.3.2 – 192.168.3.254  |


Goals:
- Separate operational and customer network
- Implement VLAN trunking
- Provide DHCP per VLAN
- Enable inter-VLAN routing via MikroTik
- Secure network with firewall rules

Testing Results:

- Switch succes VLAN Configuration
<img width="1017" height="226" alt="image" src="https://github.com/user-attachments/assets/dab655af-d368-4df3-a6c1-a939dc9f8957" />

- Switch success TRUNK and ACCESS configuration
<img width="942" height="141" alt="image" src="https://github.com/user-attachments/assets/d227dce7-2974-4544-8795-11be8a2385b4" />

- PC VLAN10 successfully received IP via DHCP
<img width="505" height="72" alt="image" src="https://github.com/user-attachments/assets/8d67d398-89f0-4ff3-b536-5ba13df33c33" />

- PC VLAN20 successfully received IP via DHCP
<img width="511" height="68" alt="image" src="https://github.com/user-attachments/assets/b1ac26da-219b-4da2-99b2-e288151458e4" />

- Both VLANs can access internet
<img width="812" height="148" alt="image" src="https://github.com/user-attachments/assets/7f01ce46-0159-4bfb-9522-f14836c9e285" />

- VLAN20 cannot access VLAN10 (firewall working)
<img width="413" height="125" alt="image" src="https://github.com/user-attachments/assets/575fe1e6-923b-471e-9a49-6855e5a1a3c1" />

- Inter-VLAN routing tested via ping gateway
<img width="736" height="223" alt="image" src="https://github.com/user-attachments/assets/0013c01a-2a67-4377-b301-0ea89dd7ae01" />

