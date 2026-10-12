# Open Evidence Pack

*English: [README.md](README.md)*

**Een open, praktisch formaat om antwoorden op vragenlijsten gekoppeld te houden aan het bewijs erachter.**

Voor B2B SaaS- en IT-leveranciers die security-, privacy-, NIS2- en AI-vragenlijsten van hun klanten beantwoorden. De meeste vragenlijsten stellen dezelfde vragen. Met dit pakket houd je één set goedgekeurde antwoorden bij, elk gekoppeld aan het bewijs dat het onderbouwt, met een eigenaar, een herzieningsdatum en eerlijke open punten.

Gemaakt door [Holdvero](https://holdvero.com). *Bewijs wat je claimt.*

## Begin hier (zonder programmeren)

1. Download het werkboek: [Nederlands](excel/open-evidence-pack-nl.xlsx) of [Engels](excel/open-evidence-pack-en.xlsx).
2. Open het fictieve voorbeeld om het ingevuld te zien: [voorbeeld-evidence-pack-nl.xlsx](examples/voorbeeld-evidence-pack-nl.xlsx).
3. Vul je eigen bewijs, antwoorden en open punten in. Het tabblad **Start** legt elke stap uit.

Het werkboek heeft drie werktabbladen:

| Tabblad | Wat erin komt |
| --- | --- |
| **Antwoorden** | De vragen die steeds terugkomen, het antwoord dat je hebt goedgekeurd, de status, eigenaar, herzieningsdatums en het bewijs erachter. |
| **Bewijsregister** | Elk document, elke registratie, instelling of resultaat dat je kunt laten zien: soort, versie, eigenaar, herzieningsdatum, waar het staat en of je het mag delen. |
| **Open punten** | Wat nog niet geregeld is, wie het oplost en wanneer. |

Keuzelijsten houden de waarden gelijk. Datums die voorbij zijn kleuren rood, zodat je ziet wat aandacht nodig heeft.

## Wat erin zit

| Map | Wat | Licentie |
| --- | --- | --- |
| `excel/` | Het lege werkboek, in het Nederlands en het Engels | CC BY 4.0 |
| `examples/` | Een fictief, ingevuld voorbeeld als Excel, YAML en JSON, in het Nederlands en het Engels | CC BY 4.0 |
| `templates/` | Vijf documentsjablonen in het Nederlands en het Engels | CC BY 4.0 |
| `format/` | De beschrijving van het formaat, en een JSON-schema | Beschrijving CC BY 4.0, schema MIT |
| `tools/` | Een klein script dat een werkboek of bestand controleert | MIT |

### De vijf sjablonen

Vijf documenten waar zakelijke klanten in vragenlijsten vaak om vragen. Elk sjabloon eindigt met **"Waar een beoordelaar op let"**.

1. [Informatiebeveiligingsbeleid](templates/nl/01-informatiebeveiligingsbeleid.md)
2. [Incidentprocedure](templates/nl/02-incidentprocedure.md)
3. [Lijst van subverwerkers](templates/nl/03-subverwerkers.md)
4. [Offboarding-checklist](templates/nl/04-offboarding-checklist.md)
5. [Overzicht maatregelen](templates/nl/05-overzicht-maatregelen.md)

## Zo werkt het

1. **Registreer je bewijs.** Geef elk document, elke registratie, instelling of resultaat een code, zoals `BEL-01` of `EVD-003`.
2. **Schrijf goedgekeurde antwoorden.** Begin met ja, nee of deels (of, bij een open vraag, meteen de beschrijving), daarna één of twee zinnen. Koppel de bewijscodes, met een paragraaf als dat helpt: `BEL-01 §3; SCR-01`.
3. **Wees eerlijk over gaten.** Ontbreekt het bewijs, schrijf dan geen ja. Gebruik de status *deels onderbouwd* of *open punt* en maak een open punt met een eigenaar en een streefdatum.
4. **Herzie.** Elk antwoord heeft een volgende herzieningsdatum, elk bewijsstuk een datum waarvoor het herzien moet worden. Rood betekent: aandacht nodig.
5. **Hergebruik.** Komt de volgende vragenlijst, dan begin je bij je goedgekeurde antwoorden in plaats van bij een lege spreadsheet. Controleer wel of ze nog kloppen voordat je ze verstuurt.

### Statussen van antwoorden

| In het werkboek | In YAML/JSON | Betekenis |
| --- | --- | --- |
| onderbouwd | `evidenced` | Klopt en is onderbouwd met bewijs uit het register. Het korte antwoord mag ja, nee of deels zijn. |
| deels onderbouwd | `partial` | Grotendeels geregeld en onderbouwd. Een kleiner restant is een open punt. |
| open punt | `open_item` | Het belangrijkste deel van de vraag is nog niet geregeld. Er is een open punt met een plan. |
| nee met uitleg | `explained_no` | Eerlijk nee (een tekortkoming), met uitleg wat je in plaats daarvan doet. |
| n.v.t. | `not_applicable` | De vraag is niet op jou van toepassing, met de reden. |

Statussen zeggen hoe goed een antwoord met bewijs onderbouwd is. **Ze zijn geen certificering.**

## Wat het is, en wat het niet is

**Het is** een licht, praktisch formaat voor vragenlijsten aan leveranciers: eerst Excel, met YAML en JSON voor wie dat wil. Het is bedoeld voor de persoon die de vragenlijsten echt invult.

**Het is niet:**

- een industriestandaard of een certificering;
- juridisch advies, of bewijs dat je voldoet aan ISO/IEC 27001, NIS2, de AVG of een ander kader;
- een tool die vragenlijsten voor je invult;
- een plek om vertrouwelijke documenten te bewaren. Het register verwijst naar waar het bewijs staat; het bewijs zelf blijft in je eigen systemen.

## Waarom niet OSCAL?

[OSCAL](https://pages.nist.gov/OSCAL/), ontwikkeld door NIST, is een set machineleesbare formaten voor catalogi van maatregelen, baselines, beveiligingsplannen, auditplannen en -resultaten, en actieplannen. Het is de juiste keuze voor formele audits en voor organisaties die op grote schaal maatregelen beheren.

Het Open Evidence Pack heeft een kleinere taak: een leverancier helpen zijn antwoorden op vragenlijsten gekoppeld te houden aan zijn bewijs, in een spreadsheet die ook een niet-specialist kan bijhouden. Het zijn geen concurrenten. Een koppeling of export naar OSCAL, waar dat nuttig is, is een ontwerpdoel voor latere versies; het pakket doet dat nu nog niet.

## Security en privacy

- Zet geen vertrouwelijke documenten, klantgegevens of inhoud van vragenlijsten die je onder NDA kreeg in het pakket.
- Gebruik in *Opslaglocatie* een interne verwijzing, nooit een openbare link naar een vertrouwelijk bestand.
- Geef in *Deelbaar* aan wat je met klanten mag delen: openbaar, op aanvraag, onder NDA of alleen intern.
- Een **hash** is een vingerafdruk van een bestand. Met een opgeslagen hash kun je later controleren of een bestand precies gelijk is aan de geregistreerde versie. **Een hash laat niet zien dat een maatregel werkt.**
- Jij blijft verantwoordelijk voor elk antwoord dat je goedkeurt en naar een klant stuurt.

## Uitbreiden

Voeg gerust eigen kolommen toe aan het werkboek, bijvoorbeeld *Klant* of *Product*. Die blijven bewaard als extra veld (`x_klant`) en geven geen fout bij de controle. In YAML of JSON laat je eigen veldnamen beginnen met `x_`.

## Een werkboek of bestand controleren (optioneel)

Voor technische gebruikers. De controle werkt op het Excel-werkboek (Nederlands of Engels), YAML en JSON.

```bash
pip install jsonschema pyyaml openpyxl
python tools/validate.py excel/mijn-evidence-pack.xlsx
```

Je krijgt fouten (ontbrekende of verkeerde waarden, bewijscodes die niet bestaan, dubbele ID's) en waarschuwingen (herzienings- en streefdatums die voorbij zijn). Met `--to-json uit.json` zet je een werkboek om naar JSON. Alle velden staan in [format/specificatie.md](format/specificatie.md).

## Licentie

De werkboeken, voorbeelden, sjablonen en documentatie vallen onder **CC BY 4.0**, met een extra toestemming: ingevulde exemplaren die je intern gebruikt of met klanten, auditors of adviseurs deelt, hebben geen naamsvermelding nodig. Zie [LICENSE-CONTENT.md](LICENSE-CONTENT.md). Het JSON-schema en de tools vallen onder **MIT** (zie [LICENSE](LICENSE)). GitHub toont "MIT" bij deze repository vanwege het bestand `LICENSE`; die licentie geldt alleen voor het schema en de code.

## Versies

Dit is versie 0.2 van het formaat. Velden kunnen nog veranderen voor versie 1.0. Zie [CHANGELOG.md](CHANGELOG.md). Suggesties zijn welkom als issue.

## Disclaimer

De sjablonen en het werkboek zijn een begin, geen juridisch advies en geen certificering. Jij blijft verantwoordelijk voor wat je opschrijft en naar je klanten stuurt. Alles in `examples/` gaat over een fictief bedrijf.

## Bijdragen

Suggesties zijn welkom. Open een issue met wat je zou veranderen en waarom. Zet er nooit vertrouwelijke informatie of klantinformatie in. Zie [CONTRIBUTING.md](CONTRIBUTING.md).

## Over Holdvero

Holdvero helpt SaaS- en IT-leveranciers in Nederland en België om security-, privacy-, NIS2- en AI-vragenlijsten van hun klanten met bewijs te beantwoorden, en dat bewijs actueel te houden. Heb je nu een vragenlijst liggen, of krijg je steeds dezelfde vragen? Kijk op [holdvero.com](https://holdvero.com).
