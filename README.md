![Facebook Watcher](docs/assets/banner.svg)

# Facebook Watcher

**Find it on Facebook. Keep it in your archive.**

Turn Facebook Marketplace searches and groups into a searchable archive of listings, prices, photos and observed changes. Find saved listings later, even when Facebook is offline.

[**Download Facebook Watcher**](https://github.com/VelocityCubed/FacebookWatcher-Releases/releases/latest) · [Installation](docs/installation.md) · [User guide](docs/user-guide.md) · [Troubleshooting](docs/troubleshooting.md)

![Facebook Watcher archive with sample listings](docs/assets/archive-preview.png)

_App preview using synthetic sample listings. Your archive starts empty._

## Download

Open the [latest release](https://github.com/VelocityCubed/FacebookWatcher-Releases/releases/latest), expand **Assets**, and choose your installer:

| Your computer                                | Download                                   |
| -------------------------------------------- | ------------------------------------------ |
| Mac with Apple silicon (M1, M2, M3 or newer) | `FacebookWatcher-VERSION-darwin-arm64.dmg` |
| Mac with an Intel processor                  | `FacebookWatcher-VERSION-darwin-x64.dmg`   |
| Windows x64                                  | `FacebookWatcher-VERSION-win32-x64.exe`    |

On a Mac, **Apple menu → About This Mac** identifies your chip or processor. You do not need Node.js, Git, a separate browser installation or a GitHub account to download the app. Linux and Windows ARM installers are not provided.

**Current release:** [v0.1.2](https://github.com/VelocityCubed/FacebookWatcher-Releases/releases/tag/v0.1.2) includes the public updater. If you use v0.1.1, download and install v0.1.2 manually once. Later updates can use **App updates** without a GitHub token. Mac apps are unsigned and not notarized; initial installation follows normal macOS approval rules. Read the notes on the release you install.

## What you can do

- **Watch Marketplace searches and groups.** Collect listings your Facebook account can access on a schedule you control.
- **Search your archive.** Filter by words, source, price, location and date, and revisit saved descriptions and images.
- **Track observed changes.** Keep the prices and details seen during successful scans.
- **Build Smart watches.** Filter shared group indexes or review AI-generated search plans before saving them.
- **Compare retail products.** Keep reference prices and review possible second-hand matches.
- **Keep useful results.** Dismiss irrelevant listings, block recognized sellers, export CSV files and back up your archive.

## Get started in five steps

1. [Install the app](docs/installation.md) for your computer.
2. Choose **Connect Facebook** and sign in directly in the dedicated Facebook browser.
3. Add a Marketplace search or Facebook group in **Watch sources**.
4. Run **Scan now**, then check **Activity** for the result.
5. Browse **Archive** and use search and filters to find saved listings.

Leave the app running for scheduled collection. Closing its window keeps it in the tray; choosing **Quit** stops its local watcher. A sleeping or powered-off computer cannot collect listings.

## Help and guides

- [Install, upgrade and uninstall](docs/installation.md)
- [User guide: sources, groups, searches, retail products and backups](docs/user-guide.md)
- [Troubleshooting and recovery](docs/troubleshooting.md)
- [Data and privacy](docs/privacy.md)
- [Release history and downloads](https://github.com/VelocityCubed/FacebookWatcher-Releases/releases)
- [Report a problem](https://github.com/VelocityCubed/FacebookWatcher-Releases/issues)

Include your app version, operating system, steps to reproduce and the message shown in **Activity** when reporting a problem. Public issues are visible to everyone: remove passwords, tokens, private group links, personal listing information and other sensitive details.

## About this repository

This is the public home for Facebook Watcher downloads, user documentation and release notes. Application source code and build automation are maintained separately. GitHub's automatically generated **Source code** archives contain only this repository's documentation; use the DMG or EXE installer to install the app.

Facebook Watcher is an independent application and is not affiliated with or endorsed by Meta or Facebook. Scans are bounded snapshots of what your account can see, not a guarantee of complete coverage or item availability. Use the app in line with the permissions and terms that apply to your account and the content you access.
