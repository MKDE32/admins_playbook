# VMware Network Modes Cheat Sheet (Workstation / Player)

| Mode            | Internet Access | Host Access | LAN Access | VM-to-VM | Use Case |
|-----------------|----------------|-------------|------------|----------|----------|
| NAT (VMnet8)    | Yes            | Yes         | No         | Yes      | Default, VMs share host internet |
| Bridged (VMnet0)| Yes            | Yes         | Yes        | Yes      | VM acts like real machine on LAN |
| Host-Only (VMnet1)| No           | Yes         | No         | Yes      | Isolated lab with host access |
| Custom (VMnetX) | Depends        | Depends     | Depends    | Yes      | Advanced setups with manual config |
| LAN Segment     | No             | No          | No         | Yes      | Fully isolated VM network (like internal net) |

---

## Notes

- NAT (VMnet8):
  - VMs can access internet via host
  - VMs can communicate with each other
  - Not directly reachable from external network

- Bridged (VMnet0):
  - VM gets IP from real network (DHCP)
  - Visible to other devices
  - Can be affected by WiFi/VPN restrictions

- Host-Only (VMnet1):
  - Only communication between host and VMs
  - No internet by default

- Custom (VMnetX):
  - Manually configured networks
  - Can behave like NAT, Host-Only, or isolated

- LAN Segment:
  - Fully isolated network
  - No host, no internet
  - Ideal for malware labs / pentesting

---

## Quick Recommendations

- Basic usage: NAT (VMnet8)
- Multi-VM lab with internet: NAT
- Real network testing: Bridged
- Controlled lab with host access: Host-Only
- Fully isolated lab: LAN Segment
