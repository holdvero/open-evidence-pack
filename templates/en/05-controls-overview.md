# Controls overview

> **Template from the [Open Evidence Pack](https://github.com/holdvero/open-evidence-pack)**, CC BY 4.0, made by [Holdvero](https://holdvero.com).
>
> **Last reviewed by Holdvero: 2026-10-11.** This template is a starting point, not legal advice. Verify the legal, contractual and regulatory requirements that apply to you before you adopt it.
>
> **How to use this template** (delete this block when you are done)
> 1. For each control, fill in whether you apply it: **Yes**, **Partly** or **No**.
> 2. Write briefly why, and how you do it. For **No** or **Partly**: why not, and whether you plan to.
> 3. For every **Yes**, point to evidence: a document, a setting, a record. Without evidence it is a **Partly**. Using the Open Evidence Pack workbook? Put the evidence codes from your evidence register in the *Our evidence* column.
> 4. Put everything that is **Partly** or **No** but should be in place in the open items list at the bottom, with an owner and a date.
>
> **About ISO/IEC 27001.** This overview is a lightweight first step, grouped into the same four themes as ISO/IEC 27002:2022 (organisational, people, physical, technological). It is not a full *Statement of Applicability*: for that, you must assess every control in Annex A of ISO/IEC 27001. If you want to certify later, you can use this overview as a starting point.

| | |
| --- | --- |
| Organisation | [Company name Ltd] |
| Scope | [For example: the platform [name], and the organisation that develops and supports it] |
| Document owner | [Name, role] |
| Version | [1.0] |
| Date | [yyyy-mm-dd] |
| Next review | [yyyy-mm-dd] |

**Legend Applied:** Yes · Partly · No · N/A (not applicable, with reason)

## 1. Organisational

| # | Control | Typical evidence | Applied | Explanation: why and how | Our evidence | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| O1 | There is a security policy, approved by management | Policy with name and date of approval | [ ] | | [Document, version] | [Name] |
| O2 | Security tasks and responsibilities are assigned to people | Roles table in the policy | [ ] | | | |
| O3 | There is an overview of systems, devices and data | List of systems and devices | [ ] | | | |
| O4 | Data is classified by sensitivity, with rules per level | Classification in the policy | [ ] | | | |
| O5 | Access is granted only when needed, and reviewed periodically | Record of the latest review | [ ] | | | |
| O6 | Suppliers are assessed before they receive data; agreements are in writing | Sub-processor list, data processing agreements | [ ] | | | |
| O7 | Incidents are reported, handled and reviewed | Incident procedure, incident register | [ ] | | | |
| O8 | There is a plan for outages of critical services or suppliers | Continuity plan, latest test | [ ] | | | |
| O9 | Legal and contractual requirements (such as GDPR, NIS2, customer contracts) are identified | Overview of requirements | [ ] | | | |
| O10 | Risks are assessed and treated periodically | Risk assessment with date | [ ] | | | |
| O11 | Controls are checked periodically to see if they work | Internal review report | [ ] | | | |

## 2. People

| # | Control | Typical evidence | Applied | Explanation: why and how | Our evidence | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| P1 | New people are screened when hired, in line with their role | Procedure, for example reference check or certificate of conduct | [ ] | | | |
| P2 | Confidentiality is included in contracts | Clause in employment or service agreement | [ ] | | | |
| P3 | Everyone receives security guidance and periodic refreshers | Attendance list with dates | [ ] | | | |
| P4 | Access is revoked when people leave or change roles | Completed offboarding checklists | [ ] | | | |
| P5 | There are agreements on remote working | Agreements in the policy | [ ] | | | |

## 3. Physical

| # | Control | Typical evidence | Applied | Explanation: why and how | Our evidence | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| PH1 | Access to offices and rooms with equipment is restricted | Key policy, or: no own server room | [ ] | [Is everything in the cloud? Say so, and refer to your hosting provider's reports] | | |
| PH2 | Devices outside the office are protected against loss and theft | Disk encryption, screen lock | [ ] | | | |
| PH3 | Equipment is securely wiped or destroyed before disposal | Record of disposed devices | [ ] | | | |

## 4. Technological

| # | Control | Typical evidence | Applied | Explanation: why and how | Our evidence | Owner |
| --- | --- | --- | --- | --- | --- | --- |
| T1 | Multi-factor authentication for email, source code, cloud and administration | Screenshot of the setting | [ ] | | | |
| T2 | Laptops and phones are encrypted, updated and protected | Report from management tool or periodic check | [ ] | | | |
| T3 | Vulnerabilities and updates are handled in time | Agreed timelines, scan report | [ ] | | | |
| T4 | Data is encrypted in transit and at rest | Configuration, hosting provider documentation | [ ] | | | |
| T5 | There are backups, and restoring is tested | Backup setting, restore test report | [ ] | | | |
| T6 | Important events are logged and reviewed | Logging configuration, example alert | [ ] | | | |
| T7 | Code is reviewed before it goes to production | Setting in the code repository | [ ] | | | |
| T8 | Development, test and production environments are separated | Architecture overview | [ ] | | | |
| T9 | Changes to production follow a fixed route | Pipeline configuration, change log | [ ] | | | |
| T10 | Passwords, keys and tokens are kept in a vault, not in code | Use of secrets management, secret scanning | [ ] | | | |
| T11 | The network and cloud environment are shielded | Firewall or security group settings | [ ] | | | |
| T12 | The service is security-tested periodically | Penetration test or scan report with date | [ ] | | | |

## 5. Open items

| # | Control | What is missing | Action | Owner | Planned for |
| --- | --- | --- | --- | --- | --- |
| [1] | [T1] | [Multi-factor authentication not yet on the cloud console] | [Enforce for all administrators] | [Name] | [yyyy-mm-dd] |

---

## What a reviewer looks for

- **Honesty.** An overview with only "Yes" is not credible. A few open items with an owner and a date build more trust.
- **Evidence for every Yes.** Reviewers often pick two or three and ask for the evidence.
- **Consistency.** What is written here must match your policy and your questionnaire answers.

## Version history

| Version | Date | Change | Approved by |
| --- | --- | --- | --- |
| [1.0] | [yyyy-mm-dd] | First version | [Name] |
