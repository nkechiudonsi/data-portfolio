# Data Quality & Cleaning Pipeline

> A reusable, documented framework for cleaning and validating business datasets — achieving 95% data accuracy.

## Overview

This repository contains a generalised data cleaning and validation pipeline built from real-world work across multiple datasets. Designed to be adapted for any tabular business dataset, it covers the full data preparation lifecycle: from raw, inconsistent input to clean, analysis-ready output.

---

## The Problem with Dirty Data

Real-world business data is messy. Common issues include:
- Duplicate records from manual entry
- Inconsistent category naming ("Lagos", "LAGOS", "Lagos State")
- Missing values (blank cells, null entries)
- Outliers from data entry errors
- Date format inconsistencies

This pipeline handles all of the above systematically and reproducibly.

---

## Pipeline Stages

```
Raw Data → [1. Audit] → [2. Standardise] → [3. Impute/Remove] → [4. Validate] → Clean Data
```

### Stage 1: Data Audit
- Row/column counts
- Null value summary
- Duplicate detection
- Data type check
- Value distribution scan

### Stage 2: Standardisation
- Trim whitespace
- Normalise text case
- Standardise date formats
- Harmonise categorical values

### Stage 3: Imputation / Removal
- Fill missing numerics with median/mean (context-dependent)
- Drop rows where critical fields are empty
- Flag (not delete) statistical outliers for review

### Stage 4: Validation
- Re-run audit to confirm improvement
- Cross-check against known reference values
- Log all changes with before/after counts

---

## Sample Code

```python
import pandas as pd
import numpy as np

def audit_data(df):
    """Returns a summary of data quality issues."""
    report = {
        'shape': df.shape,
        'nulls': df.isnull().sum().to_dict(),
        'duplicates': df.duplicated().sum(),
        'dtypes': df.dtypes.astype(str).to_dict()
    }
    return report

def standardise_text(df, columns):
    """Strip whitespace and normalise case for text columns."""
    for col in columns:
        df[col] = df[col].astype(str).str.strip().str.title()
    return df

def remove_duplicates(df, subset=None):
    """Remove duplicate rows, optionally based on key columns."""
    before = len(df)
    df = df.drop_duplicates(subset=subset, keep='first')
    print(f"Removed {before - len(df)} duplicates.")
    return df

def flag_outliers(df, column, threshold=3):
    """Flag rows where a numeric column is beyond N standard deviations."""
    mean, std = df[column].mean(), df[column].std()
    df[f'{column}_outlier'] = (abs(df[column] - mean) > threshold * std)
    return df
```

---

## Results

| Metric | Before Cleaning | After Cleaning |
|---|---|---|
| Data accuracy (estimated) | ~65–70% | **95%** |
| Null values | High (varies) | Near zero on key fields |
| Duplicate rows | Present | Eliminated |
| Processing time (manual) | Hours | **Minutes (automated)** |

---

## Tools & Technologies

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)

---

## Repository Structure

```
data-quality/
├── notebooks/
│   └── data_cleaning_pipeline.ipynb    # Full walkthrough with a sample dataset
├── scripts/
│   ├── audit.py                         # Data audit functions
│   ├── standardise.py                   # Standardisation functions
│   └── validate.py                      # Post-cleaning validation
├── data/
│   └── sample_raw_data.csv              # Anonymised sample dataset
└── README.md
```

---

*Part of [Nkechi Udonsi's Data Portfolio](../../README.md)*
