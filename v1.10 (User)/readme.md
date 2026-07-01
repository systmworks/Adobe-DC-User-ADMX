<p align="center"><a href="https://buymeacoffee.com/systmworks"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="45" alt="Buy me a coffee"></a></p>

> I have spent many, many hours creating and testing this ADMX. If it helps you please consider buying me a Coffee :)

# v1.10 (User) — Adobe DC ADMX/ADML for Intune (HKCU Preferences)

1 Jul 2026

This ADMX targets **HKCU user preferences** for Adobe Acrobat DC and Reader DC. It complements the existing HKLM-based ADMX files (x64/x86) and covers settings that are not already managed through lockable machine policies.

**Current production release.** Supersedes [v1.9 (User)](../v1.9%20(User)/readme.md) for new Intune deployments.

## What is new in v1.10

| Area | Change |
|------|--------|
| **Intune display names** | All **501** leaf policy names suffixed with ` (User)` — matches Microsoft convention for user-scope administrative templates and helps admins distinguish user vs machine settings when both appear in the same Intune profile (imported ADMX does not show hive or category path in the configuration list). |
| **Revision** | ADMX `revision`, ADML `revision`, and `<resources minRequiredRevision>` are all **1.10**. |
| **Policy inventory** | **501** policies (**258** Acrobat DC + **243** Reader DC) — unchanged from v1.9. |

**Compared to v1.9:** same policy set, registry keys, ADMX `name` attributes, categories, and explain text. Only leaf **display labels** change (each gains ` (User)`). Re-upload v1.10 to replace the `Adobe.Policies.Adobe_User` namespace import.

### Why ` (User)` on every setting?

Imported custom ADMX shows ADML display strings in the profile configuration view. Unlike built-in Settings Catalog templates, Intune does **not** auto-append `(User)` to imported policy names and does **not** show HKCU/HKLM or category breadcrumbs there. When user and machine Adobe settings are mixed in one profile, the suffix makes scope obvious at a glance — e.g. `Show Splash Screen (User)` vs machine settings without that suffix.

Six names that already contained parentheses gain a second pair (e.g. `Show Document Message Bar (MIP) (User)`). This is cosmetic only.

## Files

| File | Scope | Policies |
|------|-------|----------|
| `AdobeDC_User.admx` + `en-US/AdobeDC_User.adml` | Acrobat DC + Reader DC under Adobe (User) | 501 (258 Acrobat + 243 Reader) |

Published policy reference tables: [Documentation](../Documentation/README.md).

## Namespace

| Attribute | Value |
|-----------|-------|
| Prefix | `Adobe_User` |
| Namespace URI | `Adobe.Policies.Adobe_User` |
| Policy class | `User` |
| ADMX / ADML `revision` | 1.10 |
| `minRequiredRevision` (`resources`) | 1.10 |

## Intune upload

1. **Remove** any existing ADMX entry for `Adobe.Policies.Adobe_User` before uploading — including failed or stuck imports.
2. Wait 2–5 minutes after deletion.
3. Upload `AdobeDC_User.admx` and `en-US/AdobeDC_User.adml` together.
4. Assign to a **user group** to write settings to HKCU.

---

**Sharing & responsibility** — Built for the community, shared with good intentions. Use at your own risk. The author accepts no responsibility for any outcomes resulting from the use of these files. Always verify registry paths and values, and test in a safe environment first. If you find an issue or have a suggestion, contributions are welcome.
