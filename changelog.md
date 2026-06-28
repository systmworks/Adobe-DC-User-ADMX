<p align="center"><a href="https://buymeacoffee.com/systmworks"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="45" alt="Buy me a coffee"></a></p>

> I have spent many, many hours creating and testing this ADMX. If it helps you please consider buying me a Coffee :)

[<- Back to Documentation](README.md)

# Changelog

Settings changes across User ADMX versions. Only new, renamed, or reclassified settings are listed — internal script and formatting changes are omitted.

---

## v1.6 — 28 Jun 2026

**495 policies** (255 Acrobat DC + 240 Reader DC), up from 484 in v1.5.

### HKCU attachment lockdown (Reader + Acrobat)

**New user policies** under **Security: Trust & Permissions** — complementary HKCU controls for PDF file attachment behaviour (not a substitute for HKLM `FeatureLockDown` lockdown):

| Setting | ValueName | Suggested hardening |
|---|---|---|
| Open Non-PDF Attachments | `bAllowOpenFile` | Disabled → DWORD **0** |
| Secure Open Attachments | `bSecureOpenFile` | Enabled → DWORD **1** |

*Thanks to **[@CyberChelonian](https://github.com/CyberChelonian)** for [issue #4](https://github.com/systmworks/Adobe-DC-ADMX/issues/4) on the Computer ADMX repo (mis-filed as HKCU; addressed here in the User ADMX line).*

Adobe PrefRef labels these as version 10.x; community verification on current DC — test in your environment before production rollout.

### Reader Outlook Protected View

**New Reader DC policy** under **Security: Execution & Protection**:

| Setting | ValueName | Notes |
|---|---|---|
| Outlook Protected View | `bEnableAlwaysOutlookAttachmentProtectedView` | New for **Reader DC**; Enabled → DWORD **0** (Protected View on for Outlook attachments). Acrobat DC was already present from v1.4. |

*Thanks to **[@CyberChelonian](https://github.com/CyberChelonian)** for [issue #5](https://github.com/systmworks/Adobe-DC-ADMX/issues/5). Adobe documentation shows the Acrobat icon only; Reader path included per community request — verify Reader behaviour in your environment.*

### Microsoft Purview (MIP) — HKCU preferences only

**New category:** **Microsoft Purview (MIP)** — per-user `HKCU` preferences under `MicrosoftAIP` (not `FeatureLockDown` machine lockdown):

| Setting | ValueName |
|---|---|
| Show Document Message Bar (MIP) | `bShowDMB` |
| MIP Policy Authentication | `bEnablePolicyAuthentication` |
| MIP Logging | `bEnableLogging` |

*Thanks to **[@virtitnerd](https://github.com/virtitnerd)** for [issue #8](https://github.com/systmworks/Adobe-DC-ADMX/issues/8). This release covers the **HKCU `MicrosoftAIP`** slice of that request only. HKLM `FeatureLockDown` MIP lockdown policies (`bMIPLabelling`, `bMIPCheckPolicyOnDocSave`, `iMIPCloud`, `bMIPExternalAuthAdmin`, `bEnableDKEAdmin`, `bSilentAuth`) remain in scope for the **Computer ADMX** repo.*

See [readme in v1.6 (User)](../v1.6%20(User)/readme.md).

| ADMX File | Policies |
|---|---:|
| `AdobeDC_User.admx` + ADML | 495 |

---

## v1.5 — 28 Jun 2026

**No new policies** (484 unchanged). ADML generation fix: empty `presentationTable` omitted when there are no presentation entries, resolving Windows Server 2019 Group Policy Management Console import failures reported against v1.4.

*Thanks to **[@raschle](https://github.com/raschle)** for [PR #1](https://github.com/systmworks/Adobe-DC-User-ADMX/pull/1) identifying the WS2019 GPMC load failure.*

See [readme in v1.5 (User)](../v1.5%20(User)/readme.md).

---

## v1.4 — 7 May 2026

**No policy inventory change** (484 policies). Revision metadata aligned to **1.4** across ADMX, ADML, and `minRequiredRevision` for Group Policy and Intune consistency.

See [readme in v1.4 (User)](../v1.4%20(User)/readme.md).
