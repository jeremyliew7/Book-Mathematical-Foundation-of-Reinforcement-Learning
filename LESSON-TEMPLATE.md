---
type: template
tags: [reinforcement-learning, teaching]
created: 2026-10-30
---

# Textbook Section Template

The following skeleton is a starting point, not a required heading order. Choose the structure, pacing, depth, diagrams and examples that make the specific concept teachable. Preserve the source metadata, record what was actually checked, and keep exercises separate from their answers. A review or Q&A can have a shorter structure. Do not invent implementations, prerequisites, results, or time estimates. Use the author's PDF as the source of truth.

```markdown
---
type: textbook-section
tags: [reinforcement-learning, textbook-section]
created: <actual creation date>
section: "<chapter.section>"
title: "<English source title>"
source_file: "<source PDF filename>"
source_commit: "<verified Git commit>"
source_sha256: "<verified PDF SHA-256>"
pdf_pages: "<1-based physical pages in that PDF>"
book_pages: "<printed pages, or unverified>"
verification: "<what was actually checked and what remains uncertain>"
---

# <section number> <English title>

## Source and scope

[Source PDF, first relevant physical page](<relative-encoded-path>#page=<page>). State the edition, checked scope, and the limits of this independent companion.

## Learning objectives and prerequisites

List the specific outcomes and only the prerequisites supported by the text or the actual derivation.

## The problem

Introduce a concrete question that motivates the section.

## The concept

Explain the central idea, definitions, notation, and conditions in plain language.

## Derivation and examples

Explain the important steps, equations, and assumptions. Distinguish an author example from a new worked example, and label any simplification. For a summary or Q&A, use the heading to connect its stated ideas or questions without inventing a derivation.

## Applications and limitations

Explain where the idea helps and when the conclusion does not apply. Code and experiments are optional; separate a prediction or hand trace from an actual execution.

## Exercises

Offer appropriately graduated questions without their answers. The number and form depend on the section. If the source is Q&A, write independent review prompts without copying source answers.

## Key terms and misconceptions

| Term | Meaning | Common misconception |
| --- | --- | --- |
| <term> | <meaning> | <correction> |
```

## Teaching quality contract

A heading structure is navigation, not a substitute for teaching. A first-time reader should be able to follow the reasoning from the stated prerequisites to at least one result and then attempt a related problem independently. A concise review or Q&A section can refer back to the chapter's taught examples; it must not present a summary as a full derivation.

- Start with a concrete decision, observation, or counterexample that makes the question necessary. State exactly what the reader knows and what must be found.
- Introduce each new symbol in context before using it. Connect the notation back to the scenario; distinguish a random variable from one realization, an estimate from its target, and an assumption from a conclusion.
- Where the source includes a derivation, do not jump from its premise to the final formula. Show the intermediate transformations that make the idea understandable, and explain the rule or assumption used at each consequential step. Separate an intuitive argument from a proof; if a proof is omitted, say exactly what remains to be established.
- Include at least one fully worked, source-checked example where the topic permits it. A tiny numerical MDP or an explicit symbolic case should show the input, intermediate calculations, interpretation, and a sanity check. Label original examples and hand calculations; do not report an unrun experiment as a result.
- Make exercises progress from recognizing the idea to applying it and explaining a changed assumption. Give an optional graduated hint or point back to a worked step without revealing the exercise answer. The interactive tutor gives individualized feedback after the learner responds.
- Write in a direct teaching voice. Keep provenance and verification details in metadata or a brief source note; avoid repeated process disclaimers and defensive contrasts. Put genuine mathematical assumptions beside the result they govern.
- Explain why a common mistake is tempting and demonstrate where the reasoning fails. Do not equate a longer page or a completed template with comprehension or mastery. For a large result that cannot yet be checked or taught fully, mark the specific gap rather than compressing it into an unsupported claim.

Section files live under `learning-artifacts/textbook/sections/`; the navigation index is `learning-artifacts/textbook/INDEX.md`. A document is not marked verified because it exists or passed a structural check. Record actual page and equation review, preserve uncertainty, and compare discrepancies with the original rather than silently changing its claims. `LEARNING.md` tracks the learner's actual progress, not document production.
