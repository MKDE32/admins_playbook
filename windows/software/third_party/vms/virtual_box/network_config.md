# VirtualBox Network Modes Cheat Sheet

| Mode            | Internet Access | Host Access | LAN Access | VM-to-VM | Use Case |
|-----------------|----------------|-------------|------------|----------|----------|
| NAT             | Yes            | Limited     | No         | No       | Default, simple internet access |
| NAT Network     | Yes            | Limited     | No         | Yes      | Multiple VMs with internal network + internet |
| Bridged Adapter | Yes            | Yes         | Yes        | Yes      | VM behaves like real machine on LAN |
| Host-Only       | No             | Yes         | No         | Yes      | Isolated lab between host and VMs |
| Internal Network| No             | No          | No         | Yes      | Fully isolated VM network (lab/testing) |
| Generic Driver  | Depends        | Depends     | Depends    | Depends  | Advanced/custom setups |


# Notes

- NAT:
  - Easiest setup
  - Outbound only (no inbound unless port forwarding)

- NAT Network:
  - Like NAT but allows VM-to-VM communication
  - Good for multi-VM labs with internet

- Bridged:
  - VM gets IP from real network
  - Visible to other devices (like a physical machine)

- Host-Only:
  - Communication only between host and VMs
  - No internet by default

- Internal Network:
  - Completely isolated
  - No host access

- Generic Driver:
  - Rarely used
  - For special drivers (UDP Tunnel, VDE, etc.)

