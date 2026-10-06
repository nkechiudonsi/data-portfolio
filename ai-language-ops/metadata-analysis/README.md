# Metadata Analysis — AI Data Pipeline

> **Scale:** 59,103 metadata items processed · Quality validation for machine learning pipelines

## Overview

This repository documents the methodology for processing and quality-reviewing large volumes of metadata items generated during AI language annotation projects. Metadata quality directly impacts model training quality — a mislabelled item propagates errors into every model trained on that data.

---

## Why Metadata Quality Matters in AI

When AI companies collect annotation data, each response carries metadata:
- Language pair tags
- Task category labels
- Annotator identifiers
- Timestamp and session data
- Content domain tags
- Confidence flags

If these tags are inconsistent or wrong, the training signal is corrupted. This work ensured **59,103+ metadata records** met quality standards before being passed downstream.

---

## Methodology

### Step 1: Metadata Inventory
- Load all metadata records from platform export files
- Count and categorise by field type
- Identify missing, null, or empty fields

### Step 2: Consistency Checks
- Cross-reference language tags against actual content
- Validate category labels against master taxonomy
- Check timestamp sequences for logical order

### Step 3: Error Detection
- Flag duplicate record IDs
- Detect conflicting labels on same item
- Identify records with missing mandatory fields

### Step 4: Correction & Escalation
- Auto-correct clear formatting errors (e.g. case normalisation)
- Escalate ambiguous errors for human review
- Log all changes with before/after audit trail

---

## Scale of Work

```
Total metadata items reviewed:   59,103
Processing period:                Ongoing across annotation project
Platform:                         OneForma / Scribo WorkReport
Error detection rate:             Flagged items for correction
Final pass rate:                  Quality-approved items passed downstream
```

---

## Sample Processing Script

```python
import pandas as pd
import json

def validate_metadata(df, required_fields, valid_categories):
    """
    Validate a metadata dataframe against expected schema.
    Returns a validation report.
    """
    report = {
        "total_records": len(df),
        "missing_fields": {},
        "invalid_categories": [],
        "duplicate_ids": int(df['item_id'].duplicated().sum()),
        "flagged_for_review": 0
    }
    
    # Check required fields
    for field in required_fields:
        null_count = df[field].isnull().sum()
        if null_count > 0:
            report["missing_fields"][field] = int(null_count)
    
    # Check category values
    if 'category' in df.columns:
        invalid = df[~df['category'].isin(valid_categories)]
        report["invalid_categories"] = invalid['item_id'].tolist()
    
    # Total flags
    report["flagged_for_review"] = (
        sum(report["missing_fields"].values()) +
        len(report["invalid_categories"]) +
        report["duplicate_ids"]
    )
    
    return report

# Example usage
required = ['item_id', 'language', 'category', 'annotator_id', 'timestamp']
valid_cats = ['fluency', 'relevance', 'safety', 'accuracy', 'completeness']

# df = pd.read_csv('metadata_export.csv')
# report = validate_metadata(df, required, valid_cats)
# print(json.dumps(report, indent=2))
```

---

## Key Skills Demonstrated

- Large-scale metadata processing and quality control
- Schema validation for structured annotation data
- Audit trail documentation
- Error detection and escalation workflows
- Data pipeline quality assurance

---

## Repository Structure

```
metadata-analysis/
├── scripts/
│   ├── metadata_validator.py         # Core validation functions
│   ├── consistency_checker.py        # Cross-field consistency checks
│   └── audit_logger.py              # Change logging utilities
├── schemas/
│   └── metadata_schema.json          # Expected metadata schema definition
├── notebooks/
│   └── metadata_analysis_demo.ipynb  # Demonstration with sample data
├── reports/
│   └── sample_validation_report.json # Sample output report
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
