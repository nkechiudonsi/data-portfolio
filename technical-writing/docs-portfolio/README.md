# Technical Documentation Portfolio

> **Track record:** 95% client satisfaction rate · Upwork Technical Writer (Feb 2022 – Present)

## Overview

This repository showcases technical writing samples and documentation produced for clients across platforms, including Upwork. The work spans user guides, standard operating procedures (SOPs), API documentation, and process documentation for data and tech projects.

---

## What I Deliver

| Document Type | Description | Typical Use |
|---|---|---|
| **User Guides** | Step-by-step instructions for end users | Software onboarding, product manuals |
| **SOPs** | Standardised procedures for repeatable tasks | Operations, compliance, HR workflows |
| **API Documentation** | Technical reference for developer audiences | RESTful APIs, integration guides |
| **Data Dictionaries** | Field-level definitions for datasets | Analytics, data governance |
| **Process Documentation** | Workflow maps and procedure write-ups | M&E, project operations |
| **Reports** | Analytical reports for non-technical audiences | Executive summaries, donor reports |

---

## Sample Deliverables

### 1. User Guide — Data Entry SOP (Sample)
> *Excerpt from an SOP created for a client's data entry team*

---
**Purpose:** This guide ensures consistent, accurate data entry across all team members.

**Scope:** Applies to all staff entering records into the client management system.

**Procedure:**
1. Log in using your unique staff ID and password
2. Navigate to **Records > New Entry**
3. Complete all mandatory fields (marked with *)
4. Cross-check the client reference number against the paper form
5. Click **Save Draft** before submitting — never submit without review
6. Submit and record the confirmation number in the tracking log

**Common Errors to Avoid:**
- Do not leave the Date field blank — enter N/A if unknown
- Client names must match the master list exactly (check spelling)
- Duplicate entries will be flagged by the system — do not ignore warnings

---

### 2. API Reference Doc — Sample Structure

```markdown
## GET /api/v1/records

Returns a paginated list of records.

**Authentication:** Bearer token required

**Parameters:**
| Parameter | Type | Required | Description |
|---|---|---|---|
| page | integer | No | Page number (default: 1) |
| limit | integer | No | Records per page (default: 20, max: 100) |
| status | string | No | Filter by status: `active`, `archived` |

**Response (200 OK):**
```json
{
  "data": [...],
  "pagination": {
    "page": 1,
    "total": 248,
    "limit": 20
  }
}
```

**Error codes:** 401 Unauthorized · 404 Not Found · 500 Server Error
```

---

## Client Results

| Metric | Result |
|---|---|
| Client satisfaction rate | **95%** |
| Platform | Upwork (Freelance) |
| Active since | February 2022 |
| Document types delivered | User guides, SOPs, API docs, reports |

---

## Writing Principles

1. **Audience-first** — I write for the reader, not the subject matter expert
2. **Plain language** — Complex ideas in simple, clear sentences
3. **Structured for scanning** — Headers, tables, and numbered steps for usability
4. **Accurate** — Technical details verified before publication
5. **Consistent** — Style guides and templates maintained across deliverables

---

## Repository Structure

```
docs-portfolio/
├── samples/
│   ├── user_guide_sample.md          # Anonymised user guide sample
│   ├── sop_sample.md                 # Anonymised SOP sample
│   └── api_reference_sample.md      # API documentation sample
├── templates/
│   ├── user_guide_template.md        # Reusable user guide template
│   ├── sop_template.md               # Reusable SOP template
│   └── api_doc_template.md           # Reusable API doc template
└── README.md
```

---

*Part of [Nkechi Udonsi's Portfolio](../../README.md)*
