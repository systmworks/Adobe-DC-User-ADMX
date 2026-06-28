<p align="center"><a href="https://buymeacoffee.com/systmworks"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="45" alt="Buy me a coffee"></a></p>

> I have spent many, many hours creating and testing this ADMX. If it helps you please consider buying me a Coffee :)

# v1.6 (User) — Adobe DC ADMX/ADML for Intune (HKCU Preferences)

28 Jun 2026

This ADMX targets **HKCU user preferences** for Adobe Acrobat DC and Reader DC. It is designed to complement the existing HKLM-based ADMX files (x64/x86) and covers settings that are not already managed through lockable machine policies.

## What is new in v1.6

| Area | Change |
|------|--------|
| **HKCU attachment lockdown** | **Open Non-PDF Attachments** (`bAllowOpenFile`) and **Secure Open Attachments** (`bSecureOpenFile`) under Security: Trust & Permissions (Acrobat + Reader). Hardening pair: disable open-in-native-app and enable secure-open (block non-PDF attachments). |
| **Reader Outlook Protected View** | **Outlook Protected View** (`bEnableAlwaysOutlookAttachmentProtectedView`) extended to Reader DC (previously Acrobat-only). |
| **Microsoft Purview (MIP)** | New category with **Show Document Message Bar (MIP)** (`bShowDMB`), **MIP Policy Authentication** (`bEnablePolicyAuthentication`), and **MIP Logging** (`bEnableLogging`) for Acrobat + Reader. Per-user `MicrosoftAIP` preferences, not HKLM lockdown. |
| **Revision** | ADMX `revision`, ADML `revision`, and `<resources minRequiredRevision>` are all **1.6**. |
| **Policy inventory** | **495** policies (**255** Acrobat DC + **240** Reader DC), up from 484 in v1.5. |

**Thanks** to community members **CyberChelonian** (attachment lockdown and Reader Outlook Protected View requests) and **virtitnerd** (MIP HKCU preference coverage).

**Compared to v1.5:** inherits the WS2019 GPMC `presentationTable` fix. v1.5 remains available for deployments that do not need the new policies.

### Caveats for new policies

- **Attachment lockdown (`bAllowOpenFile` / `bSecureOpenFile`):** Adobe PrefRef labels these as version 10.x; community reports confirm they work on current DC. Test in your environment before production rollout.
- **Reader Outlook Protected View:** Adobe documentation shows the Acrobat icon only; Reader path is included per community request. Verify Reader behaviour in your environment.
- **MIP preferences:** These are per-user configuration under `MicrosoftAIP`, not FeatureLockDown-style machine lockdown. HKLM MIP lockdown policies remain in the Computer ADMX scope.

## Files

| File | Scope | Policies |
|------|-------|----------|
| `AdobeDC_User.admx` + `en-US/AdobeDC_User.adml` | Acrobat DC (User) + Reader DC (User) | 495 (255 Acrobat + 240 Reader) |

## Namespace

| Attribute | Value |
|-----------|-------|
| Prefix | `Adobe_User` |
| Namespace URI | `Adobe.Policies.Adobe_User` |
| Policy class | `Both` |
| ADMX / ADML `revision` | 1.6 |
| `minRequiredRevision` (`resources`) | 1.6 |

This namespace is distinct from the HKLM ADMX files (`Adobe.Policies.AdobeDC`) and can be uploaded alongside them without conflict.

## Intune folder structure

```
Administrative Templates
└── Adobe (User)
    ├── Acrobat DC (User)
    │   ├── Context, Tools & Search
    │   ├── Documents, Editing & Accessibility
    │   ├── Microsoft Purview (MIP)
    │   ├── Security: Execution & Protection
    │   ├── Security: Trust & Permissions
    │   ├── Sharing & Features
    │   ├── Startup & Experience
    │   ├── Updates & Desktop Integration
    │   └── Upsell
    └── Reader DC (User)
        ├── Context, Tools & Search
        ├── Documents, Editing & Accessibility
        ├── Microsoft Purview (MIP)
        ├── Security: Execution & Protection
        ├── Security: Trust & Permissions
        ├── Sharing & Features
        ├── Startup & Experience
        ├── Updates & Desktop Integration
        └── Upsell
```

Acrobat DC (User) and Reader DC (User) each expose **nine** policy categories. There is no **Cloud & Connectors** branch in this bundle (AVEntitlement-related prefs are excluded as application-managed).

## Source data

Settings were sourced from the Adobe Preference Reference documentation and Adobe enterprise MIP guidance:

- <https://www.adobe.com/devnet-docs/acrobatetk/tools/PrefRef/Windows/>
- <https://helpx.adobe.com/enterprise/kb/mpip-support-acrobat.html>

Only HKCU-specific settings are included. Any setting that already has a lockable HKLM policy (covered by the HKLM ADMX) was excluded to avoid duplication.

Each DWORD toggle policy maps Group Policy **Enabled** and **Disabled** to explicit registry DWORD values (the same pattern as the HKLM ADMX). A small number of policies include optional recommended-security notes and DISA STIG cross-references in their description text.

## Filtering (unchanged)

The following categories of settings were excluded:

- **HKLM duplicates** — settings already covered by the lockable HKLM ADMX.
- **Application-managed** — read-only values generated by the application at runtime.
- **Pre-DC versions** — settings whose version range indicates they do not apply to DC.
- **Template/placeholder paths** — settings with registry paths containing placeholders.
- **Malformed paths** — entries with embedded `HKLM\` fragments or forward slashes in the HKCU path.
- **Non-DWORD types** — only REG_DWORD settings are emitted as ADMX toggle policies.

## Prior release highlights (v1.5)

v1.5 fixed WS2019 Group Policy Management Console import by omitting an empty `presentationTable` from the ADML. Policy count was **484**. See the **v1.5 (User)** readme for details.

## Known issues

- **`class="Both"`**: Intune does not support `class="User"` for custom ADMX ingestion. All policies use `class="Both"` as a workaround. When assigned to a **user group** in Intune, the settings write to HKCU as intended. When assigned to a device group, they write to HKLM at the same path — which is not the intended use for these preference settings.
- **Skipped (unresolvable paths)**: DWORD entries whose HKCU paths contain placeholders are omitted from this ADMX.
- **Non-DWORD types excluded**: REG_SZ reference entries remain in source data for documentation alignment; they are not emitted as ADMX toggle policies.
- **No Cloud & Connectors category**: AVEntitlement-related settings were excluded as application-managed.

## Intune upload

1. Remove any existing ADMX entry for the `Adobe.Policies.Adobe_User` namespace before uploading, or Intune will report a conflict.
2. Upload `AdobeDC_User.admx` and `en-US/AdobeDC_User.adml` together.
3. The HKLM ADMX files use a separate namespace (`Adobe.Policies.AdobeDC`) and do not need to be removed.
4. Assign the resulting policy to a **user group** to write settings to HKCU.
5. If upload returns a generic **Command error, check your command query...**, remove any failed import for this namespace, confirm the ADML file is ASCII-only and within Intune's size limit, and retry uploading both ADMX and ADML together.

---

**Sharing & responsibility** — Built for the community, shared with good intentions. Use at your own risk. The author accepts no responsibility for any outcomes resulting from the use of these files. Always verify registry paths and values, and test in a safe environment first. If you find an issue or have a suggestion, contributions are welcome.
