---
name: rl-course-guide
description: Find relevant sections of Zhao’s Mathematical Foundations of Reinforcement Learning from a concept, question, or learning difficulty, and verify the result against the source. Use for course navigation, targeted review, or finding prerequisites within this book.
---

# Reinforcement Learning Textbook Guide

Help the learner find textbook material that addresses a question. For a concept, formula, or difficulty, answer the core question to the extent verified, then cite relevant sources. Keep a location-only request concise. Teach in English and Chinese while preserving the book's terms and notation.

## Locate Material

1. Read `AGENTS.md` and `LEARNING-GUIDE.md`. Read `LEARNING.md` when the request concerns progress or the next lesson. Respect any chapter or scope specified by the learner.
2. Search the candidate section index at `learning-artifacts/textbook/INDEX.md` and existing companions in `learning-artifacts/textbook/sections/`. If a companion is missing, say so and check the PDF. Search English and Chinese terminology, symbols, aliases, and context; consult the contents and chapter PDFs as needed. If the index or a file is missing, search the author's PDF directly. Do not infer verified content or page numbers from an ideal directory, bookmarks, OCR, or filenames.
3. Usually select one to three relevant candidate sections. Inspect their original PDF pages and verify that they cover the question and any formulas or assumptions cited. Distinguish printed page numbers from the PDF's one-based physical pages and name whether the full-book or chapter PDF is used. If extraction is damaged or a page cannot be confirmed, state the limitation; do not invent a page, formula, or location.
4. For each result provide the chapter or section, English or bilingual title, reason it matches, verified page, and original-book link. Link an existing companion or index and its review status where useful. List only genuinely necessary prerequisites. If nothing matches, say so and give the nearest verified location.

## Sources and Boundaries

- The author's PDF is the authority for textbook content. Recognition drafts and automatically generated companions may omit text or figures or corrupt formulas; preserve their review status. Contents, filenames, and search hits are candidates, not verified facts. If notes or OCR disagree with the book, describe the difference and check the original page; retain uncertainty if the page is unclear. Check whether the print-edition errata applies to the version in use.
- Third-party notes are independent supplementary material, not the author's textbook, and have not been shown to match the current PDF version. If cited, identify the author, link or local path, and verified scope. Do not treat their formulas, proofs, or omissions as the original text, and do not copy their content into this repository without confirmation.
- If the learner wants an explanation, use verified sources for a brief explanation and example. To continue the course, hand the navigation result to `rl-learning` and use `LEARNING.md` as the checkpoint authority. A lookup or answer alone does not update progress or reveal an unanswered question's answer.
- Claim a source was checked only after reading the actual page. If only an index or companion was found, say the PDF has not yet been checked. If the source is unavailable, give a verifiable next step rather than inventing a citation.
