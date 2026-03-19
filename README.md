# MUV VPN — Releases

Download the latest installer for your platform from the [Releases](../../releases) page.


## Windows

1. Download `MUV-VPN-Setup-x.x.x.exe`
2. Run the installer
3. If Windows Defender shows a warning, click **More info → Run anyway**
4. Launch MUV VPN from the Start menu

## macOS

1. Download `MUV-VPN-x.x.x-arm64.dmg`
2. Open the DMG and drag MUV VPN to Applications
3. Run this once in Terminal to bypass Gatekeeper:
   ```bash
   xattr -cr "/Applications/MUV VPN.app"
   ```
4. Launch MUV VPN from Applications



## Updates

The app checks for updates automatically on launch and will prompt you to restart when a new version is available.

| Platform | Auto-update |
|---|---|
| Windows | Works without signing |
| macOS | **Does not work** — manually download and install each new `.dmg` release, then re-run `xattr -cr "/Applications/MUV VPN.app"`. |
