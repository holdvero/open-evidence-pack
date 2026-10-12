# Overzicht maatregelen

> **Sjabloon uit het [Open Evidence Pack](https://github.com/holdvero/open-evidence-pack)**, CC BY 4.0, gemaakt door [Holdvero](https://holdvero.com).
>
> **Laatst herzien door Holdvero: 2026-10-11.** Dit sjabloon is een begin, geen juridisch advies. Controleer welke wettelijke, contractuele en toezichtseisen voor jou gelden voordat je het gebruikt.
>
> **Zo gebruik je dit sjabloon** (verwijder dit blok als je klaar bent)
> 1. Vul per maatregel in of je hem toepast: **Ja**, **Deels** of **Nee**.
> 2. Schrijf kort waarom, en hoe je het doet. Bij **Nee** of **Deels**: waarom niet, en of je het van plan bent.
> 3. Verwijs bij elke **Ja** naar bewijs: een document, een instelling, een registratie. Zonder bewijs is het een **Deels**. Gebruik je het werkboek van het Open Evidence Pack? Zet dan de bewijscodes uit je bewijsregister in de kolom *Bewijs bij ons*.
> 4. Zet alles wat **Deels** of **Nee** is en wel zou moeten, in de lijst met open punten onderaan, met een eigenaar en een datum.
>
> **Over ISO/IEC 27001.** Dit overzicht is een lichte opstap, ingedeeld in dezelfde vier thema's als ISO/IEC 27002:2022 (organisatorisch, mensen, fysiek, technologisch). Het is geen volledige *Verklaring van toepasselijkheid*: daarvoor moet je alle maatregelen uit bijlage A van ISO/IEC 27001 beoordelen. Wie later wil certificeren, kan dit overzicht als begin gebruiken.

| | |
| --- | --- |
| Organisatie | [Bedrijfsnaam B.V.] |
| Reikwijdte | [Bijvoorbeeld: het platform [naam], de organisatie die het ontwikkelt en ondersteunt] |
| Eigenaar van dit document | [Naam, functie] |
| Versie | [1.0] |
| Datum | [jjjj-mm-dd] |
| Volgende herziening | [jjjj-mm-dd] |

**Legenda Toegepast:** Ja · Deels · Nee · N.v.t. (niet van toepassing, met reden)

## 1. Organisatorisch

| # | Maatregel | Typisch bewijs | Toegepast | Toelichting: waarom en hoe | Bewijs bij ons | Eigenaar |
| --- | --- | --- | --- | --- | --- | --- |
| O1 | Er is een beveiligingsbeleid, vastgesteld door de directie | Beleid met naam en datum van vaststelling | [ ] | | [Document, versie] | [Naam] |
| O2 | Taken en verantwoordelijkheden voor beveiliging zijn belegd bij personen | Rollentabel in het beleid | [ ] | | | |
| O3 | Er is een overzicht van systemen, apparaten en gegevens | Lijst van systemen en apparaten | [ ] | | | |
| O4 | Gegevens zijn ingedeeld naar hoe gevoelig ze zijn, met regels per niveau | Indeling in het beleid | [ ] | | | |
| O5 | Toegang wordt alleen gegeven als het nodig is, en periodiek nagekeken | Verslag van de laatste controle | [ ] | | | |
| O6 | Leveranciers worden beoordeeld voor ze gegevens krijgen; afspraken staan op papier | Lijst van subverwerkers, verwerkersovereenkomsten | [ ] | | | |
| O7 | Incidenten worden gemeld, afgehandeld en geëvalueerd | Incidentprocedure, incidentregister | [ ] | | | |
| O8 | Er is een plan voor uitval van kritieke diensten of leveranciers | Continuïteitsplan, laatste test | [ ] | | | |
| O9 | Wettelijke en contractuele eisen (zoals AVG, NIS2, klantcontracten) zijn in kaart | Overzicht van eisen | [ ] | | | |
| O10 | Risico's worden periodiek beoordeeld en behandeld | Risicoanalyse met datum | [ ] | | | |
| O11 | Maatregelen worden periodiek gecontroleerd op werking | Verslag interne controle | [ ] | | | |

## 2. Mensen

| # | Maatregel | Typisch bewijs | Toegepast | Toelichting: waarom en hoe | Bewijs bij ons | Eigenaar |
| --- | --- | --- | --- | --- | --- | --- |
| M1 | Nieuwe mensen worden bij aanname gescreend, passend bij hun rol | Procedure, bijvoorbeeld referentiecheck of VOG | [ ] | | | |
| M2 | Geheimhouding is vastgelegd in contracten | Clausule in arbeids- of opdrachtovereenkomst | [ ] | | | |
| M3 | Iedereen krijgt uitleg en periodieke opfrissing over beveiliging | Deelnamelijst met data | [ ] | | | |
| M4 | Toegang wordt ingetrokken bij vertrek of rolwissel | Ingevulde offboarding-checklists | [ ] | | | |
| M5 | Er zijn afspraken over werken op afstand | Afspraken in het beleid | [ ] | | | |

## 3. Fysiek

| # | Maatregel | Typisch bewijs | Toegepast | Toelichting: waarom en hoe | Bewijs bij ons | Eigenaar |
| --- | --- | --- | --- | --- | --- | --- |
| F1 | Toegang tot kantoor en ruimtes met apparatuur is beperkt | Sleutelbeleid, of: geen eigen serverruimte | [ ] | [Draait alles in de cloud? Schrijf dat, en verwijs naar de rapporten van je hostingpartij] | | |
| F2 | Apparaten buiten kantoor zijn beschermd tegen verlies en diefstal | Schijfversleuteling, schermvergrendeling | [ ] | | | |
| F3 | Apparatuur wordt veilig gewist of vernietigd voor afvoer | Registratie van afgevoerde apparaten | [ ] | | | |

## 4. Technologisch

| # | Maatregel | Typisch bewijs | Toegepast | Toelichting: waarom en hoe | Bewijs bij ons | Eigenaar |
| --- | --- | --- | --- | --- | --- | --- |
| T1 | Meervoudige authenticatie voor e-mail, broncode, cloud en beheer | Schermafdruk van de instelling | [ ] | | | |
| T2 | Laptops en telefoons zijn versleuteld, bijgewerkt en beschermd | Rapport uit beheertool of periodieke check | [ ] | | | |
| T3 | Kwetsbaarheden en updates worden tijdig verwerkt | Afspraak over termijnen, scanrapport | [ ] | | | |
| T4 | Gegevens zijn versleuteld tijdens transport en opslag | Configuratie, documentatie hostingpartij | [ ] | | | |
| T5 | Er zijn back-ups, en herstellen wordt getest | Back-upinstelling, verslag hersteltest | [ ] | | | |
| T6 | Belangrijke gebeurtenissen worden gelogd en bekeken | Logconfiguratie, voorbeeld van een melding | [ ] | | | |
| T7 | Code wordt beoordeeld voor ze naar productie gaat | Instelling in de code-repository | [ ] | | | |
| T8 | Ontwikkel-, test- en productieomgeving zijn gescheiden | Architectuuroverzicht | [ ] | | | |
| T9 | Wijzigingen in productie verlopen via een vaste route | Pipeline-configuratie, wijzigingslog | [ ] | | | |
| T10 | Wachtwoorden, sleutels en tokens staan in een kluis, niet in code | Gebruik van geheimenbeheer, scan op geheimen | [ ] | | | |
| T11 | Het netwerk en de cloudomgeving zijn afgeschermd | Firewall- of security-groupinstellingen | [ ] | | | |
| T12 | De dienst wordt periodiek op beveiliging getest | Pentestrapport of scanrapport met datum | [ ] | | | |

## 5. Open punten

| # | Maatregel | Wat ontbreekt | Actie | Eigenaar | Gepland voor |
| --- | --- | --- | --- | --- | --- |
| [1] | [T1] | [Meervoudige authenticatie nog niet op de cloudconsole] | [Afdwingen voor alle beheerders] | [Naam] | [jjjj-mm-dd] |

---

## Waar een beoordelaar op let

- **Eerlijkheid.** Een overzicht met alleen "Ja" is ongeloofwaardig. Een paar open punten met een eigenaar en een datum wekken meer vertrouwen.
- **Bewijs per Ja.** De beoordelaar kiest er vaak twee of drie uit en vraagt om het bewijs.
- **Samenhang.** Wat hier staat moet kloppen met je beleid en met je antwoorden in vragenlijsten.

## Versiebeheer

| Versie | Datum | Wijziging | Vastgesteld door |
| --- | --- | --- | --- |
| [1.0] | [jjjj-mm-dd] | Eerste versie | [Naam] |
