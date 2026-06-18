# CBDB Enrichment: source-001

## Date Accessed

2026-06-18

## API

- Documentation referenced in the workshop: `https://projects.iq.harvard.edu/cbdb/cbdb-api`
- Person endpoint: `https://cbdb.fas.harvard.edu/cbdbapi/person.php`

## Person Matching

### 孫中山

- A query for `孫中山` returned no match.
- A query for the formal name `孫文` returned multiple candidates.
- CBDB person ID `75900` was selected because the record gives birth year 1866, death year 1925, index address 香山, and aliases 中山 and 逸仙.
- API record: `https://cbdb.fas.harvard.edu/cbdbapi/person.php?id=75900&o=json`

### 章太炎

- A query for `章太炎` returned no match.
- A query for the formal name `章炳麟` returned two candidates.
- CBDB person ID `88996` was selected because the record gives birth year 1868, death year 1936, index address 餘杭, and aliases 太炎 and 枚叔.
- The second candidate, CBDB person ID `645079`, is a different person associated with 大興 and a 1866 posting as 典史 in 武定府.
- API record: `https://cbdb.fas.harvard.edu/cbdbapi/person.php?id=88996&o=json`

## Data Added

- `source-001.cbdb-people.csv`: matched person identifiers, dates, aliases, and index addresses.
- `source-001.cbdb-places.csv`: CBDB address records enriched with verified CHGIS IDs and coordinates.
- `source-001.cbdb-network-nodes.csv`: people returned by the matched CBDB records.
- `source-001.cbdb-network-edges.csv`: CBDB association records with source fields.

## Limitations

- CBDB data is external enrichment and must not be presented as if it came from source-001.
- CBDB address IDs and CHGIS IDs remain distinct fields. See `chgis-enrichment.md` for the matching method.
- The database may contain incomplete or conflicting records.
- The relationship labels preserve CBDB wording. Interpretation requires source review.
