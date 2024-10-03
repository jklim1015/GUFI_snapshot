# GUFI_snapshot
# Snapshot.py - GUFI Script Contribution

## Overview
`Snapshot.py` pulls data using `gufi_query` and aggregates key statistics, such as mode, buckets, and median, before joining all the data into a comprehensive snapshot view. The script outputs an `sqlite3` database file, containing:
- Data-specific tables.
- A metadata table (`meta_snap`).
- The complete snapshot view.

This script was developed to streamline data aggregation and snapshot creation for longitudinal analysis of file systems using GUFI.

## Guide

### Prerequisites
1. Follow this [link to the GUFI repository](https://github.com/mar-file-system/GUFI) and complete the Quick Start Guide to create a GUFI tree.
2. Ensure you have the necessary environment set up for running `gufi_query`.

### Running the Script
To create a snapshot of a given GUFI tree, run the script with the following arguments:

- `--index`: Path to the index (default: `/tmp/index/build`).
- `file_name`: The name of the output `sqlite3` database file.
- `--user_time`: Time provided by the user for creating time buckets (default: current time).

#### Example Command
```bash
python3 Snapshot.py --index /tmp/index/build snapshot.db --user_time 1680123456
