# Validation Plan

The validation plan turns the design into measurable acceptance tests. It can be used during simulation, pilot deployment, or full implementation.

## Test Matrix

| Area | Test | Success Criteria |
| --- | --- | --- |
| Signal strength | Measure mesh and bridge RSSI at planned device points. | Links remain stable under expected weather and normal interference. |
| Throughput | Run bandwidth tests across camera paths and backhaul paths. | Aggregate bandwidth supports all camera streams with reserve capacity. |
| Latency | Measure delay from camera to NVR and operator workstation. | Live viewing remains usable without major lag or frame loss. |
| Camera connectivity | Confirm every camera reaches the NVR and management network as designed. | All cameras stay online and record continuously during burn-in. |
| Failover path | Temporarily degrade or disable a mesh path. | Alternate path keeps critical coverage online where mesh redundancy exists. |
| Recording | Verify NVR recording, playback, export, and retention. | Footage can be searched, played back, and exported by authorized users. |
| Security | Test credentials, VLAN isolation, ACLs, VPN, and HTTPS. | Unauthorized paths are blocked; approved paths work. |
| Storage | Monitor disk use and recording estimates. | Retention target is achievable with alert thresholds configured. |
| User experience | Ask operators to perform live view, playback, export, and camera search. | Operators complete normal tasks without admin assistance. |

## Field Measurements

Collect the following during deployment:

- Device hostname.
- Static IP address.
- VLAN.
- Physical location.
- Mount height.
- Power source.
- RSSI or signal quality.
- Camera bitrate.
- Resolution and FPS.
- Codec.
- NVR recording status.
- Firmware version.
- Last configuration backup.

## Burn-In Test

Run a burn-in period before handover:

- Continuous recording from all cameras.
- Live viewing from the monitoring workstation.
- Remote VPN login test.
- Camera disconnect and reconnect test.
- Power interruption test for the core equipment if UPS is installed.
- Storage growth check.
- Log review for failed authentication or unstable links.

## Acceptance Checklist

- All camera views match approved coverage goals.
- Camera timestamps are synchronized.
- NVR records every camera.
- Playback and export are verified.
- VLAN isolation is tested.
- Admin access is restricted.
- Default credentials are removed.
- Firmware versions are documented.
- UPS, storage, and alerting status are documented.
- Operators receive handover documentation and training.

