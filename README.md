# Open Evidence Pack

*Nederlands: [README.nl.md](README.nl.md)*

**An open, practical format for keeping questionnaire answers connected to the evidence behind them.**

For B2B SaaS and IT suppliers who answer security, privacy, NIS2 and AI questionnaires from their customers. Most questionnaires ask the same questions. This pack helps you keep one set of approved answers, each linked to the evidence that supports it, with an owner, a review date and honest open items.

Made by [Holdvero](https://holdvero.com). *Prove what you claim.*

## Start here (no coding needed)

1. Download the workbook: [English](excel/open-evidence-pack-en.xlsx) or [Dutch](excel/open-evidence-pack-nl.xlsx).
2. Open the fictional example to see it filled in: [example-evidence-pack-en.xlsx](examples/example-evidence-pack-en.xlsx).
3. Fill in your own evidence, answers and open items. The **Start** tab explains each step.

The workbook has three working tabs:

| Tab | What goes in it |
| --- | --- |
| **Answers** | The questions you get again and again, the answer you have approved, its status, owner, review dates and the evidence behind it. |
| **Evidence register** | Every document, record, setting or result you can show: type, version, owner, review date, where it is kept and whether you can share it. |
| **Open items** | What is not in place yet, who will fix it and by when. |

Dropdowns keep the values consistent. Dates that have passed turn red, so you can see what needs attention.

## What is inside

| Folder | What | Licence |
| --- | --- | --- |
| `excel/` | The empty workbook, in English and Dutch | CC BY 4.0 |
| `examples/` | A fictional, filled-in example as Excel, YAML and JSON, in English and Dutch | CC BY 4.0 |
| `templates/` | Five document templates in English and Dutch | CC BY 4.0 |
| `format/` | The description of the format, and a JSON schema | Description CC BY 4.0, schema MIT |
| `tools/` | A small script that checks a workbook or file | MIT |

### The five templates

Five documents commonly requested in enterprise questionnaires. Each one ends with **"What a reviewer looks for"**.

1. [Information security policy](templates/en/01-information-security-policy.md)
2. [Incident procedure](templates/en/02-incident-procedure.md)
3. [Sub-processor list](templates/en/03-sub-processors.md)
4. [Offboarding checklist](templates/en/04-offboarding-checklist.md)
5. [Controls overview](templates/en/05-controls-overview.md)

## How it works

1. **Register your evidence.** Give each document, record, setting or result a code, such as `BEL-01` or `EVD-003`.
2. **Write approved answers.** Start with yes, no or partly (or, for an open question, the description itself), then one or two sentences. Link the evidence codes, with a section if useful: `BEL-01 §3; SCR-01`.
3. **Be honest about gaps.** Where evidence is missing, do not write yes. Use the status *partial* or *open item* and add an open item with an owner and a target date.
4. **Review.** Every answer has a next review date, every piece of evidence a review due date. Red means it needs attention.
5. **Reuse.** When the next questionnaire arrives, start from your approved answers instead of a blank spreadsheet. Check that they are still true before you send them.

### Answer statuses

| Status | Meaning |
| --- | --- |
| `evidenced` | True and supported by evidence in the register. The short answer can be yes, no or partly. |
| `partial` | Mostly in place and evidenced. A smaller remaining part is an open item. |
| `open_item` | The main thing asked is not in place yet. There is an open item with a plan. |
| `explained_no` | Honestly no (a gap), with an explanation of what you do instead. |
| `not_applicable` | The question does not apply to you, with the reason. |

Statuses describe how well an answer is supported by evidence. **They are not a certification.**

## What it is, and what it is not

**It is** a lightweight, operational format for supplier questionnaires: Excel first, with YAML and JSON for those who want them. It is meant to be used by the person who actually answers the questionnaires.

**It is not:**

- an industry standard or a certification;
- legal advice, or proof that you comply with ISO/IEC 27001, NIS2, the GDPR or any other framework;
- a tool that fills in questionnaires for you;
- a place to store confidential documents. The register points to where evidence is kept; the evidence itself stays in your own systems.

## Why not OSCAL?

[OSCAL](https://pages.nist.gov/OSCAL/), developed by NIST, is a set of machine-readable formats for control catalogues, baselines, system security plans, assessment plans and results, and plans of action. It is the right choice for formal assessments and for organisations that manage controls at scale.

The Open Evidence Pack has a smaller job: helping a supplier keep its questionnaire answers connected to its evidence, in a spreadsheet that a non-specialist can maintain. The two are not competitors. Mapping or exporting to OSCAL where that is useful is a design goal for later versions; it is not something the pack does today.

## Security and privacy

- Do not put confidential documents, customer data or questionnaire content you received under NDA in the pack.
- Use internal references in *Storage reference*, never public links to confidential files.
- Mark in *Shareable* what you may share with customers: public, on request, under NDA or internal only.
- A **hash** is a fingerprint of a file. A stored hash lets you later verify whether a file is identical to the version that was registered. **It does not show that a control is effective.**
- You remain responsible for every answer you approve and send to a customer.

## Extending it

Add your own columns to the workbook if you need them, for example *Customer* or *Product*. They are kept as extension fields (`x_customer`) and do not break the check. In YAML or JSON, start your own field names with `x_`.

## Checking a workbook or file (optional)

For technical users. The check works on the Excel workbook (English or Dutch), YAML and JSON.

```bash
pip install jsonschema pyyaml openpyxl
python tools/validate.py excel/my-evidence-pack.xlsx
```

It reports errors (missing or wrong values, evidence codes that do not exist, duplicate IDs) and warnings (review and target dates that have passed). `--to-json out.json` converts a workbook to JSON. See [format/specification.md](format/specification.md) for every field.

## Licence

The workbooks, examples, templates and documentation are licensed under **CC BY 4.0**, with an extra permission: filled-in copies you use internally or share with customers, auditors or advisers need no credit. See [LICENSE-CONTENT.md](LICENSE-CONTENT.md). The JSON schema and the tools are licensed under **MIT** (see [LICENSE](LICENSE)). GitHub shows "MIT" for this repository because of the `LICENSE` file; that licence covers only the schema and the code.

## Versions

This is version 0.2 of the format. Fields may still change before 1.0. See [CHANGELOG.md](CHANGELOG.md). Suggestions are welcome as an issue.

## Disclaimer

The templates and the workbook are a starting point, not legal advice and not a certification. You remain responsible for what you write and send to your customers. Everything in `examples/` is about a fictional company.

## Contributing

Suggestions are welcome. Open an issue with what you would change and why. Never include confidential or customer information. See [CONTRIBUTING.md](CONTRIBUTING.md).

## About Holdvero

Holdvero helps SaaS and IT suppliers in the Netherlands and Belgium answer their customers' security, privacy, NIS2 and AI questionnaires with evidence, and keep that evidence current. Have a questionnaire to complete now, or getting the same questions again and again? See [holdvero.com](https://holdvero.com).
