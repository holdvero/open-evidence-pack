# Open Evidence Pack-formaat, versie 0.2

*English: [specification.md](specification.md)*

Een open, praktisch formaat om antwoorden op vragenlijsten gekoppeld te houden aan het bewijs erachter. Deze pagina beschrijft elk veld. Het JSON-schema is [evidence-pack.schema.json](evidence-pack.schema.json).

Het formaat heeft één datamodel en twee manieren om het op te schrijven:

- **Excel** (de hoofdmanier): het werkboek in `excel/`, in het Nederlands of het Engels.
- **YAML of JSON**: voor wie zijn antwoorden in Git bijhoudt of met tools wil verwerken.

`tools/validate.py` leest alle drie en controleert ze met dezelfde regels.

## Opbouw

Een pack heeft drie delen:

| Deel | Excel-tabblad (NL / EN) | Sleutel in YAML / JSON |
| --- | --- | --- |
| Antwoorden | Antwoorden / Answers | `answers` |
| Bewijsregister | Bewijsregister / Evidence register | `evidence` |
| Open punten | Open punten / Open items | `open_items` |

Daarnaast een paar gegevens over het pack zelf:

| Veld | Excel | Verplicht | Betekenis |
| --- | --- | --- | --- |
| `format_version` | (vanzelf) | ja | `"0.2"` |
| `organisation.name` | Tabblad Start, Organisatie | ja | Je organisatie |
| `organisation.website` | Tabblad Start, Website | nee | Je website |
| `as_of` | Tabblad Start, Peildatum | nee | Datum waarop het pack betrekking heeft |
| `default_language` | (volgt uit de taal van het werkboek) | nee | Taalcode, zoals `nl` of `en` |

## Antwoorden

| Veld | Excel-kolom (NL / EN) | Verplicht | Betekenis | Waarden |
| --- | --- | --- | --- | --- |
| `question_id` | Vraag-ID / Question ID | ja | Je eigen vaste code voor de vraag, bijv. Q-014. Letters, cijfers, . _ - |  |
| `category` | Categorie / Category | nee | Vrije indeling, bijv. Toegang, Privacy, AI. |  |
| `question` | Vraag / Question | ja | De vraag in algemene vorm. Klanten formuleren het anders; houd de kern. |  |
| `short_answer` | Kort antwoord / Short answer | ja | Ja, nee, deels, beschreven (voor open vragen zoals Wie...? of Hoe vaak...?) of n.v.t. | `yes`, `no`, `partly`, `described`, `not_applicable` |
| `approved_answer` | Goedgekeurd antwoord / Approved answer | ja | Het antwoord zoals je het zou versturen. Begin met het korte antwoord, daarna één of twee zinnen. |  |
| `answer_status` | Status antwoord / Answer status | ja | Hoe goed het antwoord met bewijs onderbouwd is. Zie het tabblad Start. | `evidenced`, `partial`, `open_item`, `explained_no`, `not_applicable` |
| `answer_owner` | Eigenaar antwoord / Answer owner | ja | Wie dit antwoord juist houdt. Een rol mag. |  |
| `last_reviewed` | Laatst herzien / Last reviewed | ja | Wanneer iemand voor het laatst controleerde of het antwoord nog klopt. | `jjjj-mm-dd` |
| `next_review` | Volgende herziening / Next review | ja | Wanneer het opnieuw gecontroleerd moet worden. Wordt rood als de datum voorbij is. | `jjjj-mm-dd` |
| `evidence` | Bewijs / Evidence | nee | Bewijs-ID's uit het Bewijsregister, gescheiden door ; met eventueel een vindplaats na het ID. Voorbeeld: BEL-01 §3; SCR-01 | lijst |
| `open_item_ids` | Open punten / Open item IDs | nee | ID's uit het tabblad Open punten, gescheiden door ;. Verplicht bij deels onderbouwd en open punt. | lijst |
| `framework_refs` | Kaderverwijzingen / Framework refs | nee | Alleen nummers, gescheiden door ;. Voorbeeld: ISO/IEC 27001:2022 A.8.5. Nooit tekst uit betaalde normen overnemen. | lijst |
| `notes` | Notities / Notes | nee | Interne notities. |  |

## Bewijsregister

| Veld | Excel-kolom (NL / EN) | Verplicht | Betekenis | Waarden |
| --- | --- | --- | --- | --- |
| `evidence_id` | Bewijs-ID / Evidence ID | ja | Je eigen vaste code, bijv. BEL-01 of EVD-003. |  |
| `title` | Titel / Title | ja | Naam van het document, de registratie, instelling of het resultaat. |  |
| `evidence_type` | Soort bewijs / Evidence type | ja | Wat voor bewijs dit is. Kies uit de lijst. | `policy`, `procedure`, `record`, `documentation`, `configuration`, `system_generated`, `screenshot`, `test_result`, `audit_report`, `certificate`, `contract`, `other` |
| `version` | Versie / Version | ja | Versieaanduiding, bijv. 2.1, Q3 2026 of een datum. |  |
| `version_date` | Versiedatum / Version date | ja | Datum waarop deze versie is vastgesteld, uitgegeven, geëxporteerd of vastgelegd. | `jjjj-mm-dd` |
| `owner` | Eigenaar / Owner | ja | Wie dit bewijs actueel houdt. |  |
| `review_due` | Herzien voor / Review due | nee | Wanneer het herzien of vernieuwd moet worden. De meeste documenten verlopen niet; ze moeten herzien worden. Wordt rood als de datum voorbij is. | `jjjj-mm-dd` |
| `locator` | Vindplaats / Locator | nee | Standaardvindplaats in het bewijs (paragraaf, pagina, instelling). Antwoorden kunnen een preciezere geven. |  |
| `shareable` | Deelbaar / Shareable | nee | Of je het met klanten mag delen, en hoe. | `public`, `on_request`, `under_nda`, `internal_only` |
| `status` | Status / Status | ja | Actueel, concept, vervangen of ingetrokken. Antwoorden horen op actueel bewijs te steunen. | `current`, `draft`, `superseded`, `withdrawn` |
| `storage_reference` | Opslaglocatie / Storage reference | nee | Waar het bewijs staat, als interne verwijzing. Zet nooit vertrouwelijke documenten in dit bestand. |  |
| `hash_algorithm` | Hash-algoritme / Hash algorithm | nee | sha256, sha384 of sha512. Verplicht als je een hash invult. | `sha256`, `sha384`, `sha512` |
| `hash` | Hash / Hash | nee | Vingerafdruk van het bestand. Met een opgeslagen hash kun je later controleren of een bestand precies gelijk is aan de geregistreerde versie. Een hash laat niet zien dat een maatregel werkt. |  |
| `notes` | Notities / Notes | nee | Interne notities. |  |

## Open punten

| Veld | Excel-kolom (NL / EN) | Verplicht | Betekenis | Waarden |
| --- | --- | --- | --- | --- |
| `open_item_id` | Open-punt-ID / Open item ID | ja | Je eigen vaste code, bijv. OI-01. |  |
| `description` | Omschrijving / Description | ja | Wat ontbreekt en wat je gaat doen. |  |
| `related_question_ids` | Betreft vragen / Related question IDs | ja | Vraag-ID's uit het tabblad Antwoorden, gescheiden door ;. | lijst |
| `owner` | Eigenaar / Owner | ja | Wie het doet. |  |
| `target_date` | Streefdatum / Target date | ja | Wanneer het af moet zijn. Wordt rood als de datum voorbij is en het punt niet is afgerond. | `jjjj-mm-dd` |
| `status` | Status / Status | ja | Open, bezig of afgerond. | `open`, `in_progress`, `closed` |
| `resolution_note` | Afhandeling / Resolution note | nee | Hoe het is opgelost. Verplicht bij afgerond. |  |

## Regels

**Korte antwoorden.** Ja, nee en deels voor gesloten vragen. Beschreven (`described`) voor open vragen zoals *Wie is verantwoordelijk…?* of *Hoe vaak…?*, waar het antwoord een beschrijving is. N.v.t. als de vraag niet van toepassing is.

**Statussen van antwoorden.**

| Werkboek | `answer_status` | Gebruik als | Regels |
| --- | --- | --- | --- |
| onderbouwd | `evidenced` | Het antwoord klopt en je kunt het laten zien | Minstens één bewijsverwijzing. Het korte antwoord mag ja, nee of deels zijn: op *Kan jullie AI zonder goedkeuring een terugbetaling doen?* is het onderbouwde antwoord nee |
| deels onderbouwd | `partial` | Grotendeels geregeld en onderbouwd; een kleiner restant is gepland | Kort antwoord is deels; minstens één open punt |
| open punt | `open_item` | Het belangrijkste deel van de vraag is nog niet geregeld, met een plan | Minstens één open punt |
| nee met uitleg | `explained_no` | Het eerlijke antwoord is nee en dat is een tekortkoming; je legt uit waarom of wat je in plaats daarvan doet | Kort antwoord is nee |
| n.v.t. | `not_applicable` | De vraag is niet op jou van toepassing | Kort antwoord is n.v.t., en andersom |

Statussen zeggen hoe goed een antwoord met bewijs onderbouwd is. Ze zijn geen certificering.

**Verwijzingen.** Elke bewijsverwijzing in een antwoord moet in het bewijsregister staan. Elk open punt waar een antwoord naar verwijst moet bestaan, en elke vraag waar een open punt naar verwijst ook. ID's zijn uniek binnen hun deel.

**Datums.** Alle datums schrijf je als `jjjj-mm-dd`. De volgende herziening mag niet vóór de laatste herziening liggen. De controle waarschuwt als een herzienings- of streefdatum voorbij is.

**Open punten.** Een afgerond open punt heeft een afhandeling nodig. Zijn alle open punten van een antwoord met *deels onderbouwd* of *open punt* afgerond, dan herinnert de controle je eraan het antwoord bij te werken.

**Hashes.** Een hash heeft een hash-algoritme nodig en moet de juiste lengte hebben: 64 tekens voor sha256, 96 voor sha384, 128 voor sha512. Een hash wijst precies één versie van een bestand aan. Hij bewijst niet dat een maatregel werkt.

## Verwijzingen en lijsten in Excel

- **Bewijs**: bewijs-ID's gescheiden door `;`. Na een ID mag je met een spatie aangeven waar in het bewijs de onderbouwing staat: `BEL-01 §3; PRO-04 §2; SCR-01`. In YAML/JSON wordt dat een lijst van `{evidence_id, locator}`.
- **Open punten, Betreft vragen**: gescheiden door `;` (een komma werkt ook).
- **Kaderverwijzingen**: gescheiden door `;`. Alleen nummers, zoals `ISO/IEC 27001:2022 A.8.5`. Neem nooit tekst uit betaalde normen over.

## Waarden in het Nederlandse werkboek

Het Nederlandse werkboek toont Nederlandse keuzewaarden. De controle zet ze om naar de vaste waarden van YAML/JSON:

| Veld | Nederlands werkboek | Vaste waarde |
| --- | --- | --- |
| `short_answer` | ja, nee, deels, beschreven, n.v.t. | `yes`, `no`, `partly`, `described`, `not_applicable` |
| `answer_status` | onderbouwd, deels onderbouwd, open punt, nee met uitleg, n.v.t. | `evidenced`, `partial`, `open_item`, `explained_no`, `not_applicable` |
| `evidence_type` | beleid, procedure, registratie, documentatie, configuratie, systeemexport, schermafdruk, testresultaat, auditrapport, certificaat, contract, overig | `policy`, `procedure`, `record`, `documentation`, `configuration`, `system_generated`, `screenshot`, `test_result`, `audit_report`, `certificate`, `contract`, `other` |
| `shareable` | openbaar, op aanvraag, onder NDA, alleen intern | `public`, `on_request`, `under_nda`, `internal_only` |
| `status (evidence)` | actueel, concept, vervangen, ingetrokken | `current`, `draft`, `superseded`, `withdrawn` |
| `status (open items)` | open, bezig, afgerond | `open`, `in_progress`, `closed` |

## Eigen velden

Eigen kolommen die je aan het werkboek toevoegt, blijven bewaard als `x_`-veld (een kolom *Klant* wordt `x_klant`). In YAML of JSON laat je eigen veldnamen beginnen met `x_`. Tools moeten die velden bewaren en mogen ze negeren.

## Versies

Dit is versie 0.2. Velden kunnen nog veranderen voor versie 1.0. Elk YAML/JSON-bestand vermeldt zijn `format_version`. Wijzigingen staan in [CHANGELOG.md](../CHANGELOG.md).

## Verhouding tot andere formaten

Het formaat is bewust klein. Het vervangt geen formele, machineleesbare formaten voor maatregelen en audits zoals NIST OSCAL. Een koppeling of export naar zulke formaten, waar dat nuttig is, is een ontwerpdoel voor latere versies, geen bestaande functie.

## Licentie

Deze beschrijving valt onder CC BY 4.0. Het schema en de tools vallen onder MIT.
