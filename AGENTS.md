# AGENTS.md

## Project Purpose

This folder is a plain-text LLM Wiki for digital humanities work on Sinitic / Chinese historical and humanities texts.

Use this wiki with [[project-overview]] to help AI assistants understand:

- Project background
- [[terminology]]
- [[source-materials]]
- [[extraction-rules]]
- [[prompt-rules]]
- [[examples|Examples of correct and incorrect outputs]]
- [[known-errors|Known model errors]]
- Project [[workflows]]

The wiki should make future AI work more consistent, cautious, and useful.

## Language Rules

- Use English for explanations by default.
- Use Traditional Chinese only when Chinese is needed.
- Do not use Simplified Chinese unless the source text itself is Simplified and the task requires preserving it.

## File Rules

- Use Markdown files.
- Keep pages short and focused.
- Prefer one topic per file.
- Do not delete existing content unless asked.
- Do not edit raw source files if a `raw/` folder is added later.
- If uncertain, add a note under an `Uncertainty` section instead of guessing. See [[known-errors]] for repeated uncertainty mistakes.

## Research Rules

- Do not invent citations, source titles, dates, names, translations, or historical facts.
- Clearly mark uncertainty.
- Ask for source text when evidence is missing.
- Separate source evidence from interpretation.
- Preserve original wording when the task requires transcription or quotation.

## Extraction Rules

- Follow [[extraction-rules]] when extracting names, places, dates, official titles, or other entities.
- Follow the requested output schema exactly.
- If an item is ambiguous, mark it as uncertain rather than forcing a clean answer.

## Prompt Rules

- Follow [[prompt-rules]] for reusable prompts.
- Record successful prompts and failed prompts.
- When a prompt causes repeated errors, document the error in [[known-errors]].

## Update Rules

- Update the wiki when the user corrects the AI.
- Update the wiki when a new project rule is created.
- Update [[known-errors]] when a repeated model error is found.
- Update [[source-materials]] when a new source is added.

## Safety and Privacy

- Do not store API keys, access tokens, passwords, or private credentials in this wiki.
- Do not include private personal data unless the user explicitly asks and it is necessary.
