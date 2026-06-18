# Map and Network Cross-Reading: source-001

## Artifacts

- Map layer: `source-001.cbdb-chgis.geojson`
- Network graph: `source-001.cbdb-network.gexf`
- Supporting place table: `source-001.chgis-places.csv`
- Supporting network tables: `source-001.cbdb-network-nodes.csv` and `source-001.cbdb-network-edges.csv`

## What The Map Shows

The map contains two CHGIS point records:

- 孫中山 / 孫文: 香山縣, under 廣州府 in 1866.
- 章太炎 / 章炳麟: 余杭縣, under 杭州府 in 1868.

These points represent CBDB index or ancestral addresses. They do not represent complete career paths, residences, or travel routes.

## What The Network Shows

The CBDB graph contains five people and four directed association records:

- 孫中山 → 秋瑾: 為Y所著書作序.
- 章太炎 → 康有為: 致書Y in 1903.
- 康有為 → 章太炎: 致書Y in 1898.
- 章太炎 → 呂美蓀: 稱道Y的詩作.

These are database-derived relations. They are not stated in source-001 and should remain separate from the article-derived network.

## Cross-Reading

The current data does not support a reliable claim that either person's network clustered around their index address. The map contains only one address for each principal person, while the association records do not include verified event locations. A geographic-network interpretation would require:

1. More CBDB postings, residences, or event addresses.
2. CHGIS matches for those event locations.
3. Dates linking each relationship to a place.
4. A larger and more complete association sample.

The current artifacts are therefore suitable for demonstrating the GIS-plus-network workflow, but not for drawing substantive conclusions about geographic clustering.
