# Operations Runbook

This runbook describes how to operate MeshSight Sentinel after deployment.

## Daily Checks

- Confirm all cameras are online.
- Confirm NVR recording is active for every camera.
- Check storage capacity and recording retention.
- Review critical alerts: camera tamper, failed login, link degradation, NVR errors, and disk warnings.
- Confirm the monitoring workstation can view live feeds and playback.

## Weekly Checks

- Review user access logs.
- Confirm no default or shared accounts are active.
- Verify bridge and mesh link quality.
- Review recent firmware advisories for router, cameras, NVR, and wireless devices.
- Export and test a short playback clip to confirm evidence workflow.
- Inspect camera views for obstruction, misalignment, or privacy issues.

## Monthly Checks

- Test UPS runtime for the core equipment.
- Review VLAN and ACL rules.
- Verify backup or archive workflow.
- Check physical mounts, enclosures, seals, and cable condition.
- Review retention policy compliance.
- Run a vulnerability scan against management interfaces from the admin VLAN.

## Incident Workflow

1. Record the incident request, requester, reason, and approval source.
2. Identify relevant camera locations and time range.
3. Review footage from the NVR using an authorized account.
4. Export only the required clip range.
5. Store exported evidence in a controlled location.
6. Log who accessed, exported, transferred, or deleted evidence.
7. Preserve related system logs when the incident involves tampering, outage, or unauthorized access.

## Outage Workflow

| Symptom | First Checks |
| --- | --- |
| Single camera offline | Power, PoE, wireless association, camera IP, ping, NVR registration, mount/cable condition. |
| Camera group offline | Mesh node, bridge station, local power, VLAN trunk, wireless interference. |
| All cameras offline | Core router, NVR, switch, UPS, ISP, VLAN configuration. |
| Recording stopped | NVR service status, disk health, camera credentials, stream settings, storage capacity. |
| Remote access failure | VPN status, user account, MFA, firewall, ISP uplink, DNS. |

## Change Management

Every network change should record:

- Change owner.
- Affected device.
- Reason for change.
- Configuration before and after.
- Test result.
- Rollback procedure.

Back up configurations before firmware upgrades, routing changes, VLAN changes, NVR storage changes, or camera credential rotation.

## Handover Package

Before the system is accepted, provide:

- Network diagram.
- Device inventory.
- IP address table.
- Camera placement map.
- Account and role matrix.
- NVR retention settings.
- Backup and export procedure.
- Firmware baseline.
- Validation results.
- Maintenance schedule.

