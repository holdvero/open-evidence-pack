# Open Evidence Pack format, version 0.2

*Nederlands: [specificatie.md](specificatie.md)*

An open, practical format for keeping questionnaire answers connected to the evidence behind them. This page describes every field. The JSON schema is [evidence-pack.schema.json](evidence-pack.schema.json).

The format has one data model and two ways to write it down:

- **Excel** (the main way): the workbook in `excel/`, in English or Dutch.
- **YAML or JSON**: for people who keep their answers in Git or want to process them with tools.

`tools/validate.py` reads all three and checks them against the same rules.

## Structure

A pack has three parts:

| Part | Excel tab (EN / NL) | YAML / JSON key |
| --- | --- | --- |
| Answers | Answers / Antwoorden | `answers` |
| Evidence register | Evidence register / Bewijsregister | `evidence` |
| Open items | Open items / Open punten | `open_items` |

Plus some details about the pack itself:

| Field | Excel | Required | Meaning |
| --- | --- | --- | --- |
| `format_version` | (implied) | yes | `"0.2"` |
| `organisation.name` | Start tab, Organisation | yes | Your organisation |
| `organisation.website` | Start tab, Website | no | Your website |
| `as_of` | Start tab, As of | no | Date the pack reflects |
| `default_language` | (implied by the workbook language) | no | Language tag, such as `en` or `nl` |

## Answers

| Field | Excel column (EN / NL) | Required | Meaning | Values |
| --- | --- | --- | --- | --- |
| `question_id` | Question ID / Vraag-ID | yes | Your own stable code for the question, e.g. Q-014. Letters, digits, . _ - |  |
| `category` | Category / Categorie | no | Free grouping, e.g. Access, Privacy, AI. |  |
| `question` | Question / Vraag | yes | The question in a general form. Customers word it differently; keep the essence. |  |
| `short_answer` | Short answer / Kort antwoord | yes | Yes, no, partly, described (for open questions such as Who...? or How often...?) or not applicable. | `yes`, `no`, `partly`, `described`, `not_applicable` |
| `approved_answer` | Approved answer / Goedgekeurd antwoord | yes | The answer as you would send it. Start with the short answer, then one or two sentences. |  |
| `answer_status` | Answer status / Status antwoord | yes | How well the answer is supported by evidence. See the Start tab. | `evidenced`, `partial`, `open_item`, `explained_no`, `not_applicable` |
| `answer_owner` | Answer owner / Eigenaar antwoord | yes | Who keeps this answer true. A role is fine. |  |
| `last_reviewed` | Last reviewed / Laatst herzien | yes | When someone last checked that the answer is still true. | `yyyy-mm-dd` |
| `next_review` | Next review / Volgende herziening | yes | When it must be checked again. Turns red when it has passed. | `yyyy-mm-dd` |
| `evidence` | Evidence / Bewijs | no | Evidence IDs from the Evidence register, separated by ; with an optional location after the ID. Example: BEL-01 §3; SCR-01 | list |
| `open_item_ids` | Open item IDs / Open punten | no | IDs from the Open items tab, separated by ;. Required for partial and open item. | list |
| `framework_refs` | Framework refs / Kaderverwijzingen | no | Reference numbers only, separated by ;. Example: ISO/IEC 27001:2022 A.8.5. Never copy text from paid standards. | list |
| `notes` | Notes / Notities | no | Internal notes. |  |

## Evidence register

| Field | Excel column (EN / NL) | Required | Meaning | Values |
| --- | --- | --- | --- | --- |
| `evidence_id` | Evidence ID / Bewijs-ID | yes | Your own stable code, e.g. BEL-01 or EVD-003. |  |
| `title` | Title / Titel | yes | Name of the document, record, setting or result. |  |
| `evidence_type` | Evidence type / Soort bewijs | yes | What kind of evidence this is. Choose from the list. | `policy`, `procedure`, `record`, `documentation`, `configuration`, `system_generated`, `screenshot`, `test_result`, `audit_report`, `certificate`, `contract`, `other` |
| `version` | Version / Versie | yes | Version label, e.g. 2.1, Q3 2026 or a date. |  |
| `version_date` | Version date / Versiedatum | yes | Date this version was approved, issued, exported or captured. | `yyyy-mm-dd` |
| `owner` | Owner / Eigenaar | yes | Who keeps this evidence current. |  |
| `review_due` | Review due / Herzien voor | no | When it must be reviewed or renewed. Most documents do not expire; they are due for review. Turns red when passed. | `yyyy-mm-dd` |
| `locator` | Locator / Vindplaats | no | Default location inside the evidence (section, page, setting). Answers can give a more precise one. |  |
| `shareable` | Shareable / Deelbaar | no | Whether you may share it with customers, and how. | `public`, `on_request`, `under_nda`, `internal_only` |
| `status` | Status / Status | yes | Current, draft, superseded or withdrawn. Answers should rely on current evidence. | `current`, `draft`, `superseded`, `withdrawn` |
| `storage_reference` | Storage reference / Opslaglocatie | no | Where the evidence is kept, as an internal reference. Never put confidential documents in this file. |  |
| `hash_algorithm` | Hash algorithm / Hash-algoritme | no | sha256, sha384 or sha512. Required when you fill in a hash. | `sha256`, `sha384`, `sha512` |
| `hash` | Hash / Hash | no | Fingerprint of the file. A stored hash lets you later verify whether a file is identical to the version that was registered. It does not show that a control is effective. |  |
| `notes` | Notes / Notities | no | Internal notes. |  |

## Open items

| Field | Excel column (EN / NL) | Required | Meaning | Values |
| --- | --- | --- | --- | --- |
| `open_item_id` | Open item ID / Open-punt-ID | yes | Your own stable code, e.g. OI-01. |  |
| `description` | Description / Omschrijving | yes | What is missing and what you will do. |  |
| `related_question_ids` | Related question IDs / Betreft vragen | yes | Question IDs from the Answers tab, separated by ;. | list |
| `owner` | Owner / Eigenaar | yes | Who does it. |  |
| `target_date` | Target date / Streefdatum | yes | When it should be done. Turns red when passed and not closed. | `yyyy-mm-dd` |
| `status` | Status / Status | yes | Open, in progress or closed. | `open`, `in_progress`, `closed` |
| `resolution_note` | Resolution note / Afhandeling | no | How it was resolved. Required when closed. |  |

## Rules

**Short answers.** `yes`, `no` and `partly` for closed questions. `described` for open questions such as *Who is responsible…?* or *How often…?*, where the answer is a description. `not_applicable` when the question does not apply.

**Answer statuses.**

| `answer_status` | Use when | Rules |
| --- | --- | --- |
| `evidenced` | The answer is true and you can show it | At least one evidence reference. The short answer can be `yes`, `no` or `partly`: to *Can your AI issue refunds without approval?* the evidenced answer is no |
| `partial` | Mostly in place and evidenced; a smaller remaining part is planned | `short_answer` is `partly`; at least one open item |
| `open_item` | The main thing asked is not in place yet, with a plan | At least one open item |
| `explained_no` | The honest answer is no and that is a gap; you explain why or what you do instead | `short_answer` is `no` |
| `not_applicable` | The question does not apply to you | `short_answer` is `not_applicable`, and the other way round |

Statuses describe how well an answer is supported by evidence. They are not a certification.

**References.** Every evidence reference in an answer must exist in the evidence register. Every open item an answer refers to must exist, and every question an open item refers to must exist. IDs must be unique within their part.

**Dates.** All dates are written as `yyyy-mm-dd`. `next_review` may not lie before `last_reviewed`. The check warns when a review date or target date has passed.

**Open items.** A closed open item needs a `resolution_note`. If all open items of a *partial* or *open item* answer are closed, the check reminds you to update the answer.

**Hashes.** A hash needs a `hash_algorithm` and must have the right length: 64 characters for sha256, 96 for sha384, 128 for sha512. A hash identifies the exact version of a file. It does not prove that a control works.

## Writing references and lists in Excel

- **Evidence**: evidence IDs separated by `;`. After an ID you may add where in the evidence the support is, separated by a space: `BEL-01 §3; PRO-04 §2; SCR-01`. In YAML/JSON this becomes a list of `{evidence_id, locator}`.
- **Open item IDs, related question IDs**: separated by `;` (a comma also works).
- **Framework refs**: separated by `;`. Reference numbers only, such as `ISO/IEC 27001:2022 A.8.5`. Never copy text from paid standards.

## Dutch workbook values

The Dutch workbook shows Dutch dropdown values. The check translates them to the canonical values used in YAML/JSON:

| Field | Dutch workbook | Canonical value |
| --- | --- | --- |
| `short_answer` | ja, nee, deels, beschreven, n.v.t. | `yes`, `no`, `partly`, `described`, `not_applicable` |
| `answer_status` | onderbouwd, deels onderbouwd, open punt, nee met uitleg, n.v.t. | `evidenced`, `partial`, `open_item`, `explained_no`, `not_applicable` |
| `evidence_type` | beleid, procedure, registratie, documentatie, configuratie, systeemexport, schermafdruk, testresultaat, auditrapport, certificaat, contract, overig | `policy`, `procedure`, `record`, `documentation`, `configuration`, `system_generated`, `screenshot`, `test_result`, `audit_report`, `certificate`, `contract`, `other` |
| `shareable` | openbaar, op aanvraag, onder NDA, alleen intern | `public`, `on_request`, `under_nda`, `internal_only` |
| `status (evidence)` | actueel, concept, vervangen, ingetrokken | `current`, `draft`, `superseded`, `withdrawn` |
| `status (open items)` | open, bezig, afgerond | `open`, `in_progress`, `closed` |

## Extension fields

Extra columns you add to the workbook are kept as `x_` fields (a column *Customer* becomes `x_customer`). In YAML or JSON, give your own fields a name that starts with `x_`. Tools must keep these fields and may ignore them.

## Versioning

This is version 0.2. Fields may still change before 1.0. Every YAML/JSON file states its `format_version`. Changes are listed in [CHANGELOG.md](../CHANGELOG.md).

## Relation to other formats

The format is deliberately small. It is not a replacement for formal, machine-readable control and assessment formats such as NIST OSCAL. Mapping or exporting to such formats where useful is a design goal for later versions, not a current feature.

## Licence

This description is licensed under CC BY 4.0. The schema and the tools are licensed under MIT.
