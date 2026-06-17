# Workflows

## Purpose of This Page

This page records repeatable project workflows so human researchers and AI assistants can follow consistent steps when working with Sinitic / Chinese historical and humanities texts. AI agents should also read [[AGENTS]].

## General Workflow Rules

- Work step by step.
- Keep raw sources separate from edited or derived files.
- Do not overwrite raw data.
- Save intermediate outputs.
- Record important decisions in the wiki.
- Check AI output before using it as research evidence.
- When a workflow fails, document the failure in [[known-errors]].

## Workflow 1: From Source Image to Extracted Text

1. Collect source image or PDF.
2. Record source metadata in [[source-materials]].
3. Run OCR.
4. Save raw OCR output.
5. Check OCR quality.
6. Correct obvious OCR errors if needed.
7. Save cleaned text separately.
8. Mark reliability level.
9. Record known OCR problems.

Output files example:

- `raw/source-image-001.jpg`
- `ocr/source-image-001.raw.txt`
- `cleaned/source-image-001.cleaned.txt`

## Workflow 2: From Text to Entity Table

1. Prepare clean source text.
2. Read [[extraction-rules]].
3. Choose entity types.
4. Choose output schema.
5. Test on 3-5 short examples.
6. Run extraction on full text.
7. Save extracted results.
8. Check uncertain or suspicious rows.
9. Record repeated errors in [[known-errors]].

Recommended CSV columns:

- `source_id`
- `row_id`
- `entity_text`
- `entity_type`
- `normalized_form`
- `uncertain`
- `evidence`
- `notes`

## Workflow 3: Prompt Testing Workflow

1. Write an initial prompt.
2. Test it on simple positive examples.
3. Test it on negative examples.
4. Test it on ambiguous examples.
5. Compare model output with expected output.
6. Revise the prompt.
7. Save the successful prompt in [[prompt-rules]].
8. Save failed examples in [[examples]] or [[known-errors]].

Example test cases:

- 王小明今天去了北京大學。
- 今天下雨。
- 陳大文和李美華一起參加會議。
- 張公奉命入京。

## Workflow 4: Comparing Local and Cloud Models

1. Select the same prompt and same test file.
2. Run it with a local model, such as LM Studio.
3. Run it with a cloud model, such as Gemini or OpenRouter.
4. Compare output quality.
5. Record:
   - accuracy
   - format consistency
   - speed
   - cost
   - common errors
6. Decide which model is suitable for the task.

Warning: A working API call does not guarantee research-quality output.

## Workflow 5: Updating the LLM Wiki After a Correction

1. Identify what the AI got wrong.
2. Decide whether it is a [[terminology]] issue, [[source-materials|source]] issue, [[extraction-rules|extraction]] issue, [[prompt-rules|prompt]] issue, or workflow issue.
3. Update the relevant wiki page.
4. Add a bad example if the error may repeat.
5. Add or revise a prevention rule.
6. Retest the corrected prompt or workflow.

## Recommended Folder Structure

```text
llm-wiki/
  AGENTS.md
  index.md
  project-overview.md
  terminology.md
  source-materials.md
  extraction-rules.md
  prompt-rules.md
  examples.md
  known-errors.md
  workflows.md
  raw/
  ocr/
  cleaned/
  outputs/
  scripts/
```

Folder purposes:

- `raw/`: Original source files, images, PDFs, or downloads. Do not edit these files.
- `ocr/`: Raw OCR outputs created from images or PDFs.
- `cleaned/`: Corrected or cleaned text derived from OCR or transcription.
- `outputs/`: Extracted tables, JSON files, CSV files, model outputs, and analysis results.
- `scripts/`: Helper scripts for OCR, cleaning, extraction, conversion, or validation.

## When To Update This Page

Update this page when:

- A new repeated workflow is created
- A workflow fails
- A workflow is improved
- A new tool is added
- File naming rules change
- Output formats change
