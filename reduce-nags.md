<p align="center"><a href="https://buymeacoffee.com/systmworks"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="45" alt="Buy me a coffee"></a></p>

> I have spent many, many hours creating and testing this ADMX. If it helps you please consider buying me a Coffee :)

[<- Back to Documentation](README.md)

# Reduce Nags, Upsells & Unwanted Notifications

Suggested **Group Policy** states to reduce onboarding prompts, tooltips, upsells, and similar UI noise in the v1.10 user (`HKCU`) ADMX templates. Rows come from the **GoodSetting** column in the preference source for non-security categories.

## Reader DC

| ![Category](https://img.shields.io/badge/Category-316dca?style=flat-square) | ![FriendlyName](https://img.shields.io/badge/FriendlyName-316dca?style=flat-square) | ![Path](https://img.shields.io/badge/Path-316dca?style=flat-square) | ![Suggested GPO](https://img.shields.io/badge/Suggested%20GPO-316dca?style=flat-square) |
|---|---|---|---|
| Context, Tools & Search | New Look Coachmark | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Context, Tools & Search | Show Tool Pane Tips | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Context, Tools & Search | Try New Coachmark | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Context, Tools & Search | UI Switcher Sessions | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Documents, Editing & Accessibility | Form Email Prompt | ``AVAlert\cCheckbox`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Create Form Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Edit Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Fill & Sign Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Hide Help Welcome | ``DC\AVGeneral`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |
| Startup & Experience | Home Onboarding | ``DC\FTEDialog`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Organize Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Redaction Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Show About Dialog | ``DC\Originals`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Show Getting Started | ``DC\HomeWelcome`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Viewer Onboarding | ``DC\FTEDialog`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Upsell | Acrobat App Promo | ``cServices\cAcrobatApp`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Upsell | Scan App Promo | ``cServices\cScanApp`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |

## Acrobat DC

| ![Category](https://img.shields.io/badge/Category-316dca?style=flat-square) | ![FriendlyName](https://img.shields.io/badge/FriendlyName-316dca?style=flat-square) | ![Path](https://img.shields.io/badge/Path-316dca?style=flat-square) | ![Suggested GPO](https://img.shields.io/badge/Suggested%20GPO-316dca?style=flat-square) |
|---|---|---|---|
| Context, Tools & Search | New Look Coachmark | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Context, Tools & Search | Show Tool Pane Tips | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Context, Tools & Search | Suppress PDF/UA Dialog | ``DC\FeatureState`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |
| Context, Tools & Search | Try New Coachmark | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Context, Tools & Search | UI Switcher Sessions | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Documents, Editing & Accessibility | Form Email Prompt | ``AVAlert\cCheckbox`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Create Form Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Edit Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Fill & Sign Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Hide Help Welcome | ``DC\AVGeneral`` | Set to ![Enabled](https://img.shields.io/badge/Enabled-238636?style=flat-square) |
| Startup & Experience | Home Onboarding | ``DC\FTEDialog`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Organize Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Redaction Onboarding | ``AVGeneral\cAV2ToolDiscoveryWalkthrough`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Show About Dialog | ``DC\Originals`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Show Getting Started | ``DC\HomeWelcome`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Startup & Experience | Viewer Onboarding | ``DC\FTEDialog`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Upsell | Acrobat App Promo | ``cServices\cAcrobatApp`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Upsell | Scan App Promo | ``cServices\cScanApp`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |
| Upsell | Show Trial Nag | ``DC\AVGeneral`` | Set to ![Disabled](https://img.shields.io/badge/Disabled-f85149?style=flat-square) |

---

**Sharing & responsibility** — Built for the community, shared with good intentions. Use at your own risk. The author accepts no responsibility for any outcomes resulting from the use of these files. Always verify registry paths and values, and test in a safe environment first. If you find an issue or have a suggestion, contributions are welcome.