# Togo Administrative Divisions / Togo



## Overview

| Item | Details |
|------|---------|
| Region | 5 |
| Prefecture | 40 |
| Canton | 373 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-24 |

## Browse by Region

| # | Region | Prefectures | Cantons | Link |
|---|----|----|----|------|
| 1 | Centrale | 5 | 59 | [Browse](divisions/centrale-tg01/) |
| 2 | Kara | 7 | 75 | [Browse](divisions/kara-tg02/) |
| 3 | Maritime | 9 | 68 | [Browse](divisions/maritime-tg03/) |
| 4 | Plateaux | 12 | 103 | [Browse](divisions/plateaux-tg04/) |
| 5 | Savanes | 7 | 68 | [Browse](divisions/savanes-tg05/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 5 region records |
| [all-prefecture.json](data/all-prefecture.json) | JSON | All 40 prefecture records |
| [all-canton.json](data/all-canton.json) | JSON | All 373 canton records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['prefecture']} prefectures")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=prefecture, 3=canton |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{prefecture-slug}/
```

Cantons are listed inline in each prefecture's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Togo Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/togo-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
