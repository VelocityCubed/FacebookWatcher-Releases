# Data and privacy

[← Home](../README.md) · [User guide](user-guide.md)

## Local storage

The desktop watcher keeps its archive, downloaded images and dedicated Facebook browser profile on your computer. Facebook sign-in takes place directly in the dedicated browser, not in a password form owned by Facebook Watcher. Your regular browser profile is not imported.

Default desktop archive directories:

| Platform | Watcher data                                            |
| -------- | ------------------------------------------------------- |
| macOS    | `~/Library/Application Support/FacebookWatcher/watcher` |
| Windows  | `%APPDATA%/FacebookWatcher/watcher`                     |

Keep one watcher per archive directory and use local storage for an active archive. Protect this directory as you would your Facebook session and personal files.

## Connections

Facebook requests use the account you connect and only its accessible content. Public update checks contact GitHub, and update packages download from GitHub's release infrastructure. Opening original listings or retailer references contacts those sites.

AI planning is optional. If you connect an OpenAI provider, planning sends your request and selected group IDs/names with the provided currency/context. It does not send Facebook credentials, indexed post text, seller/member profiles or images as planner input. Review the selected connection and its billing choice before generating a plan. Saved plans contain rules and search associations, not provider tokens.

## Backups and exports

A `.fwatch` backup includes archive data and downloaded images, while excluding Facebook browser profiles and credentials. Treat backups and CSV exports as sensitive: listings can contain personal information. Store them somewhere you control and share them deliberately.

Restoring replaces the existing archive and settings. It does not restore Facebook login. Deleting a saved filter or dismissing a listing does not delete all underlying archive records. Blocking a seller hides recognized matches while retaining records; unblocking restores visibility.

## Public reports

This repository and its issues are public. Do not post tokens, passwords, private group URLs, personal listing details, browser profiles or backups. Remove sensitive information from screenshots before sharing.

Facebook Watcher is independent of Meta and Facebook. Access to a page does not by itself grant permission for automated collection; follow the permissions and terms that apply to your account and the content you access.
