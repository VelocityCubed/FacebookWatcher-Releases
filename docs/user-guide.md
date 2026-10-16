# Facebook Watcher user guide

[← Home](../README.md) · [Install](installation.md) · [Troubleshooting](troubleshooting.md)

## The basic workflow

FacebookWatcher has four main concepts:

1. A **watch source** is a Marketplace search or Facebook group that the watcher checks.
2. A **scan** is one bounded collection of visible candidates from a source.
3. The **archive** is the local SQLite-backed collection of saved listings, images and observed changes.
4. A **retail product** is an optional reference product used to generate searches and compare archived candidates against retail or historical prices.

A normal first session is:

1. Connect Facebook in the watcher's dedicated browser.
2. Add a Marketplace search or group source.
3. Run a scan and review **Activity**.
4. Search and filter the saved listings in **Archive**.
5. Add more sources or a retail product as your workflow grows.

## First-time setup

Install the app using the [installation guide](installation.md). No developer tools are needed.

### Connect Facebook

1. Select **Connect Facebook** in the connection card.
2. Sign in in the separate Chromium window that opens. Enter your password and complete any Facebook security prompts there; FacebookWatcher does not ask for the password in its own interface.
3. Return to FacebookWatcher and wait for the status to show **Facebook connected**.

The watcher uses a dedicated browser profile on the host running the service. It does not import your normal browser profile. If the session expires or Facebook requests a security check, select **Open Facebook**, complete the required step, and reconnect.

Disconnecting with **Remove saved login** deletes the watcher's dedicated Facebook browser profile but does not delete the archive. Active scans must finish or be cancelled before the saved login can be removed.

### Keep monitoring running

Closing the desktop window keeps the local watcher running in the system tray, so scheduled scans and queued work can continue. Choose **Quit** from the app or tray menu when you want to stop the desktop-managed watcher. If you use a standalone service, closing the desktop client does not stop the service; stop that service separately. A stopped watcher pauses monitoring and resumes its normal recovery behavior when started again.

## Watch sources

### Add a source

Open **Watch sources** and select **Add watch source**. Enter:

| Field                  | Guidance                                                                                  |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| Name                   | Use a label you will recognize, such as `Office furniture` or `Audio groups`.             |
| Facebook URL           | Use a Marketplace search URL or the homepage of a Facebook group your account can access. |
| Scan every (minutes)   | Choose 5 minutes through 10,080 minutes (7 days). The default is 60 minutes.              |
| Items per scan         | Choose 1–200 visible candidates. The default is 50.                                       |
| Currency               | Choose a currency when Facebook displays an ambiguous price, or leave it to the listing.  |
| Matching words         | Optionally require words in the collected title or description, such as `Herman Miller`.  |
| Enable scheduled scans | Leave enabled to collect on the interval while the watcher is running.                    |

Examples:

```text
https://www.facebook.com/marketplace/search/?query=office%20chair
https://www.facebook.com/groups/YOUR_GROUP_ID/
```

An individual Marketplace listing URL is not a watch source. Save the source, then select **Scan now** when you want an immediate collection.

### Manage sources

For each source, **Watch sources** shows its type, interval, candidate limit, currency, last successful scan and latest status.

- **Scan now** queues one scan immediately.
- Pause or resume scheduled scans with the play/pause control.
- Edit the source when its URL, filter words, interval or candidate limit changes.
- Remove a source to stop future scans. Its already archived listings remain searchable.

Only one scan runs at a time for the watcher. Source changes are unavailable while that source has a queued or running job.

### Marketplace coverage and group indexes

New Marketplace sources use the South Africa coverage preset: twelve regional searches, newest-first ordering and a shared schedule/detail limit. Open **Edit → Search coverage** to choose custom towns and radii, add alternative phrases or keep a saved Facebook search. Coverage is bounded and reflects only results Facebook exposes; **View coverage** shows pending searches, queued details, failures and age-skipped items. Use **View coverage** to inspect the configured budgets and queued work.

Group sources can be shared through a **Group index**. The collector gathers supported group posts once, then Smart watches and local filters can reuse that indexed content with their own words, price and location rules. Use **Group indexes** to control the shared collector and **Smart watches** to control each filter; pausing a filter does not stop shared collection.

### Understand scan results

Scans are bounded snapshots of results visible to the logged-in account. They are not complete inventories. The item limit can stop a scan before all visible results are inspected, and Facebook may make some details or images unavailable.

Open **Activity** to review the last 100 scan attempts. Each entry can show:

- how many candidates were inspected and saved;
- whether the scan completed, failed, was cancelled or is still running;
- unavailable details or images; and
- whether the configured candidate limit was reached.

You can cancel a queued or running scan from **Activity**. A partial scan can still save useful listings.

## Search and review the archive

### Search and filter

Open **Archive** and type in the search box to search saved titles and descriptions. Use the quick filters for source and currency, or open **Filters** for:

- minimum and maximum price;
- location;
- availability status;
- whether dates mean **First seen** or **Posted on Facebook**; and
- a local-timezone date range.

Sort results by newest first-seen date, lowest price or highest price. Results are paginated in groups of 30. **Clear filters** returns to the full archive.

The archive is searchable when Facebook is offline or the Facebook session needs attention.

### Open a listing

Select a listing card to see:

- the description, location and displayed price;
- its original Facebook link;
- archived images that were successfully downloaded; and
  - observed prices and update timestamps.

Select **View on Facebook** to open the original listing externally. A missing price remains unknown. Currency filters do not convert exchange rates. If a listing disappears from a feed, FacebookWatcher does not infer that it was sold.

Repeated photos appear once in the gallery, including duplicates already in the archive. Rescans reuse saved photos when Facebook refreshes their image URLs.

Posting-date precision is preserved. Exact dates, date-only values, relative estimates and unknown dates remain distinguishable in the detail view.

## Retail watchlist

The retail watchlist is optional. It helps turn a product you can buy at retail into Facebook searches and a review queue for possible second-hand matches.

### Save a retail product

1. Open **Retail watchlist** and select **Add retail product**.
2. Paste a full Amazon product URL containing an ASIN (`/dp/...` or `/gp/product/...`), or a Takealot listing URL ending in `PLID...`.
3. Select **Import details** and review the title, brand, model, variant and pack quantity. You can enter the fields manually if the retailer page is blocked or ambiguous.
4. Add alternative model spellings, one per line, when sellers use different names.
5. Enter the current price and currency when known, then select **Save product**.

Shortened links and search-result links are unsupported. Import does not use Facebook cookies. A blocked, expired or ambiguous retailer offer can leave the price blank; do not treat a recommended price, coupon, delivery fee or membership price as the reference unless you have verified it yourself.

### Generate Facebook watches

1. Open the saved product and review **Facebook searches**.
2. Edit the proposed queries, with one query per line and up to five queries.
3. Select **Enable new watch schedules** only if the new Marketplace watches should start scheduled. New watches are otherwise paused.
4. Select **Create Facebook watches**.
5. Connect Facebook, then manage intervals, scans and group sources in **Watch sources**.

Identical generated searches share a watch. Reusing an existing watch preserves its current interval, item limit, currency and enabled state. **Unlink** removes the product association but keeps the watch and its archived listings.

### Review candidates

After the generated watches have collected listings, open the product and select **Refresh candidates**. For each candidate:

- inspect the listing, variant, condition, quantity and location;
- treat **Model match** and **Possible match** as suggestions, not confirmed deals;
- select **Confirm match** only when the identity is correct;
- select **Dismiss** for an incorrect match; or
- select **Reset review** when you want the automatic assessment again.

Unconfirmed savings are labelled **Estimate until confirmed**. Comparisons can be blocked by a different model generation, capacity, colour, accessory, pack quantity or currency. Candidate discovery considers the newest 5,000 archived listings plus listings with saved reviews, and candidate pages show up to 50 items.

Savings are calculated from the saved reference price:

```text
(reference price - Facebook asking price) / reference price * 100
```

Check condition, warranty, delivery and fees yourself. An asking price above the reference is shown as above reference, and unknown or incompatible prices do not produce savings.

### Refresh prices and history references

Select **Refresh retail price** to import again or enter a verified price manually. Each saved price becomes a dated snapshot; a failed import does not erase earlier snapshots.

For historical context, select **Add history reference** and link the matching product page on [Serval Tracker](https://www.servaltracker.com/) or [Buck Cheap](https://buck.cheap/). Enter any verified low or average manually, record the period and provider update date when available, and confirm that the product, variant and quantity are the same. FacebookWatcher does not automatically fetch provider timelines or fabricate historical values.

Changing the product identity invalidates previous retail/history comparisons and match reviews for that product. Save a fresh price and re-check references before confirming candidates again.

Removing a retail product removes its retail snapshots, history references and match reviews. Its Facebook watches and archived listings remain.

## Smart watches and seller controls

Open **Smart watches → Create watch with AI** to turn a natural-language request into a reviewable plan. Choose either explicit ChatGPT plan usage or a separate API-key provider, review the generated Marketplace searches and indexed-group filters, correct the rules, and save only after accepting the final plan. New watches start paused unless you explicitly enable them. AI planning is optional. Review the provider and billing choice before connecting; the app does not automatically switch billing providers.

Listing details show **Seller** for Marketplace owners and **Posted by** for group authors. **Block seller** hides that recognized identity from archive browsing, searches, watch results, retail candidates and ordinary exports without deleting stored records; **Undo** or **Blocked sellers** restores visibility. Unknown or ambiguous owners cannot be blocked. Manage existing blocks through **Blocked sellers**.

## Export, backup and restore

### Export listing data

Select **Export CSV** under **Archive tools** in the workspace menu to save listing fields for use in another tool. The API also supports JSON export. CSV and JSON exports are limited to 10,000 listings and do not replace a full archive backup.

### Create a backup

Select **Backup** under **Archive tools** in the workspace menu when no scan is queued or running. The `.fwatch` file contains a consistent SQLite archive snapshot and downloaded images, including retail watchlist data. It excludes Facebook browser profiles and service credentials. The current `.fwatch` format has a 128 MB size limit.

Keep backups on storage you control. For a move to another host, stop collection, create a backup, set up the new service, restore the file, pause enabled sources before reconnecting Facebook, run a small test scan and check **Activity**, then resume only the schedules you want. Restored enabled sources retain their schedules and may run as soon as Facebook is reconnected, so do not wait until after login to pause them.

### Restore a backup

Restore replaces the current archive and source settings after confirmation. Save a backup of the current state first if you might need it. Restores require idle scans, and the Facebook session is not included, so reconnect Facebook after the restore. Source enabled states are preserved; pause sources before reconnecting if overdue schedules must not resume immediately.

## App updates

See [Install and update](installation.md) for version-specific update instructions. v0.1.1 requires a manual upgrade to the first version that uses the public feed. Later versions check public releases without a GitHub token.

## Data, privacy and safety

- The archive and Facebook session remain on the host running the watcher.
- FacebookWatcher collects only pages and groups that the logged-in account can access.
- Connecting an account does not itself grant permission for automated collection. Follow applicable permissions, platform terms and [Meta's published guidance](https://about.fb.com/news/2021/04/how-we-combat-scraping/).
- Backups contain archive data and images, but not browser profiles or credentials. Treat them as sensitive because listings may include personal information.
- Keep one active service per archive directory and protect the directory from other users or processes.
- Currency values are not converted. Compare only like-for-like currencies and verify the listing before making a purchase decision.

## Help

See [Troubleshooting](troubleshooting.md) for login, scanning, installation and update problems, and [Data and privacy](privacy.md) for storage and backup information.
