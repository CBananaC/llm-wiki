# TEI + NLP Summary: source-001

## Method

Generated on 2026-06-18 by `scripts/tei_nlp_summary.py`.

This is a TEI-derived, rule-based NLP pass. It extracts document segments, TEI tags, controlled topic terms, and document-level classifications from the checked TEI file. It does not claim to be a corpus-level topic model, POS tagger, or machine-learning classifier.

## Output Files

- `source-001.nlp-segments.csv`
- `source-001.nlp-tags.csv`
- `source-001.nlp-topics.csv`
- `source-001.nlp-classification.csv`

## Topic Outputs

- topic-001: Revolutionary alliance and rupture (反滿革命:1|革命同道:1|思想上的差異:2|爭執:1|齟齬:1|分裂:1)
- topic-002: Personality and political authority (元首:1|國師:1|高度自信:1|直言無忌:1|屈己相從:1)
- topic-003: Nationalism and anti-Qing politics (民族主義:3|推翻滿清政權:1|排滿:1|清政府:1)
- topic-004: Imperialism and Western influence (西方文化:1|歐美:1|列強:3|帝國主義:3|西潮:1|反帝:2)
- topic-005: Asia, Russia, and communism (亞洲:2|俄:1|赤化:1|聯俄容共:1|外力:1)

## Classification Outputs

- document_genre: journal article abstract page
- language_script: Traditional Chinese
- subject_area: modern Chinese intellectual history
- historical_focus: late Qing revolutionary politics
- central_comparison: 章太炎 and 孫中山
- source_keywords: 章太炎|孫中山|革命思想|國族主義|帝國主義

## Tagging Outputs

- concept: 3
- controlled_topic_term: 20
- date: 1
- person: 6
- place: 4
- role: 2

## Limitations

- The corpus currently contains one article abstract page, so the topic output is a controlled thematic inventory rather than a statistical topic model.
- The tags are based on existing TEI markup and explicit source terms; they should be checked before being used as research evidence.
- Bibliographic metadata remains incomplete where noted in `source-materials.md` and `processing-notes.md`.
