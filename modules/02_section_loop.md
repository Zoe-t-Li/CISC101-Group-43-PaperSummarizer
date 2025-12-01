# Module 02 — Section Loop  
## Change Log (2025-11-30)
- Added `summary_level` variable with `"short"` and `"detailed"` modes.
- Added conditional behavior: short summary (1–2 sentences) or detailed summary (paragraph + 3–5 bullet points).
- Ensured summaries still follow the 200-word maximum.
- Updated instructions to match the original module’s style while incorporating new requirements.



## Section Loop Instructions

For each section, the system must extract the section text, generate a summary following the configured rules, apply length constraints, and store the summarized content in a structured format. The detail level of the summary is controlled by the `summary_level` variable.



## Summary Level Configuration

- `summary_level = "short"`  
  - Produce a compact 1–2 sentence summary of the section.

- `summary_level = "detailed"`  
  - Produce:
    - A short descriptive paragraph, **and**
    - A bullet list of **3–5 key points** extracted directly from the section.



## Section Loop

For each section:

1. **Extract the section text.**

2. **Summarize the section according to `summary_level`:**

   - **If `summary_level = "short"`**  
     Generate a concise summary of 1–2 sentences focusing on the central idea.

   - **If `summary_level = "detailed"`**  
     Produce a short paragraph describing the section’s main ideas, followed by 3–5 bullet points highlighting specific details, steps, or results.

3. **Enforce the length constraint:**  
   - The complete summary (paragraph + bullets if detailed) must not exceed **200 words**.

4. **Store** the summary in the system’s structured output format.
