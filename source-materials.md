# Source Materials

## Purpose of This Page

This page records the sources available to the project, their status, reliability, format, and rules for using them. For extraction from these sources, see [[extraction-rules]].

Use this page so AI assistants know what sources exist, what they may be used for, and what must not be assumed. AI agents should also follow [[AGENTS]].

## General Source Rules

- Do not invent source titles.
- Do not invent citations.
- Do not assume a source contains information unless it is listed or provided.
- Distinguish between primary sources, reference works, datasets, and secondary scholarship.
- Preserve original wording when quoting or transcribing.
- If source text is missing, ask the user to provide it.
- If a source is uncertain or incomplete, mark it clearly.
- Do not silently correct, modernize, or translate source text unless asked. Record repeated violations in [[known-errors]].

## Source Categories

### Primary Sources

Primary sources are historical or original texts used as evidence. See [[terminology]] for related project terms.

Possible examples:

- Gazetteers
- Genealogies
- Archival records
- Memorials
- Official documents
- Literary texts
- Commentaries
- Stone inscriptions
- Manuscripts

### Reference Works

Reference works help identify terms, names, places, dates, or background information.

Possible examples:

- Dictionaries
- Biographical databases
- Chronological tables
- Place-name databases
- Bibliographies

### Datasets

Datasets are structured data used for analysis. See [[workflows]] for repeatable processing steps.

Possible examples:

- CSV files
- JSON files
- TEI XML files
- Extracted entity tables
- OCR output files
- Metadata spreadsheets

### Secondary Scholarship

Secondary scholarship includes modern academic articles, books, theses, and research notes.

Rules:

- Do not cite scholarship unless the source is available.
- Do not invent page numbers.
- Separate the author's argument from the project's interpretation.

## Source Record Template

### Source: [Source title]

**Source type:**  
[Primary source / reference work / dataset / secondary scholarship]

**Language/script:**  
[Classical Chinese / Traditional Chinese / Simplified Chinese / English / mixed]

**Format:**  
[PDF / TXT / CSV / JSON / XML / image / website / database]

**Location:**  
[Local path, URL, repository, or description]

**Status:**  
[Raw / cleaned / OCRed / manually checked / partially checked]

**Reliability notes:**  
[Known issues, OCR quality, edition issues, missing pages, uncertain metadata]

**Allowed AI use:**  
[What the AI may use this source for]

**Restrictions:**  
[What the AI must not do with this source]

**Citation rule:**  
[How to cite or refer to this source]

## Current Sources

`source-001` is registered below. Metadata visible on the supplied page has been checked, but the publication year, publisher, and complete article page range still require verification.

### Source: source-001 — 道不同終不相為謀：論章太炎與孫中山革命思想的異趣

**Source type:**  
Secondary scholarship / journal article abstract page

**Language/script:**  
Traditional Chinese

**Author:**  
汪榮祖

**Publication:**  
《思想史》, issue or volume designation `7` as printed in the page header

**Page:**  
Printed page `2`; the complete article page range is not yet known

**Format:**  
PDF

**Location:**  
`raw/source-001/`

**Status:**  
Cleaned / TEI encoded / GIS and network artifacts created / citation partially verified

**Reliability notes:**  
The one-page PDF, raw OCR text, visually checked cleaned transcription, reviewed entity extraction outputs, and validated minimal TEI XML are available. The extraction was rerun against the corrected transcription. The title, author, `思想史 7` header, and printed page number are visible on the supplied page. The publication year, publisher, complete article page range, and stable catalog identifier have not been verified. The embedded PDF metadata is unreliable and must not be used for citation.

**Allowed AI use:**  
AI may inspect and process the available source file and OCR text. AI-generated entities must be reviewed before use as research evidence.

**External enrichment:**  
CBDB person IDs `75900` (孫文 / 孫中山) and `88996` (章炳麟 / 章太炎) were matched through the official CBDB API on 2026-06-18. Their CBDB addresses were matched through CHGIS/TGAZ to `hvd_42226` (香山縣) and `hvd_40085` (余杭縣). External database claims are stored separately under `outputs/source-001/source-001.cbdb-*` and `outputs/source-001/source-001.chgis-*` and must not be attributed to the article.

**Restrictions:**  
Do not invent the publication year, publisher, issue interpretation, complete page range, stable identifier, or other citation details.

**Citation rule:**  
Until a complete catalog or journal record is found, use only a provisional citation: 汪榮祖, 〈道不同終不相為謀：論章太炎與孫中山革命思想的異趣〉, 《思想史》 7, supplied abstract page, printed p. 2. Mark the publication year and complete page range as unverified.

## Example Source Record

### Source: 新安縣志

**Source type:**  
Primary source / gazetteer

**Language/script:**  
Classical Chinese / Traditional Chinese

**Format:**  
Not yet specified

**Location:**  
To be added

**Status:**  
Not yet verified

**Reliability notes:**  
Edition, page range, and OCR quality must be checked before use.

**Allowed AI use:**  
The AI may use this source only when relevant text is provided or when the source has been registered with reliable metadata.

**Restrictions:**  
Do not invent quotations, page numbers, edition details, or bibliographic information.

**Citation rule:**  
Cite only with verified edition and page information.

## Source Reliability Levels

- **raw**: Not checked.
- **OCRed**: Text extracted but may contain errors.
- **cleaned**: Obvious errors corrected.
- **verified**: Checked against source image or reliable edition.
- **analysis-ready**: Safe for structured extraction or citation with caution.

## When To Update This Page

Update this page when:

- A new source is added
- OCR is completed
- A source is cleaned or verified
- Citation rules are decided
- Source reliability changes
- A source is removed from active use
- A source-related workflow changes in [[workflows]]
