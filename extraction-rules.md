# Extraction Rules

## Purpose of This Page

This page records rules for extracting names, places, dates, official titles, and other structured data from Sinitic / Chinese historical and humanities texts. For term definitions, see [[terminology]].

Use these rules when turning source text into JSON, CSV, tables, lists, or other structured formats. For source reliability, check [[source-materials]] first.

## General Extraction Principles

- Preserve the original wording from the source whenever possible.
- Do not modernize or silently translate extracted terms.
- Do not guess missing information.
- If an item is uncertain, mark it as uncertain. Repeated uncertainty errors belong in [[known-errors]].
- Separate source text from interpretation.
- Follow the requested output format exactly. See [[examples]] for good and bad outputs.
- If no relevant item is found, output an empty value or `[]`, depending on the requested schema.

## Entity Types

### Personal Names

A personal name is the name of a person mentioned in the text. See [[known-errors]] for common mistakes involving names and titles.

Examples:

- 王小明
- 陳大文
- 李美華

Rules:

- Extract full names when possible.
- Do not extract general kinship terms unless they function as a name.
- Do not treat official titles alone as personal names.
- If a name and title appear together, separate them if the schema requires separate fields.

### Place Names

A place name is the name of a location, region, administrative unit, building, or geographic feature.

Examples:

- 北京
- 香港
- 廣州
- 新安縣

Rules:

- Preserve historical place names as written.
- Do not replace them with modern names unless asked.
- If the place is uncertain, mark uncertainty.

### Official Titles

An official title is a title or office held by a person in a government, court, military, or administrative system.

Examples:

- 知縣
- 總督
- 提督
- 侍衛

Rules:

- Extract the title as written.
- Do not infer rank unless the task asks for rank.
- If a person and title appear together, keep both but store them in separate fields if possible.

### Dates and Time Expressions

A date or time expression is any wording that indicates a specific date, reign period, era, dynasty, period, or time range.

Examples:

- 乾隆三十年
- 康熙年間
- 明代
- 清代

Rules:

- Preserve original date wording.
- Do not convert to Gregorian dates unless asked.
- If converting dates, store both original and converted forms.

### Text Titles and Source Titles

A text title or source title is the name of a book, document, record, gazetteer, genealogy, edition, or other source.

Examples:

- 新安縣志
- 屏山鄧氏族譜

Rules:

- Preserve title formatting.
- Do not invent bibliographic details.
- If edition information is missing, mark it as missing.

## Recommended Output Formats

### JSON Array for Simple Name Extraction

Input:

```text
王小明今天去了北京大學。
```

Output:

```json
["王小明"]
```

### CSV Columns for Historical Entity Extraction

Recommended columns:

- `source_id`
- `row_id`
- `entity_text`
- `entity_type`
- `normalized_form`
- `uncertain`
- `evidence`
- `notes`

For workflow steps using these columns, see [[workflows]].

Column meanings:

- `source_id`: The identifier for the source text, file, document, or collection.
- `row_id`: The row, line, paragraph, page, or segment identifier within the source.
- `entity_text`: The exact extracted wording from the source.
- `entity_type`: The category of entity, such as personal name, place name, official title, date, or source title.
- `normalized_form`: A standardized form, if requested or available. Leave empty if not known.
- `uncertain`: Use `yes` or `no` to mark whether the extraction is uncertain.
- `evidence`: The source wording or short passage that supports the extraction.
- `notes`: Any explanation, ambiguity, missing information, or special handling.

## Ambiguity Rules

- If an entity could belong to more than one category, mark uncertainty.
- If the model is unsure, it should not force a clean answer.
- Use `uncertain: true` in JSON or `yes` in CSV.
- Add a short note explaining the ambiguity. Compare with uncertainty examples in [[examples]].

## Common Mistakes To Avoid

- Inventing names not present in the text
- Treating place names as personal names
- Treating official titles as personal names
- Translating extracted terms without being asked
- Normalizing historical places without evidence
- Ignoring uncertainty
- Returning prose when a table, CSV, or JSON is requested

Record repeated cases in [[known-errors]] and revise related prompts in [[prompt-rules]].

## Example: Good and Bad Extraction

Source sentence:

```text
乾隆三十年，侍衛張偉明奉命前往廣州。
```

Good extraction:

- Personal name: 張偉明
- Official title: 侍衛
- Date: 乾隆三十年
- Place: 廣州

Bad extraction examples:

- Personal name: 侍衛張偉明
- Place: Canton
- Date: 1765 unless conversion was requested

## Terms To Refine Later

- [ ] Rules for extracting variant names
- [ ] Rules for extracting courtesy names and art names
- [ ] Rules for extracting kinship terms
- [ ] Rules for extracting reign dates and converted dates
- [ ] Rules for extracting dynastic periods
- [ ] Rules for extracting official ranks
- [ ] Rules for extracting administrative units
- [ ] Rules for extracting temples, schools, offices, and institutions
- [ ] Rules for extracting book titles and chapter titles
- [ ] Rules for handling uncertain OCR text
- [ ] Rules for normalized forms
- [ ] Rules for source IDs and row IDs
- [ ] Rules for nested or overlapping entities
- [ ] Rules for quotations and cited passages
