# Module 03 — Guardrails  
## Change Log (2025-11-30)
- Added `evidence_mode = "strict"` and rules for strict evidence-only summarization.
- Added standardized warnings for missing, empty, or very short sections (< 50 words).
- Strengthened rules preventing hallucinations and use of information not found in the source text.

---

## Guardrail Rules

These rules ensure the summarizer uses only information present in the provided text and signals when a section does not contain enough information for a reliable summary.

---

## 1. Strict Evidence Mode

**Variable:** `evidence_mode`  

When `evidence_mode = "strict"`:

- The summarizer must:
  - Use only claims, equations, findings, or details **explicitly stated** in the section text.
  - Avoid adding external knowledge, interpretations, or assumptions.
  - If the section lacks sufficient detail, output:

    > “The source text does not provide enough detail to summarize this section in strict evidence mode.”

---

## 2. Section Warning Messages

Before summarizing any section:

- **If the section is missing or contains no usable text:**
  - Output:
    > “Section skipped: no usable text was provided.”

- **If the section is very short (fewer than 50 words):**
  - Output:
    > “Section very short: summary may be incomplete.”

Warnings must appear before the generated summary (if a summary is produced).

---

## 3. Grounding and Source-Bound Behavior

Regardless of the mode:

- Summaries must be strictly grounded in the text of the paper.
- The system must:
  - Avoid fabricating results, data, or concepts.
  - Avoid using information from outside the provided text.
  - Avoid inserting citations or references that are not present in the source.

These guardrails apply to both `"short"` and `"detailed"` summary levels.
