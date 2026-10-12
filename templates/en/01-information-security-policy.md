# Information security policy

> **Template from the [Open Evidence Pack](https://github.com/holdvero/open-evidence-pack)**, CC BY 4.0, made by [Holdvero](https://holdvero.com).
>
> **Last reviewed by Holdvero: 2026-10-11.** This template is a starting point, not legal advice. Verify the legal, contractual and regulatory requirements that apply to you before you adopt it.
>
> **How to use this template** (delete this block when you are done)
> 1. Replace everything in `[square brackets]`.
> 2. Delete every sentence you do not actually do. A policy that promises something you do not do is worse than no policy: a customer or auditor will ask for evidence.
> 3. Keep it short. This document says *what* you want to achieve and *who* is responsible. The *how* belongs in procedures (such as the incident procedure and the offboarding checklist).
> 4. Have it approved by management and fill in the version table at the bottom.

| | |
| --- | --- |
| Organisation | [Company name Ltd] |
| Document owner | [Name, role] |
| Approved by | [Name, role of management member] |
| Version | [1.0] |
| Date approved | [yyyy-mm-dd] |
| Next review | [yyyy-mm-dd, no later than 12 months after approval] |
| Classification | [Internal / May be shared with customers] |

## 1. Purpose

[Company name] provides [short description of the service, for example: a SaaS platform for scheduling in healthcare]. Our customers trust us with their data. This policy describes how we protect that data and our own systems, so that they stay:

- **confidential**: only people who need it can access it;
- **accurate**: data is not changed without notice or authorisation;
- **available**: our service works when customers need it.

## 2. Scope

This policy applies to:

- all employees, interns and freelancers working for [Company name];
- all systems, laptops, phones and cloud services we use to develop, deliver and support [the service];
- all data of customers and of [Company name] itself, wherever it is stored.

[Optional: Out of scope is ... , because ... ]

## 3. Principles

1. **Risks drive what we do.** At least once a year we assess what can go wrong, how serious it would be and what we do about it. Major changes (a new supplier, a new product) are a reason to look again.
2. **Least access.** Everyone gets only the access they need for their work. Access to production and customer data is limited to [roles or names] and reviewed [every quarter / every six months].
3. **Strong sign-in.** Multi-factor authentication is required for [email, source code, cloud environment and administrative access]. [Delete or adjust if this is not yet in place everywhere, and list it as an open item in your controls overview.]
4. **Protecting data.** Customer data is encrypted in transit and [stored encrypted at our hosting provider]. Customer data is stored [in the EU / in the following regions: ...].
5. **Devices in order.** Laptops have disk encryption, a screen lock and automatic updates. [How you check this, for example through a management tool or a periodic check.]
6. **Suppliers are chosen with care.** Before a supplier may process customer data, we look at its security and, where needed, sign a data processing agreement. The current list is in our sub-processor list.
7. **Secure development.** Code changes are reviewed [by a second person] before they go to production. Secrets (passwords, keys) are not stored in source code.
8. **Backups and recovery.** We back up [production data] [daily] and test at least [once a year] that we can restore it.
9. **Report incidents and learn.** Everyone reports a (suspected) security incident immediately to [name or channel]. We follow the incident procedure and inform customers as agreed.
10. **People are the first line of defence.** New staff are introduced to this policy when they start. Everyone gets a short refresher at least once a year.
11. **Access ends when people leave.** When someone leaves, we revoke all access following the offboarding checklist.

## 4. Roles and responsibilities

| Role | Who | Responsible for |
| --- | --- | --- |
| Management | [Name] | Approves this policy, provides resources, decides on risks we accept |
| Information security lead | [Name] | Keeps this policy and the controls current, coordinates incidents, point of contact for customers |
| Privacy contact [or data protection officer, if you are required to have one] | [Name] | Questions about personal data, data breaches, data processing agreements |
| All staff | Everyone | Follow this policy, report incidents and doubts |

In a small team one person may hold several roles. Do write down who does what.

## 5. Exceptions

Anyone who needs to deviate from this policy asks [the information security lead]. An exception is recorded with the reason, the risks, who approved it and until when it applies.

## 6. Compliance and review

- We review this policy at least once a year, and earlier after major changes to our service, our organisation or the laws that apply to us.
- Deliberate violations of this policy may be addressed under [the employment contract / the staff handbook / the service agreement].

## 7. Related documents

- Incident procedure: [link or location]
- Sub-processor list: [link or location]
- Offboarding checklist: [link or location]
- Controls overview: [link or location]
- [Other procedures, for example backup, access management, change management]

---

## What a reviewer looks for

- **Is it approved?** A name of a management member and a date. Without that, it is a draft.
- **Is it current?** A review date that has not passed.
- **Does it match practice?** Reviewers often pick one promise, such as multi-factor authentication or backup tests, and ask for evidence. Make sure you can show it.
- **Are there names or roles?** "Everyone is responsible" does not answer who is responsible.

## Version history

| Version | Date | Change | Approved by |
| --- | --- | --- | --- |
| [1.0] | [yyyy-mm-dd] | First version | [Name] |
