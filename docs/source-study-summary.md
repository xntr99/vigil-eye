# Source Study Summary

This document summarizes the source PDF as a technical project rather than an academic manuscript. Names, institutional front matter, exact location details, and dated thesis material are intentionally excluded from the written GitHub version.

## Problem

The target community has limited surveillance coverage and relies on aging or insufficient camera infrastructure. Several areas need better visibility, especially roads, public spaces, alleys, dark corners, and high-traffic locations. The design must work within budget and staffing limits while still providing a practical path toward modern surveillance.

## Proposed Solution

The project proposes an IP-camera surveillance network using:

- Wireless mesh nodes for distributed local coverage.
- Point-to-multipoint wireless bridges for stronger longer-distance transport.
- A centralized NVR for recording, retention, and playback.
- Static addressing for predictable management.
- ONVIF and RTSP for camera/NVR interoperability.
- Secure remote access through HTTPS and VPN.
- Network segmentation, strong credentials, firmware management, and access controls.

## Research Inputs

![Community survey chart](../assets/source-figures/community-survey-p087-01.png)

![Community survey chart](../assets/source-figures/community-survey-p088-01.png)

The source material combines several input types:

| Input | How It Shapes The Design |
| --- | --- |
| Community survey | Establishes demand for improved security and identifies priority coverage areas. |
| Local interviews | Identifies budget, maintenance, staffing, and current infrastructure limits. |
| Site observation | Informs camera placement, wireless coverage, and physical layout. |
| Device research | Filters options by budget, compatibility, vendor reputation, and feature support. |
| Expert review | Adds practical recommendations for redundancy, storage, failover, security, testing, and scalability. |
| Packet Tracer simulation | Demonstrates logical connectivity, routing, VPN, ACLs, switching, and camera integration. |

## Key Design Findings

- IP cameras are a better fit than analog CCTV for scalable monitoring, centralized recording, and network integration.
- Mesh networking helps preserve coverage when one wireless path weakens.
- PtMP bridges improve stability for longer wireless paths and bandwidth-sensitive camera traffic.
- Centralized NVR storage simplifies playback and evidence management.
- Camera bandwidth must be calculated per stream, then aggregated across the full system.
- H.265/H.265+ compression, FPS tuning, and motion recording can reduce bandwidth and storage pressure.
- Static addressing is manageable for this network size and simplifies troubleshooting.
- ONVIF compatibility matters because the design uses multi-vendor components.
- Security needs both network controls and physical protection of mounted devices.

## Expert Recommendations Integrated Into This Repo

- Add RAID to the NVR storage plan.
- Consider dual ISP failover or load balancing.
- Add backup power for the core network and recording system.
- Use monitoring tools for throughput, uptime, storage, and device health.
- Consider SIEM logging for authentication, camera, NVR, and network events.
- Strengthen segmentation with VLANs and ACLs.
- Use secure mounting and physical access controls.
- Provide operator training, troubleshooting documentation, and recurring audits.

## Scope Boundary

The original work is an implementation plan and simulated design, not a completed field installation. This GitHub version keeps that boundary clear while adding production-minded guidance for teams that want to turn the blueprint into a pilot or rollout.
