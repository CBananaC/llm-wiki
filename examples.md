# Examples

## Purpose of This Page

This page records good and bad examples so AI assistants can follow project standards and avoid repeated mistakes when working with Sinitic / Chinese historical and humanities texts. Use it with [[extraction-rules]] and [[prompt-rules]].

## How To Use These Examples

- Good examples show the expected format and reasoning boundaries.
- Bad examples show common mistakes.
- Future [[prompt-rules|prompts]] and [[extraction-rules]] should refer to these examples.
- When a new repeated model error appears, add it here or in [[known-errors]].

## Example 1: Simple Personal Name Extraction

Source text:

```text
王小明今天去了北京大學。
```

Task:

Extract all personal names. Output JSON array only.

Good output:

```json
["王小明"]
```

Bad output:

```json
[]
```

Why the bad output is wrong:

- The text clearly contains the personal name 王小明.
- Returning an empty array misses the entity.

## Example 2: No Personal Name Present

Source text:

```text
今天下雨。
```

Task:

Extract all personal names. Output JSON array only.

Good output:

```json
[]
```

Bad output:

```text
無
```

Why the bad output is wrong:

- The meaning is correct, but the requested output format was JSON array.
- The correct empty result is `[]`.

## Example 3: Multiple Personal Names

Source text:

```text
陳大文和李美華一起參加會議。
```

Task:

Extract all personal names. Output JSON array only.

Good output:

```json
["陳大文", "李美華"]
```

Bad output:

```text
陳大文和李美華
```

Why the bad output is wrong:

- The names were identified, but the output is not a JSON array.
- The conjunction 和 should not be included as part of the names.

## Example 4: Historical Entity Extraction

Source text:

```text
乾隆三十年，侍衛張偉明奉命前往廣州。
```

Task:

Extract personal names, official titles, dates, and place names.

Good output:

```json
[
  {
    "entity_text": "乾隆三十年",
    "entity_type": "date",
    "uncertain": false,
    "evidence": "乾隆三十年",
    "notes": ""
  },
  {
    "entity_text": "侍衛",
    "entity_type": "official_title",
    "uncertain": false,
    "evidence": "侍衛張偉明",
    "notes": ""
  },
  {
    "entity_text": "張偉明",
    "entity_type": "personal_name",
    "uncertain": false,
    "evidence": "侍衛張偉明",
    "notes": ""
  },
  {
    "entity_text": "廣州",
    "entity_type": "place_name",
    "uncertain": false,
    "evidence": "前往廣州",
    "notes": ""
  }
]
```

Bad output:

```json
[
  {
    "entity_text": "侍衛張偉明",
    "entity_type": "personal_name",
    "uncertain": false
  },
  {
    "entity_text": "Canton",
    "entity_type": "place_name",
    "uncertain": false
  },
  {
    "entity_text": "1765",
    "entity_type": "date",
    "uncertain": false
  }
]
```

Why the bad output is wrong:

- 侍衛張偉明 incorrectly combines the official title and personal name.
- 廣州 was translated to Canton without being asked.
- 乾隆三十年 was converted to 1765 without being asked.
- The output does not preserve the original wording from the source.

## Example 5: Source Title Extraction

Source text:

```text
《新安縣志》記載，屏山鄧氏於明清時期多有科舉功名。
```

Task:

Extract text or source titles.

Good output:

```json
["新安縣志"]
```

Bad output:

```json
["新安 County Gazetteer"]
```

Why the bad output is wrong:

- The source title was partially translated without being asked.
- The original title should be preserved.

## Example 6: Uncertainty Handling

Source text:

```text
張公奉命入京。
```

Task:

Extract personal names.

Good output:

```json
[
  {
    "entity_text": "張公",
    "entity_type": "personal_name",
    "uncertain": true,
    "evidence": "張公奉命入京",
    "notes": "Could be a respectful reference rather than a full personal name."
  }
]
```

Bad output:

```json
["張公"]
```

Why the bad output is incomplete:

- It may be acceptable in simple extraction, but it does not mark uncertainty.
- 張公 may not be a full personal name.

## Patterns To Remember

- Preserve original source wording unless translation is requested; check [[source-materials]] when source status matters.
- Return the exact requested format.
- Do not invent missing details.
- Separate names from official titles.
- Mark uncertainty when needed.
- Do not normalize historical places unless asked.
- Do not convert dates unless asked.

For repeatable testing steps, see [[workflows]].

## Examples To Add Later

- [ ] OCR error correction example
- [ ] Gazetteer entity extraction example
- [ ] Classical Chinese passage example
- [ ] Table-to-CSV extraction example
- [ ] TEI XML tagging example
- [ ] Failed prompt revision example
