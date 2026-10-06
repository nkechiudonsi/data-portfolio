# AI Response Evaluation Toolkit

> A practical framework for scoring and reviewing AI-generated text at scale — built from hands-on annotation work.

## Overview

This toolkit is a collection of scoring rubrics, Python utilities, and documentation templates for evaluating AI language model outputs. It emerged from real annotation work across thousands of AI responses and is designed to be reusable for any AI QA or language evaluation project.

---

## Who This Is For

- AI companies needing structured evaluation frameworks
- Data labelling teams setting up annotation workflows
- Researchers assessing LLM output quality
- Anyone building quality assurance systems for AI content

---

## What's Included

### 1. Scoring Rubrics
Structured rubrics covering:
- **Fluency** — Is the language natural and readable?
- **Relevance** — Does the response address the prompt?
- **Completeness** — Is the answer full and sufficient?
- **Accuracy** — Is the information correct?
- **Safety** — Is the content appropriate and harmless?

### 2. Python QA Utilities

```python
def compute_qa_score(response: dict) -> dict:
    """
    Compute a composite QA score for a single AI response.
    
    Input:
      response = {
        "fluency": 4,        # 1–5
        "relevance": 5,      # 1–5
        "completeness": 3,   # 1–5
        "accuracy": 4,       # 1–5
        "safety": 5          # 1–5
      }
    
    Output:
      {"composite_score": 4.2, "grade": "Good", "flags": []}
    """
    weights = {
        "fluency": 0.15,
        "relevance": 0.30,
        "completeness": 0.25,
        "accuracy": 0.20,
        "safety": 0.10
    }
    composite = sum(response[k] * v for k, v in weights.items())
    grade = "Excellent" if composite >= 4.5 else \
            "Good" if composite >= 3.5 else \
            "Fair" if composite >= 2.5 else "Poor"
    flags = [k for k, v in response.items() if v <= 2]
    return {"composite_score": round(composite, 2), "grade": grade, "flags": flags}
```

### 3. Batch Analysis Pipeline
- Load annotation exports (CSV/JSON)
- Compute aggregate scores by category or date range
- Flag responses below threshold for review
- Export summary reports

### 4. Annotation Templates
- Excel-based scoring sheets
- JSON schema for structured annotation data
- Markdown documentation guides

---

## Key Metrics Tracked

| Dimension | Weight | Why It Matters |
|---|---|---|
| Relevance | 30% | Most critical — irrelevant responses are useless |
| Completeness | 25% | Partial answers cause user frustration |
| Accuracy | 20% | Factual errors erode trust |
| Fluency | 15% | Readability affects perception |
| Safety | 10% | Non-negotiable floor |

---

## Repository Structure

```
ai-eval-toolkit/
├── rubrics/
│   ├── qa_scoring_rubric.md          # Full scoring criteria
│   └── annotation_guidelines.md     # Annotator reference
├── scripts/
│   ├── qa_scorer.py                  # Core scoring functions
│   ├── batch_analysis.py             # Batch processing pipeline
│   └── report_generator.py          # Summary report output
├── templates/
│   ├── scoring_sheet.xlsx            # Excel annotation template
│   └── annotation_schema.json        # JSON schema for structured data
├── notebooks/
│   └── qa_analysis_demo.ipynb        # Demo walkthrough
└── README.md
```

---

## Tools & Technologies

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-000000?style=flat&logo=json&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)

---

*Part of [Nkechi Udonsi's AI & Language Ops Portfolio](../../README.md)*
