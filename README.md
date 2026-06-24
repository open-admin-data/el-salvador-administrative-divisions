# El Salvador Administrative Divisions / El Salvador



## Overview

| Item | Details |
|------|---------|
| Department | 14 |
| District | 48 |
| Municipality | 266 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-06-24 |
| Website | [openadmindata.org/sv](https://openadmindata.org/sv/) |
| API | [openadmindata.org/api/sv](https://openadmindata.org/api/sv/) |

## Browse by Department

| # | Department | Districts | Municipalitys | Link |
|---|----|----|----|------|
| 1 | Ahuachapán (Ahuachapan) | 3 | 12 | [Browse](divisions/ahuachapan-sv01/) |
| 2 | Cabañas (Cabanas) | 2 | 9 | [Browse](divisions/cabanas-sv02/) |
| 3 | Chalatenango | 4 | 34 | [Browse](divisions/chalatenango-sv03/) |
| 4 | Cuscatlán (Cuscatlan) | 2 | 16 | [Browse](divisions/cuscatlan-sv04/) |
| 5 | La Libertad | 6 | 22 | [Browse](divisions/la-libertad-sv05/) |
| 6 | La Paz | 3 | 22 | [Browse](divisions/la-paz-sv06/) |
| 7 | La Unión (La Union) | 2 | 18 | [Browse](divisions/la-union-sv07/) |
| 8 | Morazán (Morazan) | 2 | 26 | [Browse](divisions/morazan-sv08/) |
| 9 | San Miguel | 3 | 20 | [Browse](divisions/san-miguel-sv09/) |
| 10 | San Salvador | 6 | 20 | [Browse](divisions/san-salvador-sv10/) |
| 11 | San Vicente | 2 | 13 | [Browse](divisions/san-vicente-sv11/) |
| 12 | Santa Ana | 6 | 15 | [Browse](divisions/santa-ana-sv12/) |
| 13 | Sonsonate | 4 | 16 | [Browse](divisions/sonsonate-sv13/) |
| 14 | Usulután (Usulutan) | 3 | 23 | [Browse](divisions/usulutan-sv14/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-department.json](data/all-department.json) | JSON | All 14 department records |
| [all-district.json](data/all-district.json) | JSON | All 48 district records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 266 municipality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-department.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-department.json", "utf-8"));
console.log(`Total: ${data.length} departments`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=department, 2=district, 3=municipality |
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
divisions/{department-slug}/
divisions/{department-slug}/{district-slug}/
```

Municipalitys are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-department links
- [Per-department data](docs/llms-full/) — Full data by department

## Citation

```
El Salvador Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/el-salvador-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
