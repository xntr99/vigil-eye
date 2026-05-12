# Bill Of Materials

This bill of materials captures the device choices from the design and converts them into a GitHub-readable engineering inventory. Costs are intentionally kept as planning estimates rather than dated procurement values.

## Device Inventory

| Qty | Device | Role | Key Capabilities |
| --- | --- | --- | --- |
| 1 | Ubiquiti Dream Router | Main gateway | 1 Gbps networking, Wi-Fi 6, PoE ports, VLAN support, firewall, VPN options, application-aware controls. |
| 1 | Ubiquiti airMAX NanoStation 5AC | Main wireless bridge | 5 GHz bridge, 15+ km rated link range, high-gain antenna, PoE support. |
| 2 | Ubiquiti PowerBeam AC | Bridge stations | PtMP support, high-gain directional link, outdoor mounting, PoE. |
| 1 | Hikvision DS-7616NXI-K2/16P | NVR | 16 IP camera inputs, ONVIF support, up to 160 Mbps incoming bandwidth, SATA storage bays. |
| 5 | Linksys WHW0301 | Mesh nodes | Wi-Fi mesh, WPA2/WPA3 support, Gigabit ports, app/browser setup. |
| 8 | Hikvision DS-2CD1023G0-IU(F) | Bullet IP cameras | 2 MP video, H.265/H.264, ONVIF, PoE, IP67, IR, motion and tamper detection. |
| 4 | Hikvision HWI-D140H | Dome IP cameras | 4 MP video, wide field of view, H.265/H.264, ONVIF, smart detection, PoE. |

## Compatibility Notes

| Area | Compatibility Requirement |
| --- | --- |
| Camera to NVR | ONVIF Profile S/G or native Hikvision protocol. |
| Video transport | RTSP/RTP support for stream compatibility. |
| Management | HTTPS preferred, HTTP disabled where possible. |
| Wireless | WPA2 minimum; WPA3 preferred where all devices support it. |
| Monitoring | SNMP where supported; otherwise use device-native logs and health checks. |
| Power | PoE support for cameras and bridge devices where available. |
| Segmentation | VLAN support at the gateway and switching layer. |

## Procurement Guidance

- Confirm local availability and warranty before purchase.
- Confirm firmware support windows for all camera and NVR models.
- Prefer devices that expose logs, SNMP, HTTPS, ONVIF, and secure credential handling.
- Budget for mounting hardware, weatherproof boxes, UPS, cabling, labels, conduit, and surge protection.
- Treat storage drives as separate line items; surveillance-rated drives are preferred.
- Keep spare mounts, PoE injectors, patch cables, and at least one spare camera for rapid replacement.

## Upgrade Options

| Upgrade | Why It Helps |
| --- | --- |
| Layer 3 switch | Cleaner VLAN routing and future expansion. |
| Dual ISP | Remote access resilience and alert continuity. |
| UPS and surge protection | Protects recording continuity during power instability. |
| RAID storage | Protects recordings from single-drive failure. |
| SIEM integration | Improves detection of unauthorized access and outages. |
| Central dashboard | Simplifies operations across multiple vendor devices. |

