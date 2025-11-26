# Research Paper Summarizer — CISC 101 (Group 43)
This repository contains the final project for CISC 101 – Research Paper Summarizer, created by Group 43.
The project implements a modular, guardrail-heavy summarization system designed using meta-prompting, specification integration, and multi-module architecture principles learned during Weeks 2–12.
The system is capable of summarizing multi-section research papers, generating expert and lay summaries, detecting missing or short sections, mitigating hallucinations, and handling long-paper chunking.
 ## Repository Structure
CISC101-Group43-PaperSummarizer/
│
├── README.md
├── system_prompt.md
└── modules/
      ├── 1_intake_setup.md
      ├── 2_section_loop.md
      ├── 3_guardrails.md
      ├── 4_rendering_refinement.md
      ├── 5_citation_extractor.md
      └── 6_equation_explainer.md
## system_prompt.md
Contains the full System Prompt generated from our meta-prompt.
It defines the Summarizer’s greeting rules, tone, required user inputs, boundaries (no hallucinations, no invented citations), output structure (paper summary, section table, expert summary, lay summary, glossary), and all summarizer specifications constraints.
## Modules Overview (Located in /modules/)
### 1. Intake & Setup
1_intake_setup.md
Normalizes user-provided sections, detects missing or <50-word sections, prepares the text for summarization, and triggers long-paper chunking if needed.
### 2. Section Loop
2_section_loop.md
Processes each section in order, extracts its text, applies summarization rules, performs length checks, and stores results for final rendering.
### 3. Guardrails
3_guardrails.md
Implements hallucination mitigation, missing/empty section detection, <50-word safeguards, consistency checks, and context-window safety rules.
### 4. Rendering & Refinement
4_rendering_refinement.md
Builds the final output structure (summary, section table, expert summary, lay summary, glossary, warnings) while maintaining consistent formatting.
### 5. Citation Extractor (Custom Module)
5_citation_extractor.md
Parses and extracts explicit citations or reference identifiers mentioned in the paper and summarizes citation patterns (without inventing any).
### 6. Equation Explainer (Custom Module)
6_equation_explainer.md
Detects equations in the paper and produces clear explanations of their meaning, roles, and assumptions using safe non-hallucinatory descriptions.
 ## How to Use This Project
1. Open system_prompt.md.
2. Copy the full content into an LLM (e.g., Microsoft Copilot or ChatGPT) as the system prompt.
3. Provide:
 - the paper text or chunks
 - your section list
 - your target audience (expert, semi-technical, layperson)
4. The model will process the paper through all modules and generate:
 - an overall summary
 - a section-by-section table
 - expert and lay summaries
 - a mini-glossary
 - citation and equation analysis
 - warnings for missing or short sections
## Group Members
- Zoe Li
- Prithen Ravi
- Arturo Reyes
