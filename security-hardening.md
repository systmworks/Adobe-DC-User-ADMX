<p align="center"><a href="https://buymeacoffee.com/systmworks"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="45" alt="Buy me a coffee"></a></p>

> I have spent many, many hours creating and testing this ADMX. If it helps you please consider buying me a Coffee :)

[<- Back to Documentation](README.md)

# Security Hardening Guide

Recommended and optional security-related **Group Policy** states for the v1.10 user (`HKCU`) ADMX templates. **Curated subset** - only policies with a **GoodSetting** value in the preference source (not all 501 ADMX policies).

These complement (but do not replace) Adobe's own [Application Security Guide](https://www.adobe.com/devnet-docs/acrobatetk/tools/AppSec/index.html).

- ![Recommended](https://img.shields.io/badge/Recommended-238636?style=flat-square) - DISA STIG-aligned or broadly advisable; verify against your STIG baseline.
- ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) - additional hardening without a STIG cross-reference in the source data; may affect workflows.

## Reader DC (12 suggested settings)

| ![Category](https://img.shields.io/badge/Category-316dca?style=flat-square) | ![FriendlyName](https://img.shields.io/badge/FriendlyName-316dca?style=flat-square) | ![Path](https://img.shields.io/badge/Path-316dca?style=flat-square) | ![Suggested GPO](https://img.shields.io/badge/Suggested%20GPO-316dca?style=flat-square) | ![Notes](https://img.shields.io/badge/Notes-316dca?style=flat-square) | ![Priority](https://img.shields.io/badge/Priority-316dca?style=flat-square) |
|---|---|---|---|---|---|
| Security: Execution & Protection | 3D Content Trust | ``DC\3D`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | Enable JS Debugger | ``DC\JSPrefs`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | FIPS Mode | ``DC\AVGeneral`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) | STIG ARDC-CN-000345 (V-213193) Medium; STIG AADC-CN-000955 (V-245874) Medium | ![Recommended](https://img.shields.io/badge/Recommended-238636?style=flat-square) |
| Security: Execution & Protection | JS Global Security | ``DC\JSPrefs`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | JS Menu Items | ``DC\JSPrefs`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | Outlook Protected View | ``DC\TrustManager`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Accept Expired Timestamps | ``Security\cAdobe_TSPProvider`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Allow LiveCycle HTTP | ``Security\cEDC`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Load Security Settings from Server (Adobe Certificates) | ``cDigSig\cAdobeDownload`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) | STIG ARDC-CN-000335 (V-213191) Low; STIG AADC-CN-001320 (V-213138) Low | ![Recommended](https://img.shields.io/badge/Recommended-238636?style=flat-square) |
| Security: Trust & Permissions | Load Security Settings from Server (European Certificates) | ``cDigSig\cEUTLDownload`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) | STIG ARDC-CN-000330 (V-213190) Low; STIG AADC-CN-000990 (V-213126) Low | ![Recommended](https://img.shields.io/badge/Recommended-238636?style=flat-square) |
| Security: Trust & Permissions | Open Non-PDF Attachments | ``DC\Originals`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Secure Open Attachments | ``DC\Originals`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |

## Acrobat DC (12 suggested settings)

| ![Category](https://img.shields.io/badge/Category-316dca?style=flat-square) | ![FriendlyName](https://img.shields.io/badge/FriendlyName-316dca?style=flat-square) | ![Path](https://img.shields.io/badge/Path-316dca?style=flat-square) | ![Suggested GPO](https://img.shields.io/badge/Suggested%20GPO-316dca?style=flat-square) | ![Notes](https://img.shields.io/badge/Notes-316dca?style=flat-square) | ![Priority](https://img.shields.io/badge/Priority-316dca?style=flat-square) |
|---|---|---|---|---|---|
| Security: Execution & Protection | 3D Content Trust | ``DC\3D`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | Enable JS Debugger | ``DC\JSPrefs`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | FIPS Mode | ``DC\AVGeneral`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) | STIG ARDC-CN-000345 (V-213193) Medium; STIG AADC-CN-000955 (V-245874) Medium | ![Recommended](https://img.shields.io/badge/Recommended-238636?style=flat-square) |
| Security: Execution & Protection | JS Global Security | ``DC\JSPrefs`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | JS Menu Items | ``DC\JSPrefs`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Execution & Protection | Outlook Protected View | ``DC\TrustManager`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Accept Expired Timestamps | ``Security\cAdobe_TSPProvider`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Allow LiveCycle HTTP | ``Security\cEDC`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Load Security Settings from Server (Adobe Certificates) | ``cDigSig\cAdobeDownload`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) | STIG ARDC-CN-000335 (V-213191) Low; STIG AADC-CN-001320 (V-213138) Low | ![Recommended](https://img.shields.io/badge/Recommended-238636?style=flat-square) |
| Security: Trust & Permissions | Load Security Settings from Server (European Certificates) | ``cDigSig\cEUTLDownload`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) | STIG ARDC-CN-000330 (V-213190) Low; STIG AADC-CN-000990 (V-213126) Low | ![Recommended](https://img.shields.io/badge/Recommended-238636?style=flat-square) |
| Security: Trust & Permissions | Open Non-PDF Attachments | ``DC\Originals`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |
| Security: Trust & Permissions | Secure Open Attachments | ``DC\Originals`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |   | ![Optional](https://img.shields.io/badge/Optional-1f6feb?style=flat-square) |

---

**Sharing & responsibility** — Built for the community, shared with good intentions. Use at your own risk. The author accepts no responsibility for any outcomes resulting from the use of these files. Always verify registry paths and values, and test in a safe environment first. If you find an issue or have a suggestion, contributions are welcome.