# Data Documentation Templates

> Reusable templates for data dictionaries, annotation guidelines, M&E reporting, and data governance documentation.

## Overview

Good data documentation is as important as good data. This repository contains templates and examples for the documentation that makes data projects trustworthy, reproducible, and understandable by anyone who picks them up.

---

## Why Data Documentation Matters

- A dataset without a data dictionary is a dataset only its creator can use
- Annotation work without guidelines produces inconsistent, unusable labels
- M&E reports without methodology sections cannot be audited or reproduced
- Data without lineage documentation cannot be trusted

This repository addresses all of these.

---

## Contents

### 1. Data Dictionary Template

A data dictionary defines every field in a dataset: what it means, what values are valid, and where it comes from.

**Example structure:**

| Field Name | Description | Data Type | Valid Values | Required | Example |
|---|---|---|---|---|---|
| `client_id` | Unique identifier for each client | String | UUID format | Yes | `CLT-00482` |
| `registration_date` | Date client registered | Date | YYYY-MM-DD | Yes | `2023-04-15` |
| `status` | Current client status | String | `active`, `inactive`, `pending` | Yes | `active` |
| `region` | Geographic region | String | See Region Codes table | No | `South-East` |
| `total_visits` | Count of all facility visits | Integer | ≥ 0 | No | `7` |

---

### 2. Annotation Guidelines Template

For AI/ML annotation projects — defines what annotators should and should not do.

**Standard sections:**
1. **Task Overview** — What is being annotated and why
2. **Rating Scale** — What each score means, with examples
3. **Decision Rules** — How to handle edge cases
4. **Do's and Don'ts** — Common mistakes to avoid
5. **Examples** — At least 3 labelled examples per category
6. **Escalation** — What to flag for supervisor review

---

### 3. M&E Report Template

For monitoring and evaluation contexts (USAID, NGO, government programmes):

```markdown
# Routine Data Quality Assessment Report

**Programme:** [Programme Name]
**Reporting Period:** [Month Year]
**LGA/Facility:** [Name]
**Assessor:** [Name]
**Date of Assessment:** [Date]

## Executive Summary
[2–3 sentence summary of findings]

## Data Quality Dimensions Assessed

| Dimension | Score (%) | Status |
|---|---|---|
| Completeness | | |
| Accuracy | | |
| Timeliness | | |
| Consistency | | |

## Findings
[Narrative findings by dimension]

## Recommendations
1. [Recommendation 1]
2. [Recommendation 2]

## Action Plan
| Action | Responsible | Deadline |
|---|---|---|
| | | |
```

---

### 4. Dataset README Template

For any dataset shared publicly or within a team:

```markdown
# Dataset Name

## Description
What this dataset contains and what it is for.

## Source
Where the data came from, when it was collected, and by whom.

## File Structure
| File | Description |
|---|---|
| `data.csv` | Main dataset |
| `README.md` | This file |

## Data Dictionary
[Link or inline table]

## Usage
How to load and use the data (with code example).

## Limitations
Known issues, gaps, or caveats.

## Contact
Who to contact with questions.
```

---

## Repository Structure

```
data-docs/
├── templates/
│   ├── data_dictionary_template.xlsx   # Excel data dictionary template
│   ├── annotation_guidelines_template.md
│   ├── me_report_template.md           # M&E RDQA report template
│   └── dataset_readme_template.md      # Dataset README template
├── examples/
│   ├── sample_data_dictionary.md       # Filled example
│   └── sample_annotation_guide.md      # Filled example
└── README.md
```

---

*Part of [Nkechi Udonsi's Portfolio](../../README.md)*
