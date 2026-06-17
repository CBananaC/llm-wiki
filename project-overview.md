# Project Overview

## What This LLM Wiki Is

This wiki is a shared knowledge base for an AI-assisted digital humanities project focused on Sinitic / Chinese historical and humanities texts.

Its purpose is to help human researchers and AI assistants work from the same background information, [[terminology]], rules, and [[examples]]. It should be practical, readable, and easy to update as the project changes.

The wiki is not a final publication. It is a working reference space for:

- Project background
- Key terms and concepts
- [[source-materials|Source descriptions]]
- [[prompt-rules]]
- [[extraction-rules]]
- [[examples|Examples of good and bad AI outputs]]
- Notes that help AI agents understand the project before writing code or analyzing texts; see [[AGENTS]]

## What Kind of Research Project This Supports

This project uses AI tools to support research on Sinitic / Chinese historical and humanities texts.

The texts may include materials such as:

- Classical Chinese texts
- Historical documents
- Literary works
- Commentaries and annotations
- Gazetteers, archival records, or reference works
- Transcriptions, editions, translations, and metadata

The AI tools may help with tasks such as:

- Explaining project background
- Identifying and defining key terms
- Drafting or improving prompts using [[prompt-rules]]
- Extracting structured information from texts using [[extraction-rules]]
- Comparing different AI outputs with [[examples]]
- Checking whether outputs follow project rules
- Preparing code or [[workflows]] for text analysis
- Helping new collaborators understand the project

The project should treat AI as an assistant, not as an authority. Human review remains necessary, especially for interpretation, translation, source criticism, and historical claims.

## What Information Should Be Stored Here

Store information that will help future humans and AI assistants understand the project clearly.

Useful wiki content includes:

- Project goals and research questions
- Background notes about the corpus or historical context
- Definitions of important terms in [[terminology]]
- Preferred English translations for key terms
- Traditional Chinese examples where useful
- Notes about text genres, editions, and source reliability
- [[source-materials|Source material descriptions]]
- Metadata conventions
- [[prompt-rules|Prompt-writing rules]]
- [[extraction-rules]]
- Output schemas or table formats
- [[examples|Examples of correct AI outputs]]
- [[examples|Examples of incorrect AI outputs]]
- Common errors made by AI systems in [[known-errors]]
- Decisions made during the project and why they were made

Examples of useful entries:

- A note explaining how the project uses the term `Sinitic texts`
- A rule saying whether names should be romanized, translated, or kept in Chinese
- A prompt template in [[prompt-rules]] for extracting people, places, dates, and offices
- A warning in [[known-errors]] that a model often confuses dynastic periods or invents citations
- A correct example of extracting a term from a passage in Traditional Chinese

## What The AI Assistant Should Use This Wiki For

The AI assistant should read and use this wiki before doing project work.

The assistant should use the wiki to:

- Understand the project background
- Learn the project's [[terminology]]
- Follow [[prompt-rules|prompt]] and [[extraction-rules|extraction]] rules
- Use the preferred folder and file structure
- Match existing [[examples]] and conventions
- Avoid repeating [[known-errors|known mistakes]]
- Check whether a task requires caution or human review
- Understand what [[source-materials|sources]] are available and what they contain
- Write code or analysis that fits the project's actual needs

Before writing code, analyzing texts, or generating structured outputs, the assistant should look for relevant wiki pages about:

- The [[source-materials|source material]]
- The expected output format
- [[prompt-rules]]
- [[extraction-rules]]
- Correct and incorrect [[examples]]
- Any warnings in [[known-errors]] about uncertainty or model limitations

## What The AI Assistant Should Not Assume

The AI assistant should not fill gaps with guesses.

The assistant should not assume:

- That a model output is historically correct
- That a translation is reliable without review
- That an unidentified person, place, date, or title is obvious
- That simplified and Traditional Chinese forms are interchangeable
- That one Chinese term has only one correct English translation
- That all sources follow the same format
- That OCR text is accurate
- That missing metadata can be invented
- That a citation exists unless it is present in the source material
- That modern meanings of terms apply to historical texts
- That project rules are stable if the wiki says they are still being tested

When uncertain, the assistant should:

- State the uncertainty clearly
- Ask for clarification if needed
- Mark fields as unknown rather than inventing values
- Preserve the original text when possible
- Separate direct evidence from interpretation
- Follow the [[examples]] and rules in this wiki

## Basic Folder Structure

Use a simple folder structure so the wiki can grow gradually.

```text
wiki/
  project-overview.md
  background/
    research-questions.md
    project-context.md
    timeline.md
  terms/
    key-terms.md
    people.md
    places.md
    offices-and-titles.md
  sources/
    source-inventory.md
    editions-and-versions.md
    metadata-rules.md
    ocr-notes.md
  prompts/
    general-prompt-rules.md
    extraction-prompts.md
    review-prompts.md
  extraction-rules/
    people-places-dates.md
    quotations.md
    named-entities.md
    tables-and-fields.md
  examples/
    correct-outputs.md
    incorrect-outputs.md
    before-and-after.md
  ai-agent-notes/
    coding-guidelines.md
    analysis-guidelines.md
    known-model-failures.md
```

## Suggested First Pages To Create

Start with a small number of useful pages.

- `background/research-questions.md`: What the project is trying to discover or explain
- `terms/key-terms.md`: Important terms and preferred translations
- `sources/source-inventory.md`: What texts or files the project uses
- `prompts/general-prompt-rules.md`: Rules every AI prompt should follow
- `extraction-rules/tables-and-fields.md`: Expected fields for structured extraction
- `examples/correct-outputs.md`: Examples the AI should imitate
- `examples/incorrect-outputs.md`: Examples the AI should avoid
- `ai-agent-notes/known-model-failures.md`: Common AI mistakes in this project

## Working Rule

This wiki should stay concrete. Prefer clear rules, examples, and source notes over abstract theory.

When adding a new page, include:

- What the page is for
- The rule or information being recorded
- One or more examples if useful
- Any uncertainty or open questions
