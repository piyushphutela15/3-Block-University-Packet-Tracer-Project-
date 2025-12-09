# Packet Tracer Lab Steps - Build Guide (Quick)

1. Place devices:
   - 1 x Core Layer-3 switch (e.g., 3560/3850)
   - 3 x Distribution switches (3560)
   - 6-9 x Access switches (2960) — split across blocks/floors
   - 1 x Edge router (1941)
   - 1 x Wireless LAN Controller (if available in Packet Tracer) + APs
   - 1-2 x Server (Generic Server) for DHCP/DNS
   - Several PCs for testing

2. Cable devices:
   - Core <-> Dist: two Gig links each (use GigabitEthernet). Configure as trunk and then bundle with EtherChannel (LACP).
   - Dist <-> Access: trunk links.
   - Access <-> PC: copper straight-through, access ports.

3. Create VLANs on all switches (10,20,30,40,50,60).
   - Example: VLAN 10 management, 20 student, 30 staff, 40 admin, 50 wireless, 60 voice

4. Core switch:
   - Enable `ip routing`
   - Create SVIs for VLANs (ip addresses as per README)
   - Configure trunk ports and Port-channels to Distribution

5. Distribution switches:
   - Configure trunk ports toward Core and Access
   - Configure `channel-group` for EtherChannel to Core if using aggregated links

6. Access switches:
   - Configure access ports for PCs (switchport mode access; switchport access vlan X)
   - Enable `spanning-tree portfast` and `bpduguard` on access ports
   - Enable port-security if desired

7. Router (Edge):
   - Configure interface toward Core with public/transit IP
   - Configure NAT if you want internet for PCs (NAT overload)

8. Servers:
   - Configure DHCP pools for each VLAN (default-router set to SVI)
   - Configure DNS records for key hosts

9. Wireless:
   - Configure SSIDs on WLC and map to VLANs (StudentWiFi->VLAN50 etc.)
   - Place APs and connect to switches

10. Verification:
   - From PCs: obtain DHCP lease, ping SVI/gateway, ping other VLANs (if ACLs allow), test WiFi connectivity

Troubleshooting commands: `show ip interface brief`, `show vlan brief`, `show interfaces trunk`, `show spanning-tree`, `show etherchannel summary`, `show running-config`, `show ip route`.
