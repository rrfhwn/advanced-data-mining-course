# Wikipedia teaching corpus

Version: `wikipedia-teaching-2026-11-27`. File: `wikipedia_teaching.json.gz`; machine-readable selection/provenance: [wikipedia_manifest.json](wikipedia_manifest.json).

## Source, attribution, and license

**Text authors: Wikipedia contributors.** Each document includes its original article URL, recorded revision URL, revision ID/timestamp, attribution, and license URL. The source page's history identifies its contributors. The snapshot adapts English Wikipedia introductions through selection, plain-text extraction, whitespace normalization, and truncation to at most 500 whitespace-separated words. No images are redistributed. No synthetic defects were inserted into these source texts; synthetic teaching examples in notebooks are separate.

The adapted text corpus is distributed under [Creative Commons Attribution–ShareAlike 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Keep the document-level source/attribution/license metadata and this adaptation statement when sharing the corpus, and follow the license for adapted text. See [Wikimedia's reuse terms](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use#7._Licensing_of_Content). This notice concerns the Wikipedia corpus; the retail dataset retains its separately documented license.

## Contents and observation unit

- 120 distinct English article introductions, 40,744 retained whitespace-separated words, compressed size 111,900 bytes.
- Six manually chosen collection areas: space, energy, life, computing, cities, and economics. These selection areas are not ground-truth classes or query-relevance labels.
- Retained lengths range from 58 to 500 words; 21 introductions are truncated. The source window and article versions are fixed by this supplied snapshot; live pages may differ.
- 1,600 observed directed links to selected canonical article titles, excluding self-links. Links were queried from full articles at preparation time, not just the retained introductions. They provide a possible later graph artifact; Week 6 does not use them to rank text.

One row represents one selected article introduction. It is not an independent random sample of writing, a complete article, or a representative picture of Wikipedia. Neighboring articles can have related definitions and overlapping text without being erroneous duplicates. Metadata labels and original titles must not be silently appended as features in a purported text-only comparison.

## Fields

| Field | Meaning |
|---|---|
| `doc_id`, `page_id` | Stable English Wikipedia page identity; retain alignment across text, embeddings, and graph artifacts |
| `title`, `requested_title` | Canonical title returned by the source and the original collection request |
| `text` | Plain-text introduction, normalized and bounded to 500 words |
| `selection_theme` | Manual collection provenance; not an evaluation label |
| `source_url`, `revision_url` | Attribution and inspection links; revision recorded alongside acquisition |
| `revision_id`, `revision_timestamp` | Recorded revision metadata from the text acquisition request |
| `attribution`, `license_url` | Contributor attribution and CC BY-SA 4.0 link |
| `source_lead_words`, `truncated` | Length before the cap and whether it was applied |
| `outgoing_doc_ids` | Selected canonical-title links from the full article, without self-links |

## Reproducibility and automatic setup

The compressed snapshot's SHA-256 is `8cd7e9bdcec080488f264832c15dee171729cc52df84b442eb3838ca33932de6`. The Week 6 notebook verifies its bundled/cached copy or a public asset download. An embedded compressed copy with the same checksum supplies an automatic fallback before publication or during network failure. Students do not collect pages, extract archives, upload files, or run the corpus-preparation script. Dependency installation still needs internet when first performed.

The development preparation script verifies the existing snapshot by default. A deliberate refresh queries current pages and selected links; same-day response caching and rate-limit backoff allow interrupted preparation to resume. A refreshed live dataset can differ, so its version, attribution, checksum, notebook pin, and observed results must be reviewed before release. The bundled file is the exact reproducibility artifact. Link queries happen after text queries and are not claimed to be an atomic, revision-pinned graph snapshot.

## Interpretation limits

The corpus has curated English topic coverage, encyclopedia style, unequal lengths, and a 500-word cap. Absence of a feature may reflect wording, filtering, or truncation. Similarity is not relevance, factual correctness, or agreement. NMF components summarize the chosen representation; neither component counts nor word lists certify real categories.

Saved links are limited to exact selected canonical-title targets. Redirect aliases, external links, and targets outside the collection are not exhaustively resolved. A missing edge is therefore not proof of no relationship. Repeated articles, a larger random corpus, and a complete Wikipedia network are not interchangeable extensions of this small teaching snapshot.
