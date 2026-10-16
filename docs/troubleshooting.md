# Troubleshooting

[← Home](../README.md) · [Installation](installation.md) · [User guide](user-guide.md)

## The app will not install or open

Check that you selected the correct processor download. Install a Mac app into Applications and eject the DMG before opening it. On Windows, use the Setup EXE. Re-download an incomplete or damaged installer from the release page. Unsigned apps may require operating-system approval; follow your computer's policy and the [installation guide](installation.md).

## Facebook needs login or a security check

Choose **Open Facebook**, complete the prompt in the dedicated browser, then reconnect. Enter your Facebook password only on Facebook's own page. Do not repeatedly retry a blocked session. The app cannot bypass account restrictions or grant group access.

**Remove saved login** deletes the watcher's dedicated Facebook profile while retaining the archive. Finish or cancel scans before using it. Your normal browser's login is separate.

## A scan saves nothing or stops early

- Confirm the source is a Marketplace search or group homepage, not an individual listing URL.
- Open it with the connected Facebook account and confirm access.
- Check matching words, date limits, price/currency rules and whether the source is paused.
- Review **Activity** for candidate limits, unavailable details, failures or cancellations.
- For group sources, check **Group indexes**: pausing a Smart watch filter does not stop or start its shared collector.

A scan is a bounded snapshot. Partial scans can save listings; a visible end of a feed does not prove complete historical coverage. An item disappearing from a search does not prove it was sold.

## Scheduled scans are not running

Keep the computer awake and the app running. Closing the window keeps the watcher in the tray; quitting stops it. Check Facebook connection status and source schedules. New group indexes and generated watches may start paused. Open **Activity** to see queued or running work.

## A listing is missing from search

Clear search filters, check the selected source, date basis and currency, and try **Show dismissed**. Check **Blocked sellers**. A missing price is unknown rather than zero, and unknown facts can appear separately from strict Smart watch matches. The archive can only show records successfully collected.

## Photos or seller details are missing

Facebook may not expose every image or owner. Existing records may need a successful detail refresh. Anonymous authors and ambiguous identities cannot be blocked. Downloaded photos can be browsed offline; unavailable images cannot be recovered from an offline archive.

## Updates cannot be found or downloaded

v0.1.1 still points to private releases and needs one manual upgrade to v0.1.2 or newer to use the public feed. For a newer app, check your connection, wait if GitHub limits requests, and remove a saved GitHub update token if it is no longer valid. Public downloads do not require a token. Draft and prerelease versions are ignored.

On a Mac, use a writable Applications directory, quit duplicate copies and allow enough free disk space to retain the old and new app. Do not run from the DMG or Downloads. On Windows, use the installed Setup version. Finish or cancel scans before **Restart to install**. If a recovery message appears, follow it before deleting any retained app copies.

## Backup or restore is unavailable

Wait for scans to finish or cancel them from **Activity**. The current `.fwatch` backup format is limited to 128 MB. CSV exports are limited to 10,000 listings and are not a complete backup. Restore replaces the current archive and source settings; make a backup first. Reconnect Facebook after restoring and review source schedules before reconnecting if you do not want overdue scans to resume.

## AI planning or retail import fails

Check the selected OpenAI connection and its permission or usage status. API billing and ChatGPT plan usage are separate choices; the app does not switch automatically. Retry an incomplete plan and review all rules before saving. You can create sources without AI.

Retail pages may block imports or omit a reliable price. Enter verified product details manually. Check model, variant, quantity, currency and reference freshness before confirming a match or savings estimate.

## Report a problem

Open a [public issue](https://github.com/VelocityCubed/FacebookWatcher-Releases/issues) with the installed version, operating system and processor, steps to reproduce, expected result and actual message. Screenshots help if they contain no private information. Never attach credentials, browser profiles or archive backups to a public issue.
