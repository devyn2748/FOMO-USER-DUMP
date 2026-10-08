# FOMO User Dump

SQLite datasets containing FOMO user profiles, public wallet addresses, balance observations and trade records for exploratory analysis.

## Downloads

Download the compressed databases from this repository's **Releases** section.

| File | Contents | Download size |
|---|---|---:|
| `usernames.sqlite.gz` | 570,897 unique user profiles; 570,816 balance observations | 439 MB |
| `dataset.sqlite.gz` | 86,141 trade events across 71 users; 172,282 token legs | 64 MB |

The trade dataset covers a subset of the user inventory. It is not a complete trade-history dataset for all listed users.

## Usage

Extract the `.gz` files and open the resulting `.sqlite` databases with a SQLite-compatible application or library.

On Linux or macOS:

```bash
gzip -dk usernames.sqlite.gz dataset.sqlite.gz
```

The main data tables are `profiles` in the user database and `users`, `events` and `legs` in the trade database. Join records using FOMO user IDs rather than handles, which can change.

If you downloaded the checksum file, verify the downloads with:

```bash
sha256sum -c db-sharing-SHA256SUMS.txt
```

## Data notes

- Balances are snapshots, not historical balances at the time of each trade.
- Reported USD valuations are not independently verified and may include unreliable token prices.
- Some balances are missing or partially valued. A known subtotal should not be treated as a complete balance.
- Trade coverage varies by user; records should not be assumed to represent complete lifetime activity.
- Amounts may be stored as decimal strings to preserve precision.
- Public handles and wallet addresses are retained, so the datasets are not anonymous.

These datasets are intended for research and exploratory analysis. They are not a verified measure of users' wealth or trading performance.
