# MeshSight Sentinel: Resilient Wireless Mesh Surveillance Blueprint

Made by Austin BC

MeshSight Sentinel is a technical network design for a community-scale outdoor surveillance system using IP cameras, wireless mesh nodes, point-to-multipoint wireless bridges, centralized NVR storage, and secured remote access. It converts the original capstone material into a privacy-safe GitHub-ready engineering repository: architecture notes, deployment steps, device selection, network configuration examples, validation criteria, and a sanitized visual appendix.

The design focuses on a small, flat community footprint with coverage needs across multiple zones, limited existing CCTV coverage, constrained budget, and a requirement for scalable, reliable monitoring from a local operations center.

## What This Builds

- A wireless mesh surveillance topology with redundant wireless paths.
- A point-to-multipoint wireless bridge layer for longer, higher-stability links.
- A centralized NVR recording model for camera retention and review.
- Static IP planning for predictable device management.
- Secure remote access through VPN, HTTPS, strong authentication, and access control.
- A validation plan for signal strength, throughput, latency, uptime, storage, security, and user experience.
- A future-ready roadmap for SIEM monitoring, vulnerability testing, failover, RAID, and unified dashboards.

## Core Architecture

The system uses a local operations center as the hub. The main router, NVR, and monitoring workstation sit in the secure indoor core. Wireless bridges extend stable backhaul coverage, while mesh nodes distribute camera connectivity across the target area. IP cameras are placed along high-traffic paths, dark corners, intersections, and community spaces that need monitoring.

The proposed device stack includes:

| Layer | Device Role | Selected Platform |
| --- | --- | --- |
| Gateway | Main router, firewall, VPN, VLANs | Ubiquiti Dream Router |
| Backhaul | Main PtMP wireless bridge | Ubiquiti airMAX NanoStation 5AC |
| Backhaul | Bridge stations | Ubiquiti PowerBeam AC |
| Mesh | Wireless mesh nodes | Linksys WHW0301 |
| Recording | Network video recorder | Hikvision DS-7616NXI-K2/16P |
| Cameras | Bullet IP cameras | Hikvision DS-2CD1023G0-IU(F) |
| Cameras | Wide-angle dome IP cameras | Hikvision HWI-D140H |

## Design Targets

| Target | Design Direction |
| --- | --- |
| Coverage | Place cameras around priority public areas, roads, intersections, entry points, and poorly lit spaces. |
| Reliability | Use mesh path redundancy, PtMP backhaul, static addressing, secure mounting, and NVR-centered recording. |
| Scalability | Keep the topology modular so cameras, mesh nodes, storage, and monitoring integrations can be added later. |
| Security | Use WPA2 or stronger wireless security, HTTPS, VPN, MFA, ACLs, VLAN segmentation, firmware updates, and disabled unused services. |
| Bandwidth | Plan roughly 2 to 4 Mbps per camera for ordinary HD streams, then reserve capacity for spikes and live viewing. |
| Storage | Centralize recording on the NVR, prefer H.265/H.265+, and add RAID plus external backup for real deployments. |

## Repository Map

| Path | Purpose |
| --- | --- |
| [docs/architecture.md](docs/architecture.md) | Full topology, traffic flow, addressing model, protocols, and design trade-offs. |
| [docs/source-study-summary.md](docs/source-study-summary.md) | Condensed technical reading of the source PDF and its design findings. |
| [docs/ip-addressing.md](docs/ip-addressing.md) | Addressing scheme transcribed from the source visual, plus deployment corrections. |
| [docs/deployment-plan.md](docs/deployment-plan.md) | Physical installation, logical configuration, bandwidth, storage, and rollout steps. |
| [docs/security-and-compliance.md](docs/security-and-compliance.md) | Network security policy, access model, privacy controls, monitoring, and hardening checklist. |
| [docs/privacy-sanitization.md](docs/privacy-sanitization.md) | Public-safe sanitization notes and asset policy. |
| [docs/bill-of-materials.md](docs/bill-of-materials.md) | Device inventory, specs, compatibility notes, and budget posture. |
| [docs/validation-plan.md](docs/validation-plan.md) | Test plan for signal, throughput, latency, connectivity, reliability, storage, and security. |
| [docs/operations-runbook.md](docs/operations-runbook.md) | Day-to-day operations, incident handling, backup, maintenance, and escalation workflows. |
| [docs/image-gallery.md](docs/image-gallery.md) | Privacy-safe device image gallery. Sensitive source screenshots are excluded. |
| [configs/](configs/) | Example router, switch, VPN, and wireless/camera configuration references. |
| [assets/device-images/](assets/device-images/) | Public-safe device visuals only. |

## Added Engineering Improvements

The GitHub version keeps the original scope but adds practical implementation detail:

- Dual-WAN failover or load balancing option for the gateway.
- RAID-backed NVR storage guidance with backup and retention policy.
- SIEM-ready logging path for router, NVR, camera, and authentication events.
- VLAN segmentation for cameras, management, monitoring workstation, guest or admin traffic, and partner-agency interconnect.
- Network monitoring recommendations using SNMP, uptime checks, throughput probes, and storage alerts.
- Security review workflow covering vulnerability assessment, firmware review, access audits, and camera tamper alerts.
- Operator-focused dashboard concept for live feeds, playback, health status, and incident export.

## Quick Implementation Flow

1. Survey the site for mounting points, RF line-of-sight, power availability, and camera fields of view.
2. Install the secure indoor core: router, NVR, monitoring workstation, UPS, and locked cabinet.
3. Mount bridge devices and validate link quality before adding cameras.
4. Place mesh nodes for overlapping coverage and alternate wireless paths.
5. Add cameras using static IPs, ONVIF/RTSP compatibility checks, and strong credentials.
6. Segment traffic with VLANs and access rules.
7. Enable NVR recording, retention, event alerts, and secure remote access.
8. Run the validation plan and tune placement, bitrate, FPS, channel width, and QoS.

## Operational Concept

The network should be managed as critical public-safety infrastructure. Operators use the NVR and dashboard for live view, playback, and export. Administrators maintain device health, firmware, accounts, VLANs, logs, backups, and incident response. Any production deployment should include written access approval, evidence handling, retention, maintenance, and escalation procedures.

## Visual Appendix

Privacy-safe device visuals are available in [docs/image-gallery.md](docs/image-gallery.md). Source screenshots that may contain full names, exact places, signatures, reports, CVs, letters, or map details are intentionally excluded from the public repo version.
