<p align="center"><a href="https://buymeacoffee.com/systmworks"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="45" alt="Buy me a coffee"></a></p>

> I have spent many, many hours creating and testing this ADMX. If it helps you please consider buying me a Coffee :)

# Adobe DC ADMX/ADML Documentation

## Quick Links

| ![Page](https://img.shields.io/badge/Page-316dca?style=flat-square) | ![Description](https://img.shields.io/badge/Description-316dca?style=flat-square) |
|------|-------------|
| [Reader DC Settings](reader-settings.md) | Complete list of all Reader DC policies |
| [Acrobat DC Settings](acrobat-settings.md) | Complete list of all Acrobat DC policies |
| [Security Hardening](security-hardening.md) | Recommended and optional security configurations |
| [Reduce Nags & Upsells](reduce-nags.md) | Settings to suppress unwanted messages, popups, and promotions |
| [Screenshots](screenshots.md) | GPMC and Intune screenshots showing policy configuration |
| [Changelog](changelog.md) | Settings changes across ADMX versions |
| [v1.10 release readme](../v1.10%20(User)/readme.md) | Current production bundle — upload and namespace details |

These user-scope ADMX/ADML templates (**v1.10**) provide Group Policy and Intune management of **per-user** Adobe Acrobat DC and Adobe Reader DC preferences on Windows. They define `HKCU` policies (see `AdobeDC_User.admx` / `AdobeDC_User.adml` in the **v1.10 (User)** release folder), not machine-level `HKLM` lockable templates.

**Intune display names:** v1.10 appends ` (User)` to every leaf policy name in ADML (Microsoft convention), so admins can tell user vs machine settings apart in mixed profiles. The policy tables below use Adobe PrefRef **friendly names** without that suffix.

Policy list pages and the hardening / reduce-nags guides use the **GoodSetting** column from the HKCU preference source used to build these templates: **Set to Enabled** or **Set to Disabled** refers to the Group Policy policy state, mapping to the per-policy ``RegValEnabled`` / ``RegValDisabled`` DWORDs.

| ![File](https://img.shields.io/badge/File-316dca?style=flat-square) | ![Scope](https://img.shields.io/badge/Scope-316dca?style=flat-square) | ![Policies](https://img.shields.io/badge/Policies-316dca?style=flat-square) |
|------|-------|----------|
| `AdobeDC_User.admx` + ADML | User (`HKCU`) — Acrobat DC + Reader DC | **501** (258 Acrobat + 243 Reader; includes `tHostPerms` text policy) |

## Important Notes

| ![Note](https://img.shields.io/badge/Note-316dca?style=flat-square) |
|------|
| Acrobat Reader (x64) using the new **Unified Installer** runs ``Acrobat.exe``, so it requires configuration of the **Acrobat** settings rather than the Reader settings. To be safe, configure both. |
| Several ``bToggle*`` policies use inverted registry values (DWORD 0 = feature ON, DWORD 1 = feature OFF). The ADMX templates handle this so that the Group Policy **Enabled**/**Disabled** states match the FriendlyName intent, but raw registry checks may look counterintuitive. |

## Category Overview

| ![Category](https://img.shields.io/badge/Category-316dca?style=flat-square) | ![Overview](https://img.shields.io/badge/Overview-316dca?style=flat-square) | ![Reader](https://img.shields.io/badge/Reader-316dca?style=flat-square) | ![Acrobat](https://img.shields.io/badge/Acrobat-316dca?style=flat-square) |
|----------|----------|:------:|:-------:|
| Context, Tools & Search | Cursor and selection tools, hand-tool behavior, filename-as-title, recent files, Modern Viewer/HUD, search, and workflow UI preferences under HKCU. | 19 | 22 |
| Documents, Editing & Accessibility | Page display, zoom and layout defaults, rendering and fonts, commenting, forms, measurement, accessibility color replacement, and editing-related user preferences. | 86 | 89 |
| Microsoft Purview (MIP) | Per-user Microsoft Purview Information Protection (MIP) preferences under HKCU MicrosoftAIP, including document message bar visibility, policy authentication, and debug logging. | 3 | 3 |
| Security: Execution & Protection | User-level execution controls such as 3D/multimedia trust, JavaScript debugger and menu behavior, FIPS mode, and related HKCU security execution settings. | 8 | 13 |
| Security: Trust & Permissions | Digital signatures, certificate and timestamp validation, OCSP/CRL behavior, trust-manager URL permissions, and other HKCU signing and trust preferences. | 75 | 76 |
| Sharing & Features | Collaboration, Send & Track, shared reviews, cloud sharing hooks, and related feature toggles stored as per-user preferences. | 9 | 11 |
| Startup & Experience | Splash screen, launch alerts, onboarding and What's New dialogs, home-screen widgets, notifications, and first-run experience controls. | 29 | 29 |
| Updates & Desktop Integration | Product updater behavior, browser and Fast Web View integration, background download, thumbnails/shell integration, and desktop UI preferences. | 11 | 11 |
| Upsell | Upgrade prompts, trial purchase dialogs, promotional surfaces, App Center visibility, and purchasable-tool upsell controls. | 2 | 3 |


---

**Sharing & responsibility** — Built for the community, shared with good intentions. Use at your own risk. The author accepts no responsibility for any outcomes resulting from the use of these files. Always verify registry paths and values, and test in a safe environment first. If you find an issue or have a suggestion, contributions are welcome.