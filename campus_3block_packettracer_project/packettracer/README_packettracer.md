# Packet Tracer Notes

Packet Tracer cannot import raw CLI files directly as device configs in batch; you must paste each CLI into the device's terminal in Packet Tracer.
Recommended workflow:
- Add the intended device (e.g., 3560 switch), open its CLI, and paste the corresponding file from `configs/`.
- For servers: use Packet Tracer 'Server' device and configure DHCP/DNS using the GUI; the `servers/` folder contains text-based examples for real servers.
