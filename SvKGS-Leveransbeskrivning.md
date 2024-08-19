# SvKGS-Leveransbeskrivning

***Version 1.0***

# Innehåll

**1** [Inledning](#1-inledning)

**2** [Leveranspaket](#2-leveranspaket)

  **2.1** [Utformning av leveranspaket](#21-utformning-av-leveranspaket)
  
**3** [Leveransbeskrivning](#3-leveransbeskrivning)

  **3.1** [Uppgifter i leveransbeskrivningen](#31-uppgifter-i-leveransbeskrivningen)
  
  **3.2** [Exempel på leveransbeskrivning](#32-exempel-på-leveransbeskrivning)

# 1. Inledning

*Svenska kyrkans gemensamma specifikationer för elektronisk arkivering* (SvKGS) beskriver vilken information som ska
ingå vid leverans till Svenska kyrkans gemensamma e-arkiv och hur denna information ska struktureras.

Leveranser till e-arkivet delas in i informationstyper. Exempel på sådana kan vara ärendeakter med handlingar,
ekonomisk redovisning, löneredovisning, personalakter, information om gravrätter, projekthandlingar, bilder
och så vidare. Varje informationstyp kan behöva sin egen specifikation.

Beteckningen gemensamma specifikationer anger att specifikationerna gäller alla leveranser till e-arkivet oavsett
vem det är som levererar informationen och oavsett vilket IT-system som leveranser kommer ifrån.
Genom att informationen arkiveras på detta standardiserade sätt underlättas det långsiktiga bevarande
och möjligheten att återsöka den arkiverade informationen. Standardformatet kan utöver e-arkivering
även användas vid migrering av information mellan andra IT-system.

Svenska kyrkans gemensamma specifikationer är i första hand anpassningar av de specifikationer som
förvaltas av *the Digital Information LifeCycle Interoperability Standards Board* (DILCIS Board).
De kan också vara anpassningar av de förvaltningsgemensamma specifikationer (FGS) som har upprättats av Riksarkivet.
Specifikationerna kan också utgå ifrån andra standarder, om det finns några som är särskilt lämpliga
för informationstypen i fråga.

- [Dilcis Board](https://dilcis.eu)
- [Riksarkivet FGS](https://riksarkivet.se/fgs-earkiv)

# 2. Leveranspaket

Leverans av information till e-arkivet sker i form av leveranspaket. Ett paket är en mappstruktur med filer som samlas i en arkivfil, t.ex. ZIP och TAR.
Paketet innehåller den levererade informationen, arkivobjektet, men också metadata som beskriver informationen och den levererande arkivbildaren.

Svenska kyrkans utformning av leveranspaket (SIP) utgår från Riksarkivets specifikation
[FGS Paketstruktur 1.2](https://riksarkivet.se/Media/pdf-filer/doi-t/FGS_Paketstruktur_RAFGS1V1_2.pdf) men är anpassad efter egna behov.
Efter mottagande i e-arkivet omformas paketet till ett arkivpaket (AIP) som är helt i enlighet med FGS Paketstruktur 1.2. 
Det finns en plan att övergå till version 2.0 av Riksarkivets FGS så snart det är möjligt.

Specifikationerna i det här dokumentet beskriver enbart hur ett leveranspaket i sin helhet ska utformas och vilken metadata som ska ingå.
Hur den information som ska arkiveras ska struktureras, och vilket format den ska ha framgår av andra specifikationer, så som t.ex. [SvKGS Ärendehandlingar](https://github.com/svkau/SvKGS-Arendehandlingar)

## 2.1. Utformning av leveranspaket
Ett leveranspaket ska bestå av en okrypterad ZIP-fil med filändelsen .zip. I ZIP-filen ska det finnas två mappar benämnda ***content*** och ***metadata***.
I mappen ***content*** samlas den information som ska arkiveras. I mappen ***metadata*** samlas alla XML-scheman och andra scheman som behövs för att validera information i mappen ***content***. Hur informationen som ska arkiveras ska struktureras, och vilka scheman som behöver bifogas måste följa specifikationer som har upprättats av Svenska kyrkans arkiv i Uppsala.

ZIP-filens namn ska bestå av ett prefix som identifierar det levererande systemet eller den informationstyp som leveransen avser. Till prefixet ska ett UUID kopplas för att säkerställa filnamnets unicitet. Filen ska slutligen ha filändelsen .zip. **Exempel:** P360_5c3ccbc2-d929-4b4d-be31-d642cabb595d.zip

# 3. Leveransbeskrivning
Tillsammans med leveranspaketet, men som en separat fil som inte ingår i ZIP-filen, ska vid leveransen bifogas en ***leveransbeskrivning***.
Beskrivningen ska vara en JSON-fil med samma namn som ZIP-filen (men med filändelsen .json). JSON-filen ska ha den utformning som specificeras nedan, och ska kunna valideras med schemat leveransbeskrivning_schema_1_0.json. **Exempel:**  P360_5c3ccbc2-d929-4b4d-be31-d642cabb595d.json

## 3.1 Uppgifter i leveransbeskrivningen

### *Leveransfil*

> Obligatoriskt.

> Namnet på den ZIP-fil som innehåller arkivleveransen. Hur namnet ska utformas bestäms i leveransöverenskommelsen.
> Namnet behöver vara unikt och det måste finnas en komponent som identifierar det levererande IT-systemet.
 
> **Exempel:** p360_36c0954c-dcc5-42aa-9e95-a7f199d5bdaf.zip

> **Nyckel:**	`leveransfil`<br/>
> **Datatyp:**	sträng

---

### *Kontrollsumma*

> Obligatoriskt.

> Beräknad kontrollsumma för aktuell **Leveransfil** (ZIP-filen). 

> **Nyckel:**	`kontrollsumma`<br/>
> **Datatyp:**	sträng

---

### *Algoritm*

> Obligatoriskt.

> Den algoritm som har använts för att beräkna **Kontrollsumma**.

> **Exempel:** SHA256

> **Nyckel:**	`algoritm`<br/>
> **Datatyp:**	sträng

---

### *Startdatum*

> Obligatoriskt.

> Startdatum för den levererade informationen i leveransfilen. Datumet anges i formatet xs:dateTime (enligt [W3C XML Schema Definition Language](https://www.w3.org/TR/xmlschema11-2/)).

 
> **Exempel:** 2023-01-01T00:00:00

> **Nyckel:**	`startdatum`<br/>
> **Datatyp:**	sträng

---

### *Slutdatum*

> Obligatoriskt.

> Slutdatum för den levererade informationen i leveransfilen. Datumet anges i formatet xs:dateTime (enligt [W3C XML Schema Definition Language](https://www.w3.org/TR/xmlschema11-2/)).

 
> **Exempel:** 2023-12-31T00:00:00

> **Nyckel:**	`slutdatum`<br/>
> **Datatyp:**	sträng

---

### *Arkivbildare*

> Obligatoriskt.

> Namnet på arkivbildaren för den levererade informationen. Namnet måste finnas i Svenska kyrkans gemensamma arkivredovisning.

 
> **Exempel:** Sunne församling

> **Nyckel:**	`arkivbildare`<br/>
> **Datatyp:**	sträng

---

### *Arkivbildarens ID*

> Obligatoriskt.

> En identifikator för arkivbildaren, i regel organisationsnummer (utan bindestreck). Identifikatorn måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** 2520020674

> **Nyckel:**	`arkivbildare_id`<br/>
> **Datatyp:**	sträng

---

### *Arkivbildarens IT-system: Namn*

> Obligatoriskt.

> Namn på det IT-system som leveransen kommer ifrån ("källsystemet").
 
> **Exempel:** Public 360

> **Nyckel:**	`arkivbildare_system`<br/>
> **Datatyp:**	sträng

---

### *Arkivbildarens IT-system: Version*

> Obligatoriskt.

> Version för det IT-system som leveransen kommer ifrån ("källsystemet").
 
> **Exempel:** 5.17

> **Nyckel:**	`arkivbildare_system_version`<br/>
> **Datatyp:**	sträng

---

### *Nivå*

> Obligatoriskt.

> Den kyrkoorganisatoriska nivå som arkivbildaren tillhör. Värdet kan vara antingen "Församling/pastorat", "Stift" eller "Nationell nivå".
 
> **Exempel:** Stift

> **Nyckel:**	`nivå`<br/>
> **Datatyp:**	sträng

---

### *Ansvarig enhet*

> Obligatoriskt.

> Namnet på den kyrkliga enhet eller organsiation som ansvarar för leveransen. Namnet måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** Sunne pastorat

> **Nyckel:**	`ansvarig_enhet`<br/>
> **Datatyp:**	sträng

---

### *Ansvarig enhets ID*

> Obligatoriskt.

> En identifikator för den kyrkliga enhet eller organisation som ansvarar för leveransen, i regel enhetsid i Svenska kyrkans indelningssystem.
 
> **Exempel:** 2520037173

> **Nyckel:**	`ansvarig_enhet_id`<br/>
> **Datatyp:**	sträng

---

### *Bidragande organisation*

> Inte obligatoriskt.

> Namn på t.ex. konsultföretag som har hjälpt till att skapa uttag för arkivering.
 
> **Exempel:** Konsultföretaget AB

> **Nyckel:**	`bidragande_organisation`<br/>
> **Datatyp:**	sträng

---

### *Informationsägare*

> Obligatoriskt.

> Namn på den kyrkliga enhet som har arkivansvar fär den levererade informationen. Namnet måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** Sunne pastorat

> **Nyckel:**	`informationsägare`<br/>
> **Datatyp:**	sträng

---

### *Informationsägares ID*

> Obligatoriskt.

> En identifikator för den kyrkliga enhet som har arkivansvar för den levererade informationen, i regel organisationsnummer (utan bindestreck).
 
> **Exempel:** 2520037173

> **Nyckel:**	`informationsägare_id`<br/>
> **Datatyp:**	sträng

---

### *Bevarande enhet*

> Obligatoriskt.

> Namn på den enhet eller organisation som tar emot leveransen och ansvarar för bevarandet. I regel är detta alltid "Kyrkostyrelsen, Dokument och Arkiv".
 
> **Exempel:** Kyrkostyrelsen, Dokument och Arkiv

> **Nyckel:**	`bevarande_enhet`<br/>
> **Datatyp:**	sträng

---

### *Bevarandesystem*

> Obligatoriskt.

> Namn på IT-system eller teknisk plattform som används för att ta emot och bevara aktuell leverans.
 
> **Exempel:** ES Solutions, ESSArch

> **Nyckel:**	`bevarandesystem`<br/>
> **Datatyp:**	sträng

---

### *Version av bevarandesystemet*

> Obligatoriskt.

> Bevarandesystemets versionsnummer.
 
> **Exempel:** 3.2.4

> **Nyckel:**	`bevarandesystem_version`<br/>
> **Datatyp:**	sträng

---

### *Leveransöverenskommelse*

> Obligatoriskt.

> Hänvisning till leveransöverenskommelse som gäller för aktuell leverans. I regel anges här ett ärendenummer i kyrkostyrelsens diarium.
 
> **Exempel:** KS 2023-0045

> **Nyckel:**	`leveransöverenskommelse`<br/>
> **Datatyp:**	sträng

---

### *Teknisk leveransöverenskommelse*

> Obligatoriskt.

> Hänvisning till leveransöverenskommelse som har specificerats i Svenska kyrkans gemensamma e-arkiv. Värdet måste vara namnet på en i ESSArch befintlig leveransöverenskommelse.
 
> **Exempel:** LÖK P360

> **Nyckel:**	`leveransöverenskommelse_essarch`<br/>
> **Datatyp:**	sträng

---

### *Arkiv*

> Obligatoriskt.

> Namn på det arkiv som den levererade informationen tillhör. Namnet måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** Församlingsarkiv för Sunne församling

> **Nyckel:**	`arkiv`<br/>
> **Datatyp:**	sträng

---

### *Beståndskod*

> Obligatoriskt.

> Arkivets referenskod eller annat ID. Beståndskoden måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** SE/SVK/116840/001

> **Nyckel:**	`beståndskod`<br/>
> **Datatyp:**	sträng

---

### *Klassificeringsstruktur*

> Obligatoriskt.

> Namn och version på den klassificeringsstruktur som är giltig för leveransen. Värdet måste vara en hänvisning till en klassificeringsstruktur som finns i Svenska kyrkans gemensamma arkivredovining.
 
> **Exempel:** KlaSL2016_1.0

> **Nyckel:**	`klassificeringsstruktur`<br/>
> **Datatyp:**	sträng

---

### *Enhet i klassificeringsstruktur*

> Obligatoriskt (med vissa undantag).

> Namn på den enhet (process) i klassificeringsstrukturen som gäller för leveransen. Värdet måste vara en hänvisning till en enhet i en klassificeringsstruktur som finns i Svenska kyrkans gemensamma arkivredovining.
>
> Om en leverans består av flera ärenden med olika klassificeringar, ska värdet på detta element vara en tom sträng (men elementet får inte utelämnas helt) om klassificeringen framgår av respektive ärende i leveransen.
 
> **Exempel:** 2.2.1

> **Nyckel:**	`klassificeringsstruktur_enhet`<br/>
> **Datatyp:**	sträng

---

### *Förteckningsplan*

> Obligatoriskt.

> Namn och version på den förteckningsplan som är giltig för leveransen. Värdet måste vara en hänvisning till en förteckningsplan som finns i Svenska kyrkans gemensamma arkivredovining.
 
> **Exempel:** Förteckningsplan för lokal nivå (SvKB 2017:1). Version 1.0

> **Nyckel:**	`förteckningsplan`<br/>
> **Datatyp:**	sträng

---

### *Enhet i förteckningsplan*

> Obligatoriskt.

> Namn på den enhet (förvaringsenhet) i förteckningsplanen som är giltig för leveransen. Värdet måste vara en hänvisning till en enhet i en förteckningsplan som finns i Svenska kyrkans gemensamma arkivredovining.
 
> **Exempel:** D1b

> **Nyckel:**	`förteckningsplan_enhet`<br/>
> **Datatyp:**	sträng

---

### *Informationstyp*

> Obligatoriskt.

> Övergripande informationstypsspecifikation. Detta måste vara en specifikation som är giltig i Svenska kyrkans gemensamma e-arkiv.
 
> **Exempel:** ERMS

> **Nyckel:**	`informationstyp`<br/>
> **Datatyp:**	sträng

---

### *Anpassad informationstyp*

> Obligatoriskt.

> Anpassad informationstyp för Svenska kyrkan. Detta måste vara en informationstyp som är giltig i Svenska kyrkans gemensamma e-arkiv.
 
> **Exempel:** SvKGS-Ärendehandlingar. Version 1.0

> **Nyckel:**	`anpassad_informationstyp`<br/>
> **Datatyp:**	sträng

---

### *Gallring*

> Inte obligatoriskt.

> Anger om leveransen (i sin helhet) är gallringsbar. Giltiga värden är "Yes" eller "No".
>
> Om detta värde utelämnas i JSON-filen anses det betyda att värdet är "No".  E-arkivet tar i regel inte emot gallringsbar information.
> Elementet kan också helt utelämnas.
 
> **Exempel:** No

> **Nyckel:**	`gallring`<br/>
> **Datatyp:**	sträng

---

### *Sekretess*

> Inte obbligatoriskt.

> Anger om leveransen innehåller information som kan omfattas av sekretess eller GDPR. Giltiga värden är "Secrecy" eller "GDPR".
>
> Om ingen sekretess eller GDPR föreligger, utelämnas elementet i JSON-filen.
> Om nyckeln finns i JSON-filen, men värdet är en tom sträng, anses det vara det samma om om elementet hade utelämnats.
 
> **Exempel:** Secrecy

> **Nyckel:**	`sekretess`<br/>
> **Datatyp:**	sträng

---

### *Diarium: Kod*

> Enbart obbligatoriskt om leveransen avser ärendehandlingar från diariesystem.

> Kod i diariesystem för det diarium som leveransen avser.
 
> **Exempel:** P

> **Nyckel:**	`diarium_kod`<br/>
> **Datatyp:**	sträng

---

### *Diarium: Namn*

> Enbart obbligatoriskt om leveransen avser ärendehandlingar från diariesystem.

> Namn i diariesystem på det diarium som leveransen avser.
 
> **Exempel:** Sunne pastorat

> **Nyckel:**	`diarium_namn`<br/>
> **Datatyp:**	sträng


## 3.2 Exempel på leveransbeskrivning

```json
{
    "leveransfil": "P360_6ece020a-09ad-4880-9f38-9f20eb636e50.zip",
    "kontrollsumma": "c4684c92131a9a84227d95d7ea32bce8",
    "algoritm": "md5",
    "startdatum": "2019-12-13T13:20:58",
    "slutdatum": "2024-04-18T10:26:57",
    "arkivbildare": "Sunne församling",
    "arkivbildare_id": "0123456789",
    "arkivbildare_system": "Public 360",
    "arkivbildare_system_version": "5.17",
    "nivå": "Församling/pastorat",
    "ansvarig_enhet": "Sunne pastorat",
    "ansvarig_enhet_id": "20111",
    "bidragande_organisation": "Tietoevry",
    "informationsägare": "Sunne pastorat",
    "informationsägare_id": "1234567890",
    "bevarande_enhet": "Kyrkostyrelsen, Dokument och Arkiv",
    "bevarandesystem": "ES Solutions, ESSArch",
    "bevarandesystem_version": "3.2.4",
    "leveransöverenskommelse": "KS 2024-0736",
    "leveransöverenskommelse_essarch": "LÖK P360",
    "arkiv": "församlingsarkiv för Sunne församling",
    "beståndskod": "SE/SVK/116840/001",
    "klassificeringsstruktur": "KlaSL2016_1.0",
    "klassificeringsstruktur_enhet": "",
    "förteckningsplan": "Förteckningsplan för lokal nivå (SvKB 2017:1). Version 1.0",
    "förteckningsplan_enhet": "D1aa",
    "informationstyp": "ERMS",
    "anpassad_informationstyp": "SvKGS-Ärendehandlingar. Version 1.0",
    "gallring": "",
    "sekretess": "",
    "diarium_kod": "F",
    "diarium_namn": "Gärsnäs församling"
}
```
