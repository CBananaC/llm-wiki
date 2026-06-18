# Known Errors

## Purpose of This Page

This page records repeated AI mistakes so future [[prompt-rules|prompts]], [[extraction-rules]], and [[workflows]] can avoid them.

## How To Use This Page

- Check this page before designing new [[prompt-rules|prompts]].
- Add a new entry when the AI repeats the same mistake.
- Each error should include the bad output, why it is wrong, and how to fix it.
- If an error is solved by a better prompt, link or refer to [[prompt-rules]].

## Error Entry Template

### Error: [Short error name]

**Task:**  
[What the AI was asked to do]

**Source text:**  
[Source text here]

**Bad output:**  
[Wrong AI output]

**Why it is wrong:**  
- [Reason 1]
- [Reason 2]

**Correct output:**  
[Correct output]

**Prevention rule:**  
[Rule to prevent this error next time]

## Error 1: Returning Empty Array When a Name Is Present

**Task:**  
Extract personal names.

**Source text:**  
王小明今天去了北京大學。

**Bad output:**  
```json
[]
```

**Why it is wrong:**  
- The sentence clearly contains the personal name 王小明.
- The model missed an explicit entity.

**Correct output:**  
```json
["王小明"]
```

**Prevention rule:**  
Use direct [[examples]] in the prompt and test the model with simple sentences before using it on a larger corpus.

## Error 2: Returning Plain Text Instead of JSON

**Task:**  
Extract personal names and output JSON array only.

**Source text:**  
陳大文和李美華一起參加會議。

**Bad output:**  
```text
陳大文和李美華
```

**Why it is wrong:**  
- The requested format was JSON array.
- The conjunction 和 is not part of either name.
- The output cannot be reliably parsed as structured data.

**Correct output:**  
```json
["陳大文", "李美華"]
```

**Prevention rule:**  
State clearly: "Only output JSON array. Do not explain. Do not add other text."

## Error 3: Using 無 Instead of Empty JSON Array

**Task:**  
Extract personal names and output JSON array only.

**Source text:**  
今天下雨。

**Bad output:**  
```text
無
```

**Why it is wrong:**  
- The meaning is correct, but the output format is wrong.
- The requested output was JSON array.

**Correct output:**  
```json
[]
```

**Prevention rule:**  
Specify the exact empty-output format: "If no item is found, output []."

## Error 4: Combining Official Title and Personal Name

**Task:**  
Extract historical entities.

**Source text:**  
乾隆三十年，侍衛張偉明奉命前往廣州。

**Bad output:**  
```text
侍衛張偉明 as a personal name.
```

**Why it is wrong:**  
- 侍衛 is an official title.
- 張偉明 is the personal name.
- Combining them loses entity type distinctions.

**Correct output:**  
- Official title: 侍衛
- Personal name: 張偉明

**Prevention rule:**  
Tell the model to separate official titles from personal names when the schema has separate fields.

## Error 5: Translating Source Terms Without Being Asked

**Task:**  
Extract place names or source titles.

**Source text:**  
《新安縣志》記載，屏山鄧氏於明清時期多有科舉功名。

**Bad output:**  
```text
New Gazetteer of Xin'an County
```

**Why it is wrong:**  
- The task was extraction, not translation.
- The original source title should be preserved.

**Correct output:**  
```text
新安縣志
```

**Prevention rule:**  
State: "Preserve original source wording. Do not translate unless explicitly asked."

## Error 6: Converting Dates Without Being Asked

**Task:**  
Extract dates.

**Source text:**  
乾隆三十年，侍衛張偉明奉命前往廣州。

**Bad output:**  
```text
1765
```

**Why it is wrong:**  
- The source says 乾隆三十年.
- Gregorian conversion was not requested.
- Date conversion may require historical verification.

**Correct output:**  
```text
乾隆三十年
```

**Prevention rule:**  
State: "Preserve original date wording. Do not convert dates unless asked. If converting, keep both original and converted forms."

## Error 7: Overconfidence With Ambiguous Names

**Task:**  
Extract personal names.

**Source text:**  
張公奉命入京。

**Bad output:**  
```json
["張公"]
```

**Why it may be wrong:**  
- 張公 may be a respectful reference, not a full personal name.
- The output does not mark uncertainty.

**Correct output:**  
Use an uncertainty-aware format:

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

**Prevention rule:**  
Use an output schema with an uncertain field for ambiguous historical entities. See [[extraction-rules]].

## Error 8: Returning JSON Inside Markdown Code Fence

**Task:**  
Extract entities and output JSON array only.

**Source text:**  
章太炎與孫中山嘲命思想的異趣

**Bad output:**  
````text
```json
[
  {
    "entity_text": "章太炎",
    "entity_type": "personal_name",
    "uncertain": false,
    "evidence": "章太炎與孫中山嘲命思想的異趣",
    "notes": ""
  }
]
```
````

**Why it is wrong:**  
- The task requested a JSON array only.
- Markdown code fences make the output harder to parse as raw JSON.
- CSV post-processing may need to remove the code fence before parsing.

**Correct output:**  
```json
[
  {
    "entity_text": "章太炎",
    "entity_type": "personal_name",
    "uncertain": false,
    "evidence": "章太炎與孫中山嘲命思想的異趣",
    "notes": ""
  }
]
```

**Prevention rule:**  
Add a stricter instruction to prompts: "Return raw JSON only. Do not wrap the JSON in Markdown. Do not use a `json` code fence or any other Markdown code fence."

## General Prevention Rules

- Test prompts on simple examples before using them on large files.
- Use strict output schemas for structured extraction.
- Include examples of both positive and negative cases.
- Record repeated errors in this page.
- Update [[prompt-rules]] when a better prompt prevents a repeated error.
- Update [[extraction-rules]] when an error shows that a rule is unclear.

## Errors To Add Later

- [ ] OCR misreading Traditional Chinese characters
- [ ] Confusing people with places
- [ ] Confusing dynasties and reign periods
- [ ] Inventing citations
- [ ] Inventing source titles
- [ ] Misreading tables
- [ ] Over-normalizing historical terms
- [ ] Ignoring requested CSV columns
