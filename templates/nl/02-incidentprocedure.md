# Incidentprocedure

> **Sjabloon uit het [Open Evidence Pack](https://github.com/holdvero/open-evidence-pack)**, CC BY 4.0, gemaakt door [Holdvero](https://holdvero.com).
>
> **Laatst herzien door Holdvero: 2026-10-11.** Dit sjabloon is een begin, geen juridisch advies. Controleer welke wettelijke, contractuele en toezichtseisen voor jou gelden voordat je het gebruikt.
>
> **Zo gebruik je dit sjabloon** (verwijder dit blok als je klaar bent)
> 1. Vervang alles tussen `[blokhaken]`.
> 2. Neem de termijn waarbinnen je klanten informeert over uit je **verwerkersovereenkomsten en contracten**. Beloof hier nooit iets anders dan daar staat.
> 3. Valt je organisatie onder NIS2? Laat paragraaf 6 dan staan en vul de juiste autoriteit in. Zo niet, schrap die paragraaf.
> 4. Oefen de procedure minstens eens per jaar met een kort scenario, en leg vast dat je dat deed.

| | |
| --- | --- |
| Organisatie | [Bedrijfsnaam B.V.] |
| Eigenaar van dit document | [Naam, functie] |
| Versie | [1.0] |
| Datum vaststelling | [jjjj-mm-dd] |
| Volgende herziening | [jjjj-mm-dd] |

## 1. Wat is een incident?

Een **beveiligingsincident** is elke gebeurtenis waardoor de vertrouwelijkheid, juistheid of beschikbaarheid van onze dienst of van gegevens in gevaar komt of kan komen. Voorbeelden:

- een laptop of telefoon met toegang tot bedrijfsgegevens is kwijt of gestolen;
- iemand heeft (mogelijk) een wachtwoord ingevuld op een phishingpagina;
- klantgegevens zijn naar de verkeerde persoon gestuurd;
- onze dienst is langer dan [x minuten] niet bereikbaar;
- een leverancier meldt een incident dat onze gegevens kan raken;
- vreemde activiteit in logbestanden, bijvoorbeeld aanmeldingen vanuit een onbekend land.

Een **datalek** is een incident waarbij persoonsgegevens verloren gaan, of bij onbevoegden terechtkomen of kunnen komen. Voor datalekken gelden wettelijke regels (paragraaf 5).

**Twijfel je? Meld het.** Liever tien meldingen die niets blijken te zijn dan één die te laat komt.

## 2. Melden

Iedereen die een (mogelijk) incident ziet, meldt het **direct** bij:

| Kanaal | Gegevens |
| --- | --- |
| Eerste aanspreekpunt | [Naam], [telefoonnummer] |
| Vervanger | [Naam], [telefoonnummer] |
| Meldadres | [security@bedrijf.nl] |

Klanten en externen kunnen een incident of kwetsbaarheid melden via [security@bedrijf.nl / link naar meldpagina].

Wat je meldt: wat je zag, wanneer, op welk systeem, en wat je al gedaan hebt. Verander niets aan het systeem als dat niet nodig is om schade te beperken; zo blijven sporen bewaard.

## 3. Rollen

| Rol | Wie | Taak |
| --- | --- | --- |
| Incidentcoördinator | [Naam], vervanger [Naam] | Leidt de afhandeling, beslist over ernst en volgende stappen, houdt het logboek bij |
| Technisch | [Naam] | Onderzoekt, beperkt de schade, herstelt |
| Communicatie met klanten | [Naam] | Informeert klanten volgens paragraaf 5 |
| Directie | [Naam] | Beslist bij ernstige incidenten, meldt aan autoriteiten waar nodig |

## 4. Stappen

1. **Vastleggen.** De coördinator opent een incidentlogboek ([locatie, bijvoorbeeld een ticket of gedeeld document]) met tijdstip van melding, wat er bekend is en wie betrokken is. Alles wat daarna gebeurt, komt in dat logboek met tijdstip.
2. **Inschatten.** Bepaal de ernst:

   | Ernst | Wanneer | Voorbeelden |
   | --- | --- | --- |
   | Hoog | Klantgegevens mogelijk gelekt of aangetast, of de dienst ligt voor veel klanten plat | Inbraak in de productieomgeving, datalek met klantgegevens |
   | Middel | Risico voor onze eigen systemen, beperkte gevolgen voor klanten | Gestolen laptop met versleutelde schijf, kortdurende storing |
   | Laag | Geen gevolgen voor klanten of gegevens | Geblokkeerde phishingmail, mislukte inlogpogingen |

3. **Beperken.** Stop de schade: sluit accounts af, wijzig wachtwoorden en sleutels, isoleer systemen, schakel een leverancier in.
4. **Onderzoeken.** Wat is er gebeurd, sinds wanneer, welke gegevens en welke klanten zijn geraakt?
5. **Informeren.** Bepaal wie geïnformeerd moet worden: klanten (paragraaf 5), de toezichthouder (paragraaf 5 en 6), de politie bij een misdrijf, de verzekeraar.
6. **Herstellen.** Breng de dienst en gegevens terug naar een betrouwbare toestand, bijvoorbeeld vanuit een back-up.
7. **Afsluiten en leren.** Bij ernst middel of hoog schrijft de coördinator binnen [10 werkdagen] een korte evaluatie: oorzaak, gevolgen, wat ging goed, wat verbeteren we, wie doet dat en wanneer.

## 5. Datalekken en klanten informeren

Voor de meeste klantgegevens zijn wij **verwerker** en is de klant **verwerkingsverantwoordelijke**. Dat betekent:

- **Wij informeren de klant** zonder onredelijke vertraging nadat we een datalek ontdekken, en uiterlijk binnen **[termijn uit de verwerkersovereenkomst, bijvoorbeeld 24 of 48 uur]**. We sturen wat we op dat moment weten en vullen aan zodra we meer weten.
- **De klant beslist** of het datalek gemeld moet worden aan de toezichthouder en aan betrokkenen. Tenzij het datalek waarschijnlijk geen risico voor mensen oplevert, moet de klant het waar mogelijk binnen 72 uur na ontdekking melden aan de toezichthouder. Daarom moeten wij snel zijn.
- Onze melding aan de klant bevat waar mogelijk: wat er gebeurd is, wanneer, welke soorten gegevens en hoeveel betrokkenen ongeveer, de waarschijnlijke gevolgen, wat we al gedaan hebben, en een contactpersoon.

Voor gegevens waarvoor **wij zelf verwerkingsverantwoordelijke** zijn (bijvoorbeeld van onze medewerkers of van onze eigen klantcontacten), beoordelen wij zelf of we moeten melden aan de toezichthouder (Nederland: Autoriteit Persoonsgegevens; België: Gegevensbeschermingsautoriteit), binnen 72 uur na ontdekking.

**Elk datalek** wordt vastgelegd in ons register van datalekken ([locatie]), ook als het niet gemeld hoeft te worden.

## 6. NIS2 (alleen als dit op ons van toepassing is)

[Schrap deze paragraaf als je organisatie niet onder NIS2 valt. Twijfel je? Zoek uit of je een essentiële of belangrijke entiteit bent onder de wet in jouw land.]

Bij een **significant incident** melden wij aan [het CSIRT of de bevoegde autoriteit, bijvoorbeeld in België het CCB]:

| Wanneer | Wat |
| --- | --- |
| Binnen 24 uur na ontdekking | Vroegtijdige waarschuwing |
| Binnen 72 uur na ontdekking | Incidentmelding met eerste beoordeling |
| Binnen 1 maand na de incidentmelding | Eindverslag |

Controleer de precieze regels en het meldloket in de wetgeving van jouw land.

## 7. Contactgegevens

| Partij | Contact |
| --- | --- |
| Hostingpartij | [Naam, supportkanaal, contractnummer] |
| [Andere kritieke leverancier] | [Contact] |
| Verzekeraar (cyberverzekering) | [Contact, polisnummer] |
| Juridisch adviseur | [Contact] |
| Toezichthouder persoonsgegevens | [Autoriteit Persoonsgegevens / Gegevensbeschermingsautoriteit] |

## 8. Oefenen en herzien

- We oefenen deze procedure minstens eens per jaar met een kort scenario en leggen vast wanneer en met wie.
- We herzien deze procedure na elk incident met ernst hoog, en minstens eens per jaar.

## Officiële bronnen

Controleer de termijnen en meldplichten in de officiële teksten. Ze kunnen veranderen, en voor NIS2 geldt de omzettingswet van jouw land.

- AVG (Verordening (EU) 2016/679), artikel 33 en 34: [EUR-Lex](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- NIS2-richtlijn (Richtlijn (EU) 2022/2555), artikel 23: [EUR-Lex](https://eur-lex.europa.eu/eli/dir/2022/2555/oj)
- Autoriteit Persoonsgegevens: [autoriteitpersoonsgegevens.nl](https://autoriteitpersoonsgegevens.nl)
- Gegevensbeschermingsautoriteit: [gegevensbeschermingsautoriteit.be](https://www.gegevensbeschermingsautoriteit.be)
- Centrum voor Cybersecurity België (CCB): [ccb.belgium.be](https://ccb.belgium.be)

---

## Waar een beoordelaar op let

- **Een concrete termijn voor klanten**, die overeenkomt met de verwerkersovereenkomst.
- **Namen en een vervanger**, zodat het ook werkt als iemand op vakantie is.
- **Een register van incidenten en datalekken**, ook als het leeg is: dan zeg je "nul incidenten in [periode]" en kun je het register laten zien.
- **Bewijs van een oefening**, bijvoorbeeld een kort verslag met datum.

## Versiebeheer

| Versie | Datum | Wijziging | Vastgesteld door |
| --- | --- | --- | --- |
| [1.0] | [jjjj-mm-dd] | Eerste versie | [Naam] |
