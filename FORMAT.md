# `.updatetibu` format 1

The file begins with a packed 64-byte little-endian header:

| Field | Size | Value |
|---|---:|---|
| magic | 8 | `TIBUUPD1` |
| format | 4 | `1` |
| header size | 4 | `64` |
| preserved-data boundary | 4 | `133120` sectors |
| record count | 4 | number of records |
| payload CRC-32 | 4 | IEEE CRC-32 over all records |
| version | 20 | NUL-padded ASCII |
| reserved | 16 | zero |

Each sorted record contains a 32-bit starting LBA, a 32-bit sector count, and
`count * 512` bytes. Format 1 rejects records below LBA 2048 or at/above LBA
133120. Gaps inside the EFI partition are zeroed before populated records are
written.
