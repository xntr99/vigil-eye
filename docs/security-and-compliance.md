# Security And Compliance

The surveillance network handles sensitive community footage, so the design treats security as part of the architecture rather than an afterthought.

## Security Principles

- Least privilege for every account and device.
- Separate camera traffic from management and user traffic.
- Prefer secure remote access through VPN instead of direct public exposure.
- Keep footage access auditable and limited to authorized personnel.
- Patch cameras, NVR, routers, and mesh infrastructure on a scheduled cadence.
- Protect both digital access and physical device locations.

## Access Model

| Role | Access |
| --- | --- |
| System administrator | Router, NVR, camera management, monitoring, backups, and policy updates. |
| Surveillance operator | Live view, playback, export workflow, and incident tagging. |
| Site official | Approved playback or incident access through request workflow. |
| Law enforcement or external requester | Evidence access only through documented approval and disclosure process. |
| Vendor technician | Time-bound maintenance access with supervision and logs. |

## Hardening Checklist

- Change all default credentials before connecting devices to the production network.
- Use unique passwords per device class.
- Enable MFA for remote access and administrative portals where supported.
- Use HTTPS for management interfaces.
- Disable UPnP, unused cloud features, unused discovery services, and unused accounts.
- Restrict camera management access to admin VLANs.
- Use ACLs to limit lateral movement from camera VLANs.
- Enable automatic or scheduled firmware review.
- Disable direct inbound internet access to NVR and cameras.
- Use VPN for remote management and review.
- Keep an asset inventory with serials, firmware versions, assigned IPs, and physical locations.

## VLAN Policy

| VLAN | Allowed Access |
| --- | --- |
| Camera VLAN | Cameras can stream to NVR; cameras cannot initiate admin access to other segments. |
| Core/NVR VLAN | NVR can receive camera streams and serve approved operator clients. |
| Admin VLAN | Admin workstations can manage approved infrastructure. |
| Mesh/bridge management VLAN | Only network admins can manage wireless infrastructure. |
| Remote/VPN VLAN | VPN users receive role-based access only. |

## Logging And SIEM Path

The original recommendations mention adding SIEM, penetration testing, vulnerability assessments, and security audits. A practical SIEM pipeline would collect:

- Router firewall and VPN logs.
- NVR login, playback, export, and recording failure events.
- Camera tamper, illegal login, and disconnect events.
- Wireless bridge signal, disassociation, and link-quality events.
- Switch port status and topology changes.
- Windows or workstation authentication logs for monitoring clients.

Recommended alert categories:

- Failed login bursts.
- New or unknown device on camera VLAN.
- Camera offline beyond threshold.
- NVR recording stopped.
- Storage capacity above threshold.
- VPN login from unusual location or time.
- Firmware version below approved baseline.

## Physical Security

- Mount cameras with tamper-resistant hardware.
- Place bridge devices high enough to reduce casual access.
- Use weatherproof electrical enclosures.
- Keep the router, NVR, UPS, and monitoring workstation in a locked location.
- Label cables without exposing sensitive network details publicly.
- Maintain an inspection schedule for mounts, seals, cable damage, and enclosure integrity.

## Privacy And Data Protection

The system should follow privacy-by-design principles:

- Limit camera views to public safety-relevant areas.
- Avoid unnecessary capture of private interiors.
- Publish clear notice that surveillance is operating.
- Define retention before deployment.
- Keep export and disclosure workflows documented.
- Log who accessed footage, what was accessed, and why.
- Dispose of expired footage according to policy.
- Require written authorization for external release.

## Security Review Workflow

Run these reviews before production and on a recurring schedule:

- Credential audit.
- Firmware review.
- VLAN and ACL review.
- NVR retention and backup review.
- Wireless encryption review.
- Camera field-of-view privacy review.
- Vulnerability scan of management interfaces.
- Restore test for exported or backed-up footage.
