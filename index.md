# LLM Wiki Index

## Purpose

This wiki is a working knowledge base for AI-assisted digital humanities work on Sinitic / Chinese historical and humanities texts.

It helps AI assistants understand project background, [[terminology]], [[source-materials]], [[extraction-rules]], [[prompt-rules]], [[examples]], [[known-errors]], and [[workflows]] before doing project work.

Skills are reusable instructions that help AI agents perform specific tasks consistently and safely.

Classical digital humanities methods should produce verifiable artifacts, such as TEI XML, structured NLP outputs, map-ready gazetteer data, and network edge lists.

## Quick Start for AI Assistants

Before doing any project work, read these files in order:

1. [[AGENTS]]
2. [[project-overview]]
3. The task-specific page, such as [[extraction-rules]], [[prompt-rules]], or [[source-materials]]

Rules:

- Do not invent sources, citations, names, dates, translations, or historical facts.
- Use English for explanation by default.
- Use Traditional Chinese only when Chinese is needed.
- Follow the requested output format exactly.
- Mark uncertainty instead of guessing.

## Wiki Pages

| File | Purpose | When to read it |
| --- | --- | --- |
| [[AGENTS]] | Gives working rules for AI coding and research agents. | Read first before any project work. |
| [[project-overview]] | Explains what the LLM Wiki is and what kind of project it supports. | Read when joining the project or starting a new task. |
| [[terminology]] | Defines key AI, digital humanities, and Sinitic text terms. | Read when terms, translations, or categories are unclear. |
| [[source-materials]] | Records sources, source categories, reliability, and citation rules. | Read before using, citing, or describing any source. |
| [[extraction-rules]] | Defines rules for extracting names, places, dates, titles, and structured data. | Read before extraction or entity-recognition tasks. |
| [[prompt-rules]] | Stores reusable prompt rules and prompt templates. | Read before writing or revising prompts. |
| [[examples]] | Shows correct and incorrect AI outputs. | Read before testing prompts or judging model output. |
| [[known-errors]] | Records repeated AI mistakes and prevention rules. | Read before designing prompts or debugging bad outputs. |
| [[workflows]] | Describes repeatable project workflows. | Read before OCR, extraction, model comparison, or wiki updates. |

## Skills

| File | Purpose | When to use it |
| --- | --- | --- |
| `skills/rest-api-workflow.md` | Provides a safe, repeatable workflow for using external RESTful APIs. | Use when requesting external data or calling an API from a script. |
| `skills/librarycloud-search.md` | Provides a workflow for searching Harvard LibraryCloud or a similar catalog API. | Use when finding and evaluating bibliographic records. |
| `skills/tei-encoding.md` | Provides rules for encoding source texts as structured TEI XML. | Use when marking text structure, entities, dates, titles, or divisions. |
| `skills/nlp-analysis.md` | Provides rules for computational text analysis and structured NLP outputs. | Use for entity extraction, classification, tagging, topic detection, or model comparison. |
| `skills/historical-gis.md` | Provides rules for linking historical places to gazetteers and map-ready data. | Use for place extraction, historical geocoding, and geographic data preparation. |
| `skills/network-analysis.md` | Provides rules for creating evidence-based nodes and edge lists. | Use for relationship extraction and network data preparation. |

## Suggested Reading Paths

### For Text Extraction Tasks

Read:

1. [[AGENTS]]
2. [[terminology]]
3. [[source-materials]]
4. [[extraction-rules]]
5. [[examples]]
6. [[known-errors]]

### For Prompt Writing Tasks

Read:

1. [[AGENTS]]
2. [[prompt-rules]]
3. [[examples]]
4. [[known-errors]]

### For Source Management Tasks

Read:

1. [[AGENTS]]
2. [[source-materials]]
3. [[workflows]]

### For Updating the Wiki

Read:

1. [[AGENTS]]
2. [[project-overview]]
3. [[workflows]]

## Current Wiki Status

This is the first version of the LLM Wiki. It currently contains general rules and examples. More project-specific source records, extraction schemas, and real examples should be added later.

## Next Pages To Improve

- [ ] Add real source records to [[source-materials]]
- [ ] Add project-specific entity categories to [[extraction-rules]]
- [ ] Add tested prompts to [[prompt-rules]]
- [ ] Add real good and bad examples to [[examples]]
- [ ] Add repeated model failures to [[known-errors]]
- [ ] Add real OCR and extraction workflows to [[workflows]]
