| Cisco command | FortiGate equivalent | Notes |
|---|---|---|
| `show ip interface brief` | `get system interface` | Interface information, including configured IPv4 addresses. |
| `show ip interface brief \| exclude unassigned` | `get system interface \| grep -v "ip: 0.0.0.0"` | Approximate equivalent: filters out lines showing no IPv4 address. |
| `show ipv6 interface brief` | `diagnose ipv6 address list` | Lists IPv6 addresses and their interfaces. |
| `show vlan brief` | `show system interface` | Look for `set vlanid` and the parent `set interface`. There is no identical Cisco-style VLAN summary. |
| `show running-config` | `show` | Displays configuration excluding most default settings. Use `show full-configuration` to include defaults. |
| `show startup-config` | No direct equivalent | FortiGate normally saves configuration automatically. |
| `copy running-config startup-config` | Usually unnecessary; `execute cfg save` for manual/revert save modes | See the saving explanation below. |
| `show mac address-table` | `diagnose netlink brctl name host <bridge-name>` | Shows a bridge’s learned MAC addresses; depends on switch/bridge configuration. |
| `show ip dhcp binding` | `execute dhcp lease-list` | Shows leases issued by the FortiGate DHCP server. |
| `show interfaces` | `diagnose netlink interface list` | Runtime interface details and counters. |
| `show interface Port-channel1` | `diagnose netlink aggregate name <aggregate-name>` | Shows the corresponding aggregate interface’s status and members. |
