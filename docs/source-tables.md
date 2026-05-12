# Source Tables

This file rebuilds the most useful tables from the PDF into Markdown so the repo has searchable technical data instead of only screenshots.

## Device Inventory And Roles

| Qty | Device | Network Role | Reason For Inclusion |
| --- | --- | --- | --- |
| 1 | Ubiquiti Dream Router | Core gateway, firewall, VLAN, VPN, and local routing | Compact gateway with VLAN, VPN, PoE, and management features. |
| 1 | Ubiquiti airMAX NanoStation 5AC | Main point-to-multipoint wireless bridge | Long-distance bridge layer for backhaul stability. |
| 2 | Ubiquiti PowerBeam AC | Wireless bridge stations | Directional bridge endpoints for stable wireless transport. |
| 1 | Hikvision DS-7616NXI-K2/16P | Network video recorder | Central recording, playback, and camera management. |
| 5 | Linksys WHW0301 | Mesh nodes | Local wireless coverage and path redundancy. |
| 8 | Hikvision DS-2CD1023G0-IU(F) | Bullet IP cameras | Roadway and long-view surveillance. |
| 4 | Hikvision HWI-D140H | Dome IP cameras | Wider-angle intersection and public-area coverage. |

## Protocol And Compatibility Matrix

| Area | Required Capability |
| --- | --- |
| Camera interoperability | ONVIF Profile S/G or compatible native NVR integration. |
| Video streaming | RTSP/RTP support. |
| Wireless security | WPA2 minimum; WPA3 where all devices support it. |
| Secure management | HTTPS and strong credentials. |
| Remote access | VPN rather than direct public NVR exposure. |
| Monitoring | SNMP, logs, uptime checks, link-health monitoring, and storage alerts. |
| Network segmentation | VLANs and ACLs for camera, management, core, and partner access. |

## IP Addressing Table

| Device | Interface Or Role | Address | Subnet Mask | Range |
| --- | --- | --- | --- | --- |
| Site Router | `G0/0` | `192.168.1.1` | `255.255.255.0` | `192.168.1.0 - 192.168.1.254` |
| Site Router | `G0/1` | `192.168.2.1` | `255.255.255.0` | `192.168.2.0 - 192.168.2.254` |
| Site Router | `G0/2` | `192.168.3.1` | `255.255.255.0` | `192.168.3.0 - 192.168.3.254` |
| Main PC | Monitoring workstation | `192.168.1.5` | `255.255.255.0` | Core range |
| NVR | Recorder | `192.168.1.6` | `255.255.255.0` | Core range |
| IoT Server | Simulation server | `192.168.1.10` | `255.255.255.0` | Core range |
| Partner Router | `G0/0` | `192.168.4.1` | `255.255.255.0` | `192.168.4.0 - 192.168.4.254` |
| Partner Router | `G0/1` | `192.168.5.1` | `255.255.255.0` | `192.168.5.0 - 192.168.5.254` |
| Partner PC | Workstation | `192.168.5.3` | `255.255.255.0` | Partner range |
| Mesh Node 1 | Mesh node | `192.168.2.12` | `255.255.255.0` | Mesh range |
| Mesh Node 2 | Mesh node | `192.168.2.13` | `255.255.255.0` | Mesh range |
| Mesh Node 3 | Mesh node | `192.168.2.14` | `255.255.255.0` | Mesh range |
| Mesh Node 4 | Mesh node | `192.168.2.15` | `255.255.255.0` | Mesh range |

## Naming Convention

| Category | Names |
| --- | --- |
| Routers | `Site_Router`, `Partner_Router`, `Internet` |
| Switches | `Site_Switch`, `Partner_Switch` |
| Mesh Nodes | `Main_Mesh`, `NODE_1`, `NODE_2`, `NODE_3`, `NODE_4` |
| Workstations And Services | `Partner_PC`, `MAIN_PC`, `NVR` |
| Cameras | `CAM1`, `CAM1_1`, `CAM1_2`, `CAM2`, `CAM2_1`, `CAM2_2`, `CAM4`, `CAM4_1`, `CAM4_2`, `CAM5`, `CAM5_1`, `CAM5_2` |

## Bandwidth Planning Table

| Camera Count | Average Bitrate | Estimated Stream Load | Recommended Reserved Capacity |
| --- | --- | --- | --- |
| 12 | 2 Mbps | 24 Mbps | 36 Mbps or higher |
| 12 | 4 Mbps | 48 Mbps | 72 Mbps or higher |
| 12 | 8 Mbps | 96 Mbps | 144 Mbps or higher |

## Community Survey Technical Summary

| Finding | Result |
| --- | --- |
| Daytime safety concern | Majority reported unsafe or very unsafe conditions. |
| Nighttime safety concern | Majority reported unsafe or very unsafe conditions. |
| Current security confidence | Very low confidence in current measures and response effectiveness. |
| Camera availability | Most respondents reported a lack of existing public-area surveillance cameras. |
| Support for surveillance improvement | Very high support for improved surveillance coverage. |
| Priority areas | Parks, dark corners, alleys, residential streets, parking areas, and commercial areas. |

## Validation Metrics

| Metric | What To Measure | Why It Matters |
| --- | --- | --- |
| Signal strength | RSSI or link-quality readings at planned device points. | Confirms mesh and bridge viability. |
| Throughput | Actual usable bandwidth by link and segment. | Confirms camera stream capacity. |
| Latency | Delay from camera to NVR and workstation. | Confirms live monitoring usability. |
| Connectivity | Camera/NVR registration and link stability. | Confirms devices stay online. |
| Reliability | Uptime, failover path behavior, storage continuity. | Confirms resilience. |
| Security | ACLs, VLAN isolation, VPN, HTTPS, credential policy. | Confirms access controls. |
| Storage | Disk growth, retention, and recording health. | Confirms evidence preservation. |

