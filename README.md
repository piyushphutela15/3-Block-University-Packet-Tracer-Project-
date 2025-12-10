Campus Network Design — 3-Block University (Packet Tracer Project)
This package contains configuration files, server configs, lab steps, and a simple topology image to help you build a Cisco Packet Tracer project for a 3-block university campus network.

What's included

configs/ - CLI configuration snippets for devices (core, distribution, access, edge router, WLC).
servers/ - Example dhcpd.conf and named.conf snippets for DHCP/DNS.
lab_steps.md - Step-by-step Packet Tracer build instructions.
topology.png - Simple topology diagram (placeholder). Replace with a detailed diagram if you wish.
packettracer/README_packettracer.md - Notes for how to import configs into Packet Tracer.
How to use

Open Cisco Packet Tracer (recommended version: 8.x — include the actual version you are using in your GitHub README).
Add devices matching the topology: 1 Core L3 switch, 3 Distribution switches, several Access switches, Router (Edge), Wireless LAN Controller (or simulated WLC), APs, Servers, PCs.
Use the CLI config files in configs/ as templates: copy/paste into device CLI (enable mode) then save running-config to startup-config.
Configure the Packet Tracer Server DHCP/DNS using the servers/dhcpd.conf and servers/named.conf examples as guidance if you replicate on a real server.
Follow lab_steps.md to wire devices, configure VLANs, trunking, SVIs, EtherChannel, STP, DHCP, and WLC mappings.
If you want, I can produce more specific Packet Tracer instructions (exact cable types, port numbers, and a fully automated .pkt file).
