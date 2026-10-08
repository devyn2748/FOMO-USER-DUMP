# FOMO User Dump

A dataset of **570,897 unique FOMO user profiles**, including public handles, wallet addresses, profile statistics and balance observations.

## Download

Download `profiles.sqlite.gz` from this repository's **Releases** section.

- Format: gzip-compressed SQLite
- Download size: approximately 104 MB
- Database contents: one table, `profiles`
- Balance observations: 570,816 users

This release contains **profiles and balances only**. It contains no individual trade records or trade histories.

## Usage

Extract the `.gz` file and open `profiles.sqlite` with a SQLite-compatible application or library.

On Linux or macOS:

```bash
gzip -dk profiles.sqlite.gz
```

Use `user_id` to identify users; handles can change. Balance values are stored as decimal strings to preserve precision.

To verify the download, place the checksum file beside the archive and run:

```bash
sha256sum -c db-sharing-SHA256SUMS.txt
```

## Data notes

- Balances are snapshots, not historical balances.
- Reported USD valuations are not independently verified and may include unreliable token prices.
- Some valuations are incomplete or missing. `known_holdings_usd` is a subtotal; use `balance_complete` and `balance_observed_at` to interpret it.
- Profile counters are reported statistics, not verified history totals.
- Public handles and wallet addresses are retained, so this dataset is not anonymous.

This dataset is intended for research and exploratory analysis, not as a verified measure of users' wealth.
