# Changelog

## 0.2.1 (2026-10)

Release fix. No new features; the format stays at version 0.2.

- Workbooks: the counts "Answers due for review" and "Evidence due for review" on the Start tab now skip empty rows. Some spreadsheet programs counted every empty row as overdue.
- Templates: each template states when Holdvero last reviewed it and that it is not legal advice. The incident procedure and the sub-processor list link to the official sources.
- Clearer wording about what a hash does and does not show.
- README: "Five documents commonly requested in enterprise questionnaires" instead of an absolute claim.

## 0.2.0 (2026-10)

First public version.

- **Excel workbook** as the main way to use the pack, in English and Dutch: tabs for answers, the evidence register and open items, with dropdowns, red highlighting for dates that have passed and a summary on the Start tab.
- **Fictional example** (Voorbeeld Software B.V., 15 questions) as Excel, YAML and JSON, in English and Dutch.
- **Format 0.2**: answers, evidence register and open items as three linked parts. Short answers include `described` for open questions. The evidence register has an evidence type, version date, review due date, locator, shareability, status, storage reference and an optional hash.
- **Five templates** in Dutch and English: information security policy, incident procedure, sub-processor list, offboarding checklist, controls overview.
- `tools/validate.py` checks Excel workbooks (English or Dutch), YAML and JSON, and converts a workbook to JSON. An automated check runs on every change.

## 0.1.0

Internal draft, not published. Answers with embedded sources and open items.
