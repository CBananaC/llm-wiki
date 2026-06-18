# Final Summary: AI Agents for Sinitic Texts

## What This Workshop Covered

The workshop followed a practical learning path from basic LLM concepts to building a reusable research environment:

1. What a large language model, or LLM, is.
2. The Four Pillars: model, prompt, context, and tools.
3. Tokens, parameters, temperature, knowledge cutoff, reasoning, and context window.
4. AI coding agents and Codex.
5. Deterministic and non-deterministic methods.
6. Regex compared with LLM-based extraction.
7. Running local models with LM Studio.
8. Using API loops for repeated processing.
9. Building browser-based batch LLM tools.
10. Using Git and deploying tools with GitHub Pages.
11. Understanding memory, context, retrieval-augmented generation (RAG), and the LLM Wiki.
12. Using Obsidian as a wiki interface.
13. Building an LLM Wiki from raw sources, project rules, workflows, and reusable skills.
14. Using REST APIs to work with external data.
15. Applying classical digital humanities methods: TEI, NLP, historical GIS, and network analysis.

## What I Built

- A local LM Studio setup.
- A working OpenAI-compatible API call using `curl`.
- A browser-based LLM batch caller.
- A GitHub Pages deployment for the tool.
- Support for an API URL and API key.
- Image OCR input.
- A first LLM Wiki.
- Obsidian-ready wikilinks.
- Project folders: `raw/`, `ocr/`, `cleaned/`, `outputs/`, `scripts/`, and `skills/`.
- Reusable skills for:
  - Personal name extraction.
  - REST API workflow.
  - LibraryCloud search.
  - TEI encoding.
  - NLP analysis.
  - Historical GIS.
  - Network analysis.

## Main Lessons

- A successful API call does not guarantee good research output. The response still needs to be checked for accuracy, relevance, and completeness.
- Small local models are useful for learning, experimentation, and privacy, but they may fail on complex extraction tasks.
- Prompt design affects output quality. Clear instructions, examples, schemas, and uncertainty rules make results more consistent.
- Structured output formats such as JSON and CSV are important because they make research results easier to inspect, compare, validate, and reuse.
- LLM Wikis help AI agents remember project-specific terminology, source rules, workflows, examples, and known errors.
- Raw sources, cleaned text, and AI-generated outputs should be kept separate so that each stage of the research process remains traceable.
- AI can assist classical digital humanities methods, but final artifacts such as TEI XML, NLP data, gazetteer records, and network edge lists must be verifiable.
- Human review remains necessary. AI output should be treated as a research aid, not automatically accepted as evidence.

## My Current Project Structure

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
  folder-structure.md
  log.md
  final-summary.md
  raw/
  ocr/
  cleaned/
  outputs/
  scripts/
  skills/
```

## What To Do Next

1. Add real source records to `source-materials.md`.
2. Put one real source PDF or image into `raw/`.
3. Run OCR and save the output in `ocr/`.
4. Clean a small sample and save it in `cleaned/`.
5. Use the batch LLM tool to extract entities.
6. Save extracted results in `outputs/`.
7. Record errors in `known-errors.md`.
8. Update extraction and prompt rules based on real results.
9. Use Obsidian to navigate and refine the wiki.
10. Commit changes regularly with Git.

## Personal Reflection

This workshop shows that working with AI is not just chatting with a model. A useful AI research environment combines models with tools, context, prompts, source rules, repeatable workflows, and carefully organized files. The goal is not simply to generate answers, but to produce outputs that can be checked, corrected, documented, and reused in responsible research.
