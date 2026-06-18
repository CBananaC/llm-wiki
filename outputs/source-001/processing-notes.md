# Processing Notes: source-001

## Source Location

`raw/source-001/`

## Current Status

The raw PDF, OCR text, visually checked cleaned transcription, reviewed entity extraction outputs, and validated minimal TEI XML are available. Visible page metadata has been checked; the publication year, publisher, and complete article page range still require verification.

## Processing Steps

- Confirm source title and metadata.
- Run OCR or extract text.
- Save raw OCR output in `ocr/source-001/`.
- Check OCR quality.
- Save cleaned text in `cleaned/source-001/`.
- Run entity extraction.
- Save extraction output in `outputs/source-001/`.
- Record errors in `known-errors.md`.
- Update source status in `source-materials.md`.

## Notes

- 2026-06-18: Saved the source PDF in `raw/source-001/`.
- 2026-06-18: Saved raw OCR text and a source-page image in `ocr/source-001/`.
- 2026-06-18: Created a cleaned sample in `cleaned/source-001/`; the full cleaned text still requires completion.
- 2026-06-18: Ran entity extraction with Vertex AI and cleaned the batch CSV output.
- 2026-06-18: Retried five rows that initially failed with HTTP 429 errors. All five retries succeeded.
- 2026-06-18: Regenerated `source-001.entities.cleaned.csv` with 22 entity rows and `source-001.entities.errors.csv` with zero error rows.
- 2026-06-18: Reviewed the seven recovered entity rows against the source context.
- Added five supported records to `source-001.entities.verified.csv`: 章, 國師, 中山, 太炎, and 中國.
- Excluded 西方 because it describes a cultural concept in this passage rather than a discrete place.
- Excluded 歐美 because it is a collective regional expression rather than a specific place record under the current extraction rules.
- 2026-06-18: Compared the one-page source image with the OCR and completed `cleaned/source-001/source-001.cleaned.txt`.
- Corrected OCR errors including `嘲命` to `革命`, `早匣` to `齟齬`, `謠刀` to `諂媚`, `倡義` to `倡議`, `懊已` to `屈己`, `威轟` to `威脅`, and `未當` to `未嘗`.
- Preserved the earlier OCR-based extraction as `source-001.entities.ocr.vertex.csv`, `source-001.entities.ocr.cleaned.csv`, `source-001.entities.ocr.errors.csv`, and `source-001.entities.ocr.verified.csv`.
- 2026-06-18: Reran Vertex AI entity extraction using `source-001.cleaned.extraction-input.txt`.
- Processed five corrected input rows and produced ten model-extracted entity rows with zero error rows.
- Reviewed the corrected extraction and added two explicit entities missed by the model: `清季革命時期` and `俄`.
- The active `source-001.entities.verified.csv` contains twelve reviewed entity rows based on the corrected transcription.
- 2026-06-18: Verified visible bibliographic details from the source image: author 汪榮祖; title 〈道不同終不相為謀：論章太炎與孫中山革命思想的異趣〉; running header `思想史 7`; printed page `2`.
- The embedded PDF metadata names a download tool rather than the article and is not reliable bibliographic evidence.
- Focused external searches did not locate an exact catalog or journal record for the article. Publication year, publisher, interpretation of `7`, complete page range, and stable identifier remain unverified.
- 2026-06-18: Created `source-001.tei.xml` as a minimal TEI representation of the checked transcription.
- Marked the article structure, personal names, roles, places, time expression, and keywords while preserving the source wording.
- Validated the XML successfully with `xmllint --noout`.
- 2026-06-18: Created `source-001.gazetteer.csv` from the reviewed place entities.
- Preserved the source forms 歐美, 中國, 亞洲, and 俄 without inventing normalized names, gazetteer identifiers, or coordinates.
- Marked all four GIS records as uncertain because they are broad or abbreviated geographic expressions and have not been matched against an authoritative historical gazetteer.
- 2026-06-18: Created `source-001.network-nodes.csv` and `source-001.network-edges.csv`.
- Added four evidence-based relationships: revolutionary association, ideological conflict, self-identification as 國師, and 孫中山's political alignment expressed as 聯俄容共.
- Did not infer friendship, residence, kinship, teacher-student relations, or other ties not stated in the source.
- Marked the edge to 俄 as uncertain because the abbreviated geopolitical target has not been historically normalized.
- 2026-06-18: Queried the official CBDB person endpoint and disambiguated the source's two named people.
- Matched 孫中山 to 孫文, CBDB person ID `75900`, using dates 1866–1925, address 香山, and alias 中山.
- Matched 章太炎 to 章炳麟, CBDB person ID `88996`, using dates 1868–1936, address 餘杭, and alias 太炎.
- Added separate CBDB people, places, network nodes, and network edges CSVs so external data remains distinct from source-derived claims.
- Added CBDB links to the TEI personal-name markup.
- 2026-06-18: Matched the CBDB address 香山 to CHGIS 香山縣 (`hvd_42226`) at year 1866.
- 2026-06-18: Matched the CBDB address 餘杭 to CHGIS 余杭縣 (`hvd_40085`) at year 1868 using the TGAZ spelling variant 余杭.
- Added `source-001.chgis-places.csv` with stable CHGIS IDs, valid years, historical parents, and authoritative point coordinates.
- Added the verified coordinates to `source-001.cbdb-places.csv` while preserving the separate CBDB and CHGIS identifiers.
- 2026-06-18: Created `source-001.cbdb-chgis.geojson` for import into QGIS or another mapping tool.
- 2026-06-18: Created `source-001.cbdb-network.gexf` for import into Gephi.
- Added `map-network-cross-reading.md` to compare the map and network while documenting that the place records are index addresses rather than career routes.
- The current external data is sufficient to demonstrate the workflow but not sufficient to claim geographic clustering of the network.
