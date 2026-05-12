# Deployment Plan

This plan converts the design into an implementation sequence. It is written as a practical blueprint for a real rollout, while still matching the original simulated project scope.

## Phase 1: Site Survey

- Map roads, intersections, dark areas, community spaces, existing poles, power sources, and mounting constraints.
- Perform RF checks for bridge line-of-sight, mesh overlap, noise, and interference.
- Confirm camera fields of view before final mounting.
- Identify the secure indoor location for the router, NVR, UPS, and monitoring workstation.
- Record each proposed device location in an installation sheet.

## Phase 2: Physical Install

| Component | Placement Guidance |
| --- | --- |
| Main router | Secure indoor cabinet or rack at the local operations center. |
| NVR | Same secured core location as router, with ventilation and UPS. |
| Monitoring PC | Wired to the core network where possible. |
| Main wireless bridge | Elevated position with line-of-sight to bridge stations. |
| Bridge stations | Mounted on stable poles or buildings with weatherproofing. |
| Mesh nodes | Spaced for overlapping coverage and reduced dead zones. |
| Bullet cameras | Roads, approaches, long corridors, and high-traffic paths. |
| Dome cameras | Intersections, wider-angle spaces, entrances, and gathering areas. |

Use tamper-resistant mounts, weatherproof enclosures, cable strain relief, and labeled cables. Sensitive core devices should sit behind locked physical access controls.

## Phase 3: Logical Configuration

- Assign static IPs to all infrastructure and camera devices.
- Create VLANs for cameras, management, core/NVR, and remote interconnect.
- Configure trunks between switches and the router where VLANs cross links.
- Configure WPA2 or stronger wireless security.
- Disable unused services on cameras, NVR, router, and mesh devices.
- Enable HTTPS management where supported.
- Enable VPN for remote access rather than exposing the NVR directly.
- Configure ACLs so only authorized workstations and admin networks can reach camera management pages.
- Verify ONVIF and RTSP compatibility before final camera acceptance.

## Phase 4: Bandwidth Planning

Use the expected bitrate per camera to size links and storage. A simple planning model:

```text
total_camera_bandwidth = number_of_cameras * average_camera_bitrate
recommended_capacity = total_camera_bandwidth * 1.5
```

For the original twelve-camera design, a 2 to 4 Mbps average stream suggests:

| Camera Count | Average Bitrate | Estimated Stream Load | Recommended Reserved Capacity |
| --- | --- | --- | --- |
| 12 | 2 Mbps | 24 Mbps | 36 Mbps or higher |
| 12 | 4 Mbps | 48 Mbps | 72 Mbps or higher |
| 12 | 8 Mbps | 96 Mbps | 144 Mbps or higher |

Tune bitrate, FPS, resolution, and codec after field testing. Prefer H.265 or H.265+ where supported.

## Phase 5: Storage Planning

Use the NVR as the primary recording point. Add RAID and external backup for production use.

Approximate storage formula:

```text
storage_gb = (bitrate_mbps * 86,400 seconds * retention_days) / 8 / 1,024
```

Operational guidance:

- Define retention by policy before deployment.
- Reserve space for motion spikes and high-complexity scenes.
- Use RAID for disk failure tolerance.
- Export critical incidents to a controlled evidence archive.
- Monitor disk health, recording status, and free capacity.

## Phase 6: Monitoring and Alerting

- Poll router, switches, NVR, and bridge devices with SNMP where available.
- Alert on camera offline, recording failure, high disk use, link degradation, and failed logins.
- Forward security logs to a SIEM when available.
- Maintain firmware inventory and change history.
- Review access logs and operator accounts regularly.

## Phase 7: Acceptance

Accept the rollout only after the validation plan passes:

- Camera coverage matches the intended viewing zones.
- Every camera records to the NVR.
- Remote access works only through approved secure channels.
- Mesh and bridge links remain stable under live camera load.
- Failover, backup, and recovery procedures are documented.
- Operators can view live feeds, search playback, and export evidence.
