# MUV VPN

MUV VPN is a desktop application that connects you securely to MUV Edge devices over WireGuard.

Download the latest installer for your platform from the [Releases](../../releases) page.

---

## Installation

### Windows

1. Download `MUV-VPN-Setup-x.x.x.exe`
2. Run the installer (you can choose the install directory)
3. If Windows SmartScreen / Defender shows a warning, click **More info → Run anyway**
4. Launch **MUV VPN** from the Start menu

> **Note:** The app needs administrator privileges to manage the WireGuard tunnel service. You may see a UAC prompt when connecting for the first time. Running the app as Administrator avoids this prompt entirely.

**Prerequisite:** [WireGuard for Windows](https://www.wireguard.com/install/) must be installed.

---

### macOS

> **Supported:** Apple Silicon (arm64) only.

1. Download `MUV-VPN-x.x.x-arm64.dmg`
2. Open the DMG and drag **MUV VPN** to Applications
3. Run this once in Terminal to allow the app to open (required because the app is not code-signed):
   ```bash
   xattr -cr "/Applications/MUV VPN.app"
   ```
4. Launch **MUV VPN** from Applications

**Prerequisite:** `wireguard-tools` must be installed via Homebrew:
```bash
brew install wireguard-tools
```

When connecting, macOS will show a system password dialog to bring up the WireGuard interface — this is expected.

---

## Updates

The app checks for updates automatically on launch.

| Platform | Auto-update |
|---|---|
| Windows | Updates download silently in the background. You will be prompted to restart when a new version is ready. |
| macOS | **Auto-update is not available** (the app is not code-signed). Download and install each new `.dmg` manually, then re-run `xattr -cr "/Applications/MUV VPN.app"`. |

---

## Troubleshooting

### Windows — "Port already in use" error
Another MUV VPN window or process is holding port 51821. Quit all MUV VPN instances and try again.

### macOS — App won't open after update
Re-run the Gatekeeper bypass after every new installation:
```bash
xattr -cr "/Applications/MUV VPN.app"
```

### macOS — "wg-quick not found" error
Install WireGuard tools:
```bash
brew install wireguard-tools
```

### macOS — "muv0 already exists" on reconnect
This can happen if the app crashed without cleaning up. The app handles this automatically on the next connect attempt (it runs `wg-quick down` before `up`).
