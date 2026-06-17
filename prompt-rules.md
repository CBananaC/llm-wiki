# Prompt Rules

## Purpose of This Page

This page stores reusable prompt rules and templates so AI assistants produce consistent, verifiable, and structured outputs when working with Sinitic / Chinese historical and humanities texts. Pair it with [[examples]] and [[known-errors]].

Use this page when writing prompts for extraction, analysis, comparison, OCR cleanup, or prompt improvement. For entity rules, see [[extraction-rules]].

## General Prompt Principles

- State the task clearly.
- Give the model the role only if it helps the task.
- Provide the source text or data directly. If the source is registered, check [[source-materials]].
- Tell the model what output format to use.
- Tell the model what not to do.
- Ask the model to mark uncertainty instead of guessing.
- Keep reusable prompts short enough to edit easily.
- Separate instructions from source text.
- Do not rely on the model's memory for source-specific facts.

## Recommended Prompt Structure

Use this structure for most project prompts:

1. Role or task
2. Source text or input data
3. Extraction or analysis rules
4. Output format
5. Uncertainty rule
6. Final warning not to explain if structured output is required

Template:

```text
Task:
[Describe the task clearly.]

Source text:
[Paste the text here.]

Rules:
- [Rule 1]
- [Rule 2]
- [Rule 3]

Output format:
[JSON / CSV / Markdown table / plain text]

Uncertainty:
If uncertain, mark the item as uncertain and explain briefly in the notes field.
```

## Prompt Template: Simple Personal Name Extraction

Use this prompt when the task is only to extract personal names. Compare outputs against [[examples]].

System prompt:

```text
你是一個中文人名抽取工具。請從每句中抽取所有人名。只輸出 JSON 陣列，不要解釋。如果沒有任何人名，請輸出 []。
```

Example input:

```text
王小明今天去了北京大學。
```

Expected output:

```json
["王小明"]
```

## Prompt Template: Historical Entity Extraction

Use this prompt when extracting multiple historical entity types from a source text. Follow [[extraction-rules]].

Reusable prompt:

```text
Task:
Extract historical entities from the source text.

Source text:
[Paste the source text here.]

Entity types:
- personal name
- place name
- official title
- date or time expression
- text or source title

Rules:
- Preserve the original wording from the source.
- Do not translate or modernize extracted terms.
- Do not invent missing information.
- Separate names, places, titles, dates, and source titles.
- If an item is uncertain, mark uncertain as true and explain briefly in notes.

Output format:
Return a JSON array. Each item must contain:
- entity_text
- entity_type
- uncertain
- evidence
- notes

Final warning:
Return only JSON. Do not explain.
```

Example source text:

```text
乾隆三十年，侍衛張偉明奉命前往廣州。
```

Expected output:

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

## Prompt Template: Compare AI Outputs

Use this prompt to compare two AI outputs against the project [[extraction-rules]].

```text
Task:
Compare two AI outputs against the extraction rules and decide which output is better.

Source text:
[Paste the source text here.]

Extraction rules:
[Paste or summarize the relevant rules here.]

Output A:
[Paste Output A here.]

Output B:
[Paste Output B here.]

Evaluate:
- Which output is better?
- Which rules were followed?
- Which rules were broken?
- Were any entities invented?
- Was uncertainty handled properly?
- What is the final recommendation?

Output format:
Use a Markdown table followed by a short final recommendation.
```

## Prompt Template: Improve a Failed Prompt

Use this prompt after a model failure to produce a better prompt. Record repeated failures in [[known-errors]].

```text
Task:
Improve the prompt so the model is less likely to repeat the same error.

Original prompt:
[Paste the original prompt here.]

Source text:
[Paste the source text here.]

Model output:
[Paste the model output here.]

Expected output:
[Paste the expected output here.]

Error type:
[Describe the error type, such as invented entity, wrong category, bad JSON, ignored uncertainty, or translated source text.]

Request:
Explain briefly why the prompt failed, then write a revised prompt.

Output format:
- Failure reason
- Revised prompt
```

## Common Prompt Mistakes

- Asking too many tasks at once
- Not specifying output format
- Mixing source text and instructions unclearly
- Asking for JSON but allowing explanation
- Not giving examples for difficult tasks
- Asking the model to infer missing historical facts
- Not telling the model how to handle uncertainty
- Using vague words such as "analyze" without defining what to analyze

## When To Update This Page

Update this page when:

- A prompt works well
- A prompt fails repeatedly
- The output schema changes
- The project adds a new task
- The user corrects the AI's prompting method

Also update [[examples]] when a prompt produces a useful good or bad example.
