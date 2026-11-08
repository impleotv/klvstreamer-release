# Release Notes

## 2.0.1 - 2026-11-08

- Signed offline installer, application binary, offline User Guide, and website help archives.
- Includes .NET Framework 4.8, runtime libraries, DirectShow filters, and the default ImpleoTV decoder.


## 2.0.0 — Pending Release

The installer is awaiting code signing. Version 2.0.0 is not yet published.

- Updated the Windows application to .NET Framework 4.8 (x86), with refreshed
  application and toolbar icons.
- Added a single offline EXE installer with the .NET 4.8 prerequisite, required
  Visual C++ runtime libraries, DirectShow filters, and default ImpleoTV decoder.
- Added migration from the legacy MSI installer, including retry handling when
  Windows Installer is busy.
- Added signed JWT licenses without a separate activation key while retaining
  existing XML licenses and their activation keys.
- Added the `NI-KLVSTR-` node identity and a copy button in the License tab.
  Existing XML hardware locks remain supported.
- Moved new license imports to the current Windows user's LocalAppData folder,
  with a backup when replacing a license.
- Added the offline User Guide and an **About → Check for Updates** action that
  checks the latest stable release on GitHub.
- Improved VBR pacing to prevent accumulating preview delay during bitrate
  changes.
- Fixed transport-packet alignment after seeking, final-packet delivery, and
  stopping paused streams.

### Installation

Download and run **KlvStreamerSetup-2.0.0-x86.exe**. Administrator access is
required. Windows 10 and Windows 11 are supported; the application is 32-bit.
The installer includes its prerequisites and can run offline. If a restart is
requested, restart Windows and run the installer again.

Back up your license, activation key (if applicable), and playlists before
upgrading. See the [current installation and licensing instructions](https://github.com/impleotv/klvstreamer-release#installation)
or the [archived instructions for version 1.0.30 and earlier](https://github.com/impleotv/klvstreamer-release/blob/master/LEGACY-INSTALLATION.md).

### Planned Release Assets

- `KlvStreamerSetup-2.0.0-x86.exe`: offline installer.
- `payload-sha256.json`: SHA-256 manifest for the files packaged in the installer.
- `SHA256SUMS.txt`: SHA-256 checksums for the installer and payload manifest.
