# Privacy Policy

**Last updated: June 2, 2026**

## Overview

Xell ("the app") is an open-source SSH workspace for developers. This policy explains what data the app handles and how it is stored.

## Data We Collect

**Xell does not collect, transmit, or share any personal data.**

All data stays on your device. There are no analytics, no telemetry, no tracking, and no cloud sync.

## Data Stored on Your Device

The app stores the following data locally:

### Non-sensitive data (via Android SharedPreferences)
- SSH host configurations (name, hostname, port, username, tags)
- App settings (theme, terminal font size)
- Recent connections list

### Sensitive data (via Android Keystore / encrypted storage)
- SSH passwords (encrypted, never leaves your device)
- SSH private key passphrases (encrypted, never leaves your device)

Private key **files** are never copied or stored by the app — only the file path you select is saved.

## Network Access

The app connects to SSH servers you explicitly configure. No other network connections are made. The app does not communicate with any Xell or third-party servers.

## Permissions

| Permission | Reason |
|-----------|--------|
| `INTERNET` | Required to establish SSH connections to your servers |

## Data Sharing

Xell does not share any data with third parties. Ever.

## Data Deletion

To delete all app data, use the "Clear local data" option in Settings, or uninstall the app. Uninstalling removes all locally stored hosts, credentials, and preferences.

## Children's Privacy

Xell is a developer tool not intended for use by children under 13.

## Open Source

Xell is open source. You can review the full source code to verify these claims.

## Contact

If you have questions about this privacy policy, open an issue on the project's GitHub repository.
