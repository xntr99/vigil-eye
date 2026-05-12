# Camera Wireless Profile

Use this as a configuration reference for simulated wireless cameras or camera-adjacent wireless client devices.

## Wireless Settings

| Setting | Recommendation |
| --- | --- |
| SSID | Use a dedicated surveillance SSID, not a public or staff SSID. |
| Security | WPA2-PSK minimum; WPA3 where supported by all devices. |
| Passphrase | Use a long unique passphrase stored in the credential vault. |
| IP mode | Static IP for cameras and infrastructure. |
| Management | HTTPS only where supported. |
| Discovery | Disable broad discovery after onboarding if operations allow it. |

## Camera Onboarding

1. Factory reset only if the device is new or being re-provisioned.
2. Upgrade firmware before production use.
3. Change default credentials.
4. Assign static IP, gateway, DNS, and NTP.
5. Enable ONVIF only if required by the NVR.
6. Confirm RTSP stream paths.
7. Add the camera to the NVR.
8. Verify live view, recording, playback, and tamper alerts.
9. Record camera location, MAC address, serial number, firmware, and assigned VLAN.

## Recommended Stream Defaults

| Stream | Suggested Baseline |
| --- | --- |
| Codec | H.265 or H.265+ |
| Resolution | Match placement goal; avoid maximum resolution by default. |
| FPS | Tune for usable evidence and bandwidth limits. |
| Bitrate | Start around 2 to 4 Mbps for HD, then tune after field testing. |
| Motion recording | Enable where policy allows to reduce storage load. |

