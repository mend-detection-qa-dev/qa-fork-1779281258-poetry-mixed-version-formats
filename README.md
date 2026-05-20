# poetry-mixed-version-formats

Stress test for **SCA-5540** — `versionPatternWhl` regex must handle all version format variants.

## Dependencies

| Package | Version | Format |
|---|---|---|
| `requests` | `2.31.0` | semver (3-part) |
| `pdfminer.six` | `20251230` | calendar version (no dots) |
| `Pillow` | `10.3.0` | two-segment |
| `httpx` | `0.27.2` | semver |

## Key assertion

All 4 direct deps must appear with non-empty `sha1`. A partial regex fix that handles only
one format variant will be caught here.
