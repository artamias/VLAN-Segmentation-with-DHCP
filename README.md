This project simulates enterprise network segmentation using VLAN, DHCP server, trunk and access port configuration.

Goals:
- Separate operational and customer network
- Implement VLAN trunking
- Provide DHCP per VLAN
- Enable inter-VLAN routing via MikroTik
- Secure network with firewall rules

Testing Results:

- PC VLAN10 successfully received IP via DHCP
- PC VLAN20 successfully received IP via DHCP
- Both VLANs can access internet
- VLAN20 cannot access VLAN10 (firewall working)
- Inter-VLAN routing tested via ping gateway

<img width="663" height="769" alt="image" src="https://github.com/user-attachments/assets/ba7c4c61-7c1a-4fc5-8bcb-92cba606ce0b" />
