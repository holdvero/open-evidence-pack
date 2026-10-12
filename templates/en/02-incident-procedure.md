# Incident procedure

> **Template from the [Open Evidence Pack](https://github.com/holdvero/open-evidence-pack)**, CC BY 4.0, made by [Holdvero](https://holdvero.com).
>
> **Last reviewed by Holdvero: 2026-10-11.** This template is a starting point, not legal advice. Verify the legal, contractual and regulatory requirements that apply to you before you adopt it.
>
> **How to use this template** (delete this block when you are done)
> 1. Replace everything in `[square brackets]`.
> 2. Take the deadline for informing customers from your **data processing agreements and contracts**. Never promise anything here that differs from what they say.
> 3. Does NIS2 apply to your organisation? Then keep section 6 and fill in the right authority. If not, delete that section.
> 4. Practise the procedure at least once a year with a short scenario, and record that you did.

| | |
| --- | --- |
| Organisation | [Company name Ltd] |
| Document owner | [Name, role] |
| Version | [1.0] |
| Date approved | [yyyy-mm-dd] |
| Next review | [yyyy-mm-dd] |

## 1. What is an incident?

A **security incident** is any event that puts, or may put, the confidentiality, accuracy or availability of our service or of data at risk. Examples:

- a laptop or phone with access to company data is lost or stolen;
- someone has (possibly) entered a password on a phishing page;
- customer data was sent to the wrong person;
- our service is unavailable for more than [x minutes];
- a supplier reports an incident that may affect our data;
- unusual activity in logs, for example sign-ins from an unknown country.

A **personal data breach** is an incident in which personal data is lost, or reaches or may reach unauthorised people. Data breaches are subject to legal rules (section 5).

**In doubt? Report it.** Ten reports that turn out to be nothing are better than one that comes too late.

## 2. Reporting

Anyone who notices a (possible) incident reports it **immediately** to:

| Channel | Details |
| --- | --- |
| First contact | [Name], [phone number] |
| Backup | [Name], [phone number] |
| Reporting address | [security@company.com] |

Customers and third parties can report an incident or vulnerability via [security@company.com / link to reporting page].

What to report: what you saw, when, on which system, and what you have already done. Do not change anything on the system unless needed to limit damage; that way, traces are preserved.

## 3. Roles

| Role | Who | Task |
| --- | --- | --- |
| Incident coordinator | [Name], backup [Name] | Leads the response, decides on severity and next steps, keeps the log |
| Technical | [Name] | Investigates, limits damage, restores |
| Customer communication | [Name] | Informs customers according to section 5 |
| Management | [Name] | Decides on serious incidents, notifies authorities where needed |

## 4. Steps

1. **Record.** The coordinator opens an incident log ([location, for example a ticket or shared document]) with the time of the report, what is known and who is involved. Everything that happens afterwards goes into that log with a timestamp.
2. **Assess.** Determine the severity:

   | Severity | When | Examples |
   | --- | --- | --- |
   | High | Customer data possibly leaked or affected, or the service is down for many customers | Intrusion into production, breach of customer data |
   | Medium | Risk to our own systems, limited impact on customers | Stolen laptop with encrypted disk, short outage |
   | Low | No impact on customers or data | Blocked phishing email, failed sign-in attempts |

3. **Contain.** Stop the damage: disable accounts, change passwords and keys, isolate systems, engage a supplier.
4. **Investigate.** What happened, since when, which data and which customers are affected?
5. **Inform.** Decide who needs to be informed: customers (section 5), the regulator (sections 5 and 6), the police in case of a crime, the insurer.
6. **Recover.** Bring the service and data back to a trustworthy state, for example from a backup.
7. **Close and learn.** For medium or high severity, the coordinator writes a short review within [10 working days]: cause, impact, what went well, what we improve, who does that and when.

## 5. Personal data breaches and informing customers

For most customer data we are the **processor** and the customer is the **controller**. This means:

- **We inform the customer** without undue delay after we become aware of a breach, and no later than **[deadline from the data processing agreement, for example 24 or 48 hours]**. We send what we know at that moment and add to it as we learn more.
- **The customer decides** whether the breach must be notified to the regulator and to the people affected. Unless the breach is unlikely to result in a risk to people, the customer must notify the regulator where feasible within 72 hours of becoming aware of it. That is why we must be fast.
- Where possible, our notice to the customer includes: what happened, when, which types of data and roughly how many people, the likely consequences, what we have already done, and a contact person.

For data where **we are the controller** ourselves (for example data about our staff or our own business contacts), we assess whether we must notify the data protection authority (Netherlands: Autoriteit Persoonsgegevens; Belgium: Data Protection Authority) within 72 hours of becoming aware.

**Every breach** is recorded in our breach register ([location]), even if it does not need to be notified.

## 6. NIS2 (only if it applies to us)

[Delete this section if your organisation is not in scope of NIS2. Not sure? Find out whether you are an essential or important entity under the law in your country.]

For a **significant incident** we notify [the CSIRT or competent authority, for example the CCB in Belgium]:

| When | What |
| --- | --- |
| Within 24 hours of becoming aware | Early warning |
| Within 72 hours of becoming aware | Incident notification with an initial assessment |
| Within 1 month of the incident notification | Final report |

Check the exact rules and the reporting point in the law of your country.

## 7. Contact details

| Party | Contact |
| --- | --- |
| Hosting provider | [Name, support channel, contract number] |
| [Other critical supplier] | [Contact] |
| Insurer (cyber insurance) | [Contact, policy number] |
| Legal adviser | [Contact] |
| Data protection authority | [Autoriteit Persoonsgegevens / Data Protection Authority] |

## 8. Practice and review

- We practise this procedure at least once a year with a short scenario and record when and with whom.
- We review this procedure after every high-severity incident, and at least once a year.

## Official sources

Check the deadlines and reporting duties in the official texts. They can change, and for NIS2 the transposition law of your country applies.

- GDPR (Regulation (EU) 2016/679), articles 33 and 34: [EUR-Lex](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- NIS2 Directive (Directive (EU) 2022/2555), article 23: [EUR-Lex](https://eur-lex.europa.eu/eli/dir/2022/2555/oj)
- Autoriteit Persoonsgegevens (Netherlands): [autoriteitpersoonsgegevens.nl](https://autoriteitpersoonsgegevens.nl)
- Data Protection Authority (Belgium): [dataprotectionauthority.be](https://www.dataprotectionauthority.be)
- Centre for Cybersecurity Belgium (CCB): [ccb.belgium.be](https://ccb.belgium.be)

---

## What a reviewer looks for

- **A concrete deadline for customers** that matches the data processing agreement.
- **Names and a backup**, so the procedure works when someone is on holiday.
- **An incident and breach register**, even if it is empty: then you can say "zero incidents in [period]" and show the register.
- **Evidence of an exercise**, for example a short report with a date.

## Version history

| Version | Date | Change | Approved by |
| --- | --- | --- | --- |
| [1.0] | [yyyy-mm-dd] | First version | [Name] |
