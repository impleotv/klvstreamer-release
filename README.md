<div align="center">
  <img src="images/impleo_logo.png" alt="ImpleoTV logo">
</div>

# KlvStreamer 2.0.0

**KlvStreamer** re-streams STANAG 4609 transport-stream files over IP networks.
Build playlists of CBR or VBR files, send them over unicast or multicast UDP,
preview video and KLV metadata, and inspect bitrate statistics.

[Product information](https://impleotv.com/products/applications/klvstreamer) ·
[Release notes](CHANGELOG.md) ·
[All releases](https://github.com/impleotv/klvstreamer-release/releases)

## Download

| Version | Installer |
| --- | --- |
| **2.0.0** | Awaiting code signing; download will be added when the signed installer is published. |

Version 2.0.0 uses a standalone **offline installer**. It includes .NET Framework
4.8, the required runtime libraries and DirectShow filters, the ImpleoTV video
decoder, and the User Guide.

**Installing an older version?** Open the [legacy installation instructions for
version 1.0.30 and earlier](LEGACY-INSTALLATION.md), including the original ZIP
download and manual prerequisite links.

## System Requirements

- Windows 10 or Windows 11 with support for 32-bit Windows applications.
- Administrator access to run setup.
- A web browser to open the User Guide.
- A network interface and a reachable UDP destination for streaming.

KlvStreamer is a **32-bit (x86)** application and also runs on 64-bit Windows.
Setup installs .NET Framework 4.8 only when version 4.8 or newer is missing.
The required Visual C++ runtime libraries and default preview decoder are bundled.
If you select a different decoder in **Options → Misc**, install it separately.

## Installation

1. Once version 2.0.0 is published, download `KlvStreamerSetup-2.0.0-x86.exe`
   from the [GitHub releases page](https://github.com/impleotv/klvstreamer-release/releases).
2. Close KlvStreamer, run the installer, and approve the administrator prompt.
3. Follow the setup wizard. On 64-bit Windows, the default installation folder is
   `C:\Program Files (x86)\ImpleoTV\KlvStreamer`.
4. If setup requests a restart, restart Windows and run the same installer again.
5. Start **KlvStreamer** from the **ImpleoTV** group in the Start menu.

After downloading the installer, installation and the bundled User Guide work
without an Internet connection. Open the guide through **Help → User Guide** or
the **KlvStreamer User Guide** Start menu shortcut.

### Upgrading from an Older Version

Back up your license file, any separate activation key, and your playlists before
upgrading. Close KlvStreamer and run the new installer. Setup detects and removes
the legacy MSI installation. License files, playlists, and settings stored outside
the installation folder are retained.

If Windows Installer is busy (error **1618**), let the other installation or
uninstallation finish, then click **Retry** or run setup again. Legacy MSI removal
logs are saved in `%LOCALAPPDATA%\ImpleoTV\KlvStreamer\SetupLogs`.

## Licensing

Without a valid license, streaming and preview sessions have a **three-minute
demo limit**. KlvStreamer accepts both legacy XML licenses with an activation key
and signed JWT licenses without a separate key.

### Request a License

1. On the target computer, open **Options → License**.
2. Use **Copy** beside **Node Info** to copy the complete `NI-KLVSTR-...` identifier.
3. Include that identifier when requesting a **KlvStreamer application license**
   through the [license request form](https://docs.google.com/forms/d/e/1FAIpQLSd_XW6bDsFce1G1cpds4gMQNlwNax0CvkWzcMbscxZ5rLaIbA/viewform).
   A KlvStreamer SDK license is a separate product license.

Send the Node Info value as text. If a license is locked to a computer, it must
match that computer. Existing legacy XML hardware locks remain supported.

### Import and Activate a License

Stop streaming before changing licenses. In **Options → License**, click
**Browse…** and select the supplied license file:

- **Signed JWT (`.jwt` or `.lic`):** validated during import; no activation key is
  required. Confirm **License Ok** and **Production (JWT)**.
- **Legacy XML (`.lic`):** import the file, paste the matching activation key into
  **Key**, and click **Apply**. Confirm **License Ok** and the licensed mode.

Review any restrictions under **Capabilities**, then click **OK**.

New license imports are stored in
`%LOCALAPPDATA%\ImpleoTV\KlvStreamer\KlvStrLicense.lic`, so importing a license
does not require administrator access. Replacing an imported license saves the
previous file as `KlvStrLicense.lic.bak`. Existing configured license locations and
the legacy ProgramData location remain supported.

## Check for Updates

Open **About → Check for Updates** to compare your installed version with the
latest stable GitHub release. The About dialog also links to the download page.
