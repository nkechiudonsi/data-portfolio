# Language Acceptability Annotation Study

> **Scale:** 3,142 acceptability hits · 58.79+ judging hours · 59,103 metadata items processed

## Project Overview

This repository documents the methodology and findings from an AI language acceptability evaluation project completed on the **OneForma / Scribo WorkReport (The Translation Gate)** platform. The work contributed to improving machine learning data pipelines by systematically evaluating AI-generated text for language quality, acceptability, and factual accuracy.

---

## What is Language Acceptability Evaluation?

In AI/ML development, language annotators assess whether AI-generated responses are:
- **Linguistically correct** — proper grammar, syntax, and fluency
- **Contextually appropriate** — relevant, coherent, and on-topic
- **Factually sound** — not hallucinated or misleading
- **Safe and acceptable** — free from harmful, biased, or offensive content

This data trains and improves AI language models, making annotation a critical step in the AI development pipeline.

---

## Project Scope & Scale

| Metric | Value |
|---|---|
| Total acceptability hits completed | **3,142** |
| Total judging hours | **58.79+** |
| Metadata items processed | **59,103** |
| Platform | OneForma / Scribo WorkReport |
| Primary evaluation focus | English language AI outputs |

---

## Evaluation Framework

Each AI response was assessed across multiple dimensions:

### 1. Language Quality
- Grammar and syntax correctness
- Fluency and naturalness of expression
- Vocabulary appropriateness

### 2. Response Relevance
- Does the response address the prompt?
- Is it complete? Is it over-padded?
- Logical coherence and internal consistency

### 3. Acceptability Rating
Final ratings assigned on a structured scale:
```
5 - Excellent: No issues, fully acceptable
4 - Good: Minor issues, generally acceptable
3 - Fair: Noticeable issues, borderline acceptable
2 - Poor: Significant issues, not acceptable
1 - Unacceptable: Fundamentally flawed
```

### 4. Metadata Tagging
Each response tagged with:
- Language pair identifiers
- Content category
- Error type labels (where applicable)
- Confidence score

---

## Key Insights from the Work

- AI-generated text commonly fails on **contextual coherence** before it fails on grammar
- **Over-verbose responses** were a frequent issue — often rated down even when technically correct
- Igbo-language inputs produced noticeably different acceptability distributions than English-only tasks
- Metadata consistency is critical: mislabelled items propagate errors into downstream model training

---

## Skills Demonstrated

- AI output quality assessment (QA scoring)
- Structured annotation under production guidelines
- Metadata tagging and validation
- Cross-lingual evaluation (English / Igbo)
- High-volume, time-sensitive task completion
- Pattern recognition across large annotation sets

---

## Repository Structure

```
annotation-study/
├── docs/
│   ├── evaluation_framework.md       # Full evaluation criteria documentation
│   └── annotation_guidelines.md     # Annotator reference guide
├── analysis/
│   ├── annotation_stats.ipynb        # Statistical summary of completed work
│   └── rating_distribution.png      # Chart of rating distributions
├── templates/
│   └── scoring_rubric_template.xlsx  # Reusable scoring template
└── README.md
```

---

## Tools & Technologies

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![OneForma](https://img.shields.io/badge/Platform-OneForma-FF6B35?style=flat)

---

*Part of [Nkechi Udonsi's AI & Language Ops Portfolio](../../README.md)*
