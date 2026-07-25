---
name: research-paper-writing
description: Improve academic paper writing quality for ML/CV/NLP-style papers with clear section structure, paragraph flow, and reviewer-facing presentation. Use when drafting or revising Abstract, Introduction, Related Work, Method, Experiments, or Conclusion; polishing figures/tables; checking claim-support alignment; or performing self-review before submission.
---
# Research Paper Writing

## Overview

Use this skill to rewrite a research paper into a reviewer-friendly, high-clarity draft.
Prioritize first-impression quality (figures/tables/layout), logical flow, and evidence-backed claims.

## Core Workflow

1. Clarify the paper story before sentence-level edits.
2. Use section-specific guidance in `references/`.
3. Rewrite paragraph-by-paragraph with one message per paragraph.
4. Run reverse outlining after writing each section.
5. Check every major claim in Abstract/Introduction against experimental evidence.
6. Run final-paper adversarial review with `references/paper-review.md`.

## Global Principles

1. Keep one paragraph for one message only.
2. State the paragraph message in the first sentence.
3. Make nouns self-contained; define new terms before reusing them.
4. Maintain sentence-to-sentence flow (cause, contrast, consequence, or refinement).
5. Iterate with adversarial self-review: read as a skeptical reviewer.
6. Treat visual quality as core content, not decoration.
7. Use a clean teaser and pipeline figure.
8. Use readable, minimal-ink tables.
9. Keep formatting consistent and tidy.

## Terminology And Wording Consistency

1. Maintain a concise terminology map before editing. When a term changes, update abstract, main text, captions, tables, appendices, prompt listings, and generated figures consistently.
2. Use one stable term for each concept. Avoid alternating between near-synonyms unless they denote different technical objects.
3. Avoid defensive phrasing by default. State evidence-aligned claims directly, and add limitations only when scientifically necessary.
4. Define recurring technical phrases at first use with a short, concrete explanation.
5. Preserve original titles in citations and bibliography entries.

## Tables And Generated Figures

1. In main result tables, use `#FFC7CE` for best values and `#D9E7F4` for second-best values when highlighting is requested.
2. For generated plots, match the established paper style: main titles, if present, use 25pt bold; subtitles, if present, use 22pt bold; axis labels use 20pt; tick labels use `tick_params` at 15pt; legends use 15pt; axes use `set_facecolor('#f5f5f5')`; borders/spines use linewidth 2; y-axis grids use `ax1.yaxis.grid(True, linestyle='--', linewidth=0.5, zorder=0)` when applicable; layouts use `plt.tight_layout(rect=[0,0,0.99,1])`.
3. For bar charts, draw bar borders. For polar plots, keep `ax1.spines['polar'].set_visible(True)` and `ax1.spines['polar'].set_linewidth(2)`. For multi-axis figures, apply spine and tick styling consistently, e.g. `for spine in axs[0].spines.values(): spine.set_linewidth(2)` and `axs[0].tick_params(axis='both', labelsize=11)` when matching an existing figure family.

## Paragraph Clarity Check (Important)

Use this quick test whenever the user asks whether a paragraph "flows" or is clear.

1. Read as an external reader:
   - Does this paragraph have one explicit message?
   - Does the first sentence state what this paragraph will do?
   - Are all key nouns/terms readable without hidden context?
   - Does each sentence connect to the previous one with a clear relation (cause, contrast, consequence, refinement, example)?
2. Run reverse outlining for the current section:
   - Write down thesis/main claim.
   - Write down each paragraph topic sentence.
   - Write down the evidence/explanation points under each paragraph.
   - Check mapping: topic sentence -> thesis, and evidence -> topic sentence.
   - Revise or remove any paragraph that cannot be mapped cleanly.
3. If flow is still weak, add temporary section headers and explicit transition phrases during revision, then remove unnecessary headers before finalizing.

Source reference for this check:

- `references/does-my-writing-flow-source.md`

## Section Guides

Load only the needed section file:

- Introduction: `references/introduction.md`
- Abstract: `references/abstract.md`
- Related Work: `references/related-work.md`
- Method: `references/method.md`
- Experiments: `references/experiments.md`
- Conclusion: `references/conclusion.md`
- Paper review (Paper Rview): `references/paper-review.md`
- Paragraph clarity source: `references/does-my-writing-flow-source.md`
- Example bank index: `references/examples/index.md`

## Paper Review Core Points

Use `references/paper-review.md` for the full checklist and workflow.

1. Add an end-of-draft self-review question list in five dimensions:
   - contribution,
   - writing clarity,
   - experimental strength,
   - evaluation completeness,
   - method design soundness.
2. Treat claim-evidence alignment as a hard constraint, especially for Abstract and Introduction.
3. Perform adversarial writing: review as a skeptical reviewer and resolve every high-risk question.
4. Revise until major rejection risks are explicitly addressed.

## Execution Rules

1. Build a mini-outline before drafting prose.
2. For each subsection, explicitly include motivation, design, and technical advantage when applicable.
3. Avoid writing style that looks like incremental patching of a naive baseline.
4. Keep terminology stable across the full paper.
5. If a claim cannot be supported by results, weaken or remove the claim.
6. Before finalizing, append and answer a five-dimension self-review question list, then revise the paper based on unresolved items.
7. Do not load all section references (Introduction/Abstract/Related Work/Method/Experiments/Conclusion) at once; load only the specific section guide needed for the current edit target.

## Output Contract

When asked to rewrite or draft sections, return:

1. A compact section outline (3-7 bullets).
2. Revised paragraphs with explicit paragraph roles (opening/challenge/method/advantage/evidence/limitation).
3. A short self-review checklist covering clarity, flow, terminology consistency, unsupported claims, and missing evidence.
4. A claim-evidence map for each major claim in the revised text using `Claim: ... | Evidence: ... | Status: supported/needs evidence`.
