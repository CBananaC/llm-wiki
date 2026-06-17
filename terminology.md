# Terminology

## Purpose of This Page

This page records important project terms, preferred meanings, and usage rules for this LLM Wiki. Use it alongside [[extraction-rules]], [[prompt-rules]], and [[source-materials]].

Use it so that AI assistants do not guess what a term means. If a term has more than one possible meaning, record the uncertainty instead of forcing one answer; repeated mistakes should go in [[known-errors]].

## Core AI Terms

- **LLM**: A large language model. It is an AI system that generates or analyzes text based on patterns learned from data.
- **AI agent**: An AI assistant that can follow instructions, use tools, read files, write files, or complete multi-step tasks.
- **Prompt**: The instruction or input given to an AI model. See [[prompt-rules]] for reusable prompt guidance.
- **System prompt**: A high-priority instruction that tells the AI how to behave for a task or project.
- **Context**: The information available to the AI when it answers, such as the prompt, files, notes, or conversation history.
- **Memory**: Stored information that helps an AI assistant remember project preferences or past decisions.
- **RAG**: Retrieval-Augmented Generation. A method where the AI first retrieves relevant documents or notes, then uses them to answer.
- **LLM Wiki**: A plain-text knowledge base that helps AI assistants understand the project before doing research, writing, or coding. Start from [[index]] and [[AGENTS]].
- **Token**: A small unit of text used by an AI model. A token may be a word, part of a word, punctuation, or a character.
- **Model**: The specific AI system being used, such as a local model or a cloud-hosted model.
- **API**: An interface that lets software send requests to another system, such as an AI model server.
- **Local model**: An AI model running on the user's own computer or local network.
- **Cloud model**: An AI model hosted by an external provider and accessed over the internet.

## Digital Humanities Terms

- **Digital humanities**: The use of digital tools and methods to study humanities materials such as texts, history, literature, language, and culture.
- **Corpus**: A collection of texts or documents used for research.
- **Metadata**: Information about a text or document, such as title, author, date, source, edition, language, or file format.
- **Text extraction**: The process of taking useful text or data out of a source file, image, PDF, or document. See [[extraction-rules]].
- **Named entity recognition**: The task of identifying names of people, places, organizations, dates, titles, or other important entities in a text.
- **Structured data**: Information organized into a clear format, such as a table, list, CSV file, or JSON object.
- **CSV**: Comma-Separated Values. A simple table format where each row is a line and fields are separated by commas.
- **JSON**: JavaScript Object Notation. A structured data format often used by APIs and software tools.
- **TEI**: Text Encoding Initiative. A standard for encoding texts in XML, often used in digital humanities projects.
- **OCR**: Optical Character Recognition. A process that converts text in images or scans into machine-readable text. See [[workflows]] for source-image workflows.

## Sinitic / Chinese Text Terms

- **Sinitic texts**: Texts written in Chinese or related Sinitic written traditions, including historical, literary, administrative, and scholarly materials.
- **Classical Chinese**: A historical written form of Chinese used in many premodern texts. It differs from modern spoken and written Chinese.
- **Traditional Chinese**: Chinese characters in traditional form, such as `學`, `國`, and `書`.
- **Simplified Chinese**: Chinese characters in simplified form, such as `学`, `国`, and `书`.
- **Romanization**: Writing Chinese sounds using the Latin alphabet, such as pinyin or other systems.
- **Personal name**: The name of a person mentioned in a text.
- **Place name**: The name of a location, region, administrative unit, building, or geographic feature.
- **Official title**: A title or office held by a person, often in a government, court, military, or administrative system.
- **Reign period**: A named period associated with a ruler's reign, often used for dating historical events.
- **Dynasty**: A ruling house or historical period, such as Tang, Song, Ming, or Qing.
- **Gazetteer**: A local historical or geographic work that records information about places, people, institutions, events, and customs.
- **Archival record**: A document preserved as part of an official, institutional, family, or historical archive.

## Project Usage Rules

- Use English for explanation by default.
- Use Traditional Chinese when Chinese examples are needed.
- Do not silently convert Traditional Chinese to Simplified Chinese.
- Preserve the source text when doing transcription or quotation; see [[source-materials]].
- If a term has multiple possible meanings, mark uncertainty instead of guessing.

## Terms To Define Later

- [ ] Project-specific corpus name
- [ ] Main historical period or periods
- [ ] Main region or regions
- [ ] Important genres in the source material
- [ ] Key people
- [ ] Key places
- [ ] Key institutions
- [ ] Common official titles
- [ ] Dating conventions
- [ ] Romanization system
- [ ] Preferred translation rules
- [ ] Source edition terminology
- [ ] OCR correction terminology
- [ ] Entity extraction categories
- [ ] Output schema terms
