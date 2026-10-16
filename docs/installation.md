# Install and update Facebook Watcher

[← Home](../README.md) · [User guide](user-guide.md) · [Troubleshooting](troubleshooting.md)

## Choose the right download

Download from [GitHub Releases](https://github.com/VelocityCubed/FacebookWatcher-Releases/releases/latest). The desktop distribution includes its runtime and dedicated Chromium browser. You need an internet connection and a Facebook account that can access the sources you choose. An OpenAI connection is optional and is used only for AI planning.

| Computer          | Installer                         |
| ----------------- | --------------------------------- |
| Apple silicon Mac | File ending in `darwin-arm64.dmg` |
| Intel Mac         | File ending in `darwin-x64.dmg`   |
| Windows x64       | File ending in `win32-x64.exe`    |

The `.zip`, `.nupkg` and `RELEASES` files support updates; choose the DMG or EXE for first installation. GitHub's **Source code** downloads are documentation archives, not the app.

## macOS

1. Open the downloaded DMG.
2. Drag **FacebookWatcher.app** into **Applications**. Do not run it directly from the DMG.
3. Eject the DMG and open Facebook Watcher from Applications.
4. If macOS identifies the app as unsigned or from an unidentified developer, follow the approval options in **System Settings → Privacy & Security**, if offered, after verifying where you downloaded it. Do not disable macOS security protections.

The v0.1.1 apps are unsigned and not notarized. A Mac managed by an organization may prevent installation. If macOS says the app is damaged, download it again, confirm the processor type and consult [troubleshooting](troubleshooting.md).

For future in-app updates, the app must be in a writable Applications directory (`/Applications` or your own `~/Applications`). The updater does not ask for administrator access.

## Windows

1. Run the downloaded `FacebookWatcher-VERSION-win32-x64.exe` setup installer.
2. Follow the installer and start Facebook Watcher from the Start menu.
3. If Windows shows an unknown-publisher warning, verify the download source and follow your computer's installation policy.

Use the Setup installer rather than copying an EXE out of an app directory. The installed version contains the Windows update support.

## First launch

Choose **Connect Facebook**. A separate browser opens for Facebook sign-in and any security prompts. Return to the app when connected. Your regular browser profile is not imported. See the [user guide](user-guide.md) to add a source and run the first scan.

## Updates and the move to public releases

**v0.1.1 is a legacy manual-installation release.** Its updater points to the private repository. Download and install the first public-feed version manually when it becomes available. Copying the v0.1.1 files to a public release does not change the updater inside those files.

In versions containing the new public updater:

1. Open the workspace menu's **App updates** card or **Update settings & details**.
2. Choose **Check now** or **Check for updates**.
3. Leave **Automatically check and download updates** enabled for checks shortly after launch and every six hours.
4. Finish or cancel active scans, then choose **Restart to install** when the update is ready.

Public update checks do not need a GitHub token. Remove an old saved update credential if it is no longer needed. GitHub may temporarily limit requests; wait and retry. Only newer stable releases are offered, not draft or prerelease versions.

The newer Mac updater verifies package size, checksum, app identity and architecture before staging the update. It supports unsigned releases and requires an explicit restart action; initial macOS installation approval still applies. Windows uses its installed Squirrel updater.

## Manual upgrades

Create a **Backup** first, then quit the app. On macOS, replace the app in Applications with the newly downloaded version. On Windows, run the newer Setup installer. Archive and login data live separately from the app. Avoid downgrading: an older version may not understand newer archive data.

## Uninstall

Quit Facebook Watcher first. On macOS, remove the app from Applications. On Windows, uninstall it through **Settings → Apps**. App files and archive data are separate; inspect the data locations in [Data and privacy](privacy.md) if you also want to remove retained data. Back up anything you need before deleting it. Deleting the browser profile removes the watcher's saved Facebook login.
