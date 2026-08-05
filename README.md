# TibuOS Update

This is the public, read-only update channel for TibuOS. The operating system's
main source repository remains private.

- `latest.updatetibu` is the package retrieved by the experimental Update
  Manager.
- Versioned packages and checksums are retained in their version folders.
- The current package is Alpha v0.1.11.1.

The v0.1.11.1 updater validates the `TIBUUPD1` structure and payload CRC-32, writes
only the EFI system partition (LBAs 2048-133119), and preserves the target
disk's GPT and TibuFS user-data partition. The format is not cryptographically
signed yet. Keep backups and do not power off during an update.

SHA-256 checksums are provided for independent download verification.
