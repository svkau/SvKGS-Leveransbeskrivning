# SvKGS-Leveransspecifikation

***Version 0.1***

# Innehåll

- 1 [Inledning](#1-inledning)
  - 1.1 [Arkivpaket](#11-arkivpaket)
- 3 [Dataelement med exempel](#3-dataelement-med-exempel)
  - 3.1 [Övergripande information om XML-dokumentet](#31-övergripande-information-om-xml-dokumentet)

# 1. Inledning

*Svenska kyrkans gemensamma specifikationer för elektronisk arkivering* beskriver vilken information som ska
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

## 1.1. Arkivpaket

Leverans av information till e-arkivet sker i form av arkivpaket. Ett paket är en mappstruktur med filer.
Paketet innehåller den levererade informationen, arkivobjektet, men också metadata som beskriver
informationen och den levererande arkivbildaren.

Specifikationerna i det här dokumentet beskriver arkivobjektet, det vill säga den information som
ska arkiveras. Det utgör endast en del av hela arkivpaketet.

Arkivpaketet i sin helhet utformas i enlighet med Riksarkivets specifikation
[FGS Paketstruktur 1.2](https://riksarkivet.se/Media/pdf-filer/doi-t/FGS_Paketstruktur_RAFGS1V1_2.pdf).



# 3. Leveransspecifikation

## *leveransfil*

> Obligatoriskt.

> Namnet på den ZIP-fil som innehåller arkivleveransen. Hur namnet ska utformas bestäms i leveransöverenskommelsen.
> Namnet behöver vara unikt och det måste finnas en komponent som identifierar det levererande IT-systemet.
 
> **Exempel:** p360_36c0954c-dcc5-42aa-9e95-a7f199d5bdaf.zip

> **Nyckel:**	`leveransfil`<br/>
> **Datatyp:**	sträng

---

## *Startdatum*

> Obligatoriskt.

> Startdatum för den levererade informationen i leveransfilen. Datumet anges i formatet xs:dateTime (enligt [W3C XML Schema Definition Language](https://www.w3.org/TR/xmlschema11-2/)).

 
> **Exempel:** 2023-01-01T00:00:00

> **Nyckel:**	`startdatum`<br/>
> **Datatyp:**	sträng

---

## *Slutdatum*

> Obligatoriskt.

> Slutdatum för den levererade informationen i leveransfilen. Datumet anges i formatet xs:dateTime (enligt [W3C XML Schema Definition Language](https://www.w3.org/TR/xmlschema11-2/)).

 
> **Exempel:** 2023-01-01T00:00:00

> **Nyckel:**	`startdatum`<br/>
> **Datatyp:**	sträng

---

## *Arkivbildare*

> Obligatoriskt.

> Namnet på arkivbildaren för den levererade informationen. Namnet måste finnas Svenska kyrkans gemensamma arkivredovisning.

 
> **Exempel:** Sunne församling

> **Nyckel:**	`arkivbildare`<br/>
> **Datatyp:**	sträng

---

## *Arkivbildarens ID*

> Obligatoriskt.

> En identifikator för arkivbildaren, i regel organisationsnummer (utan bindestreck). Identifikatorn måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** 2520020674

> **Nyckel:**	`arkivbildare_id`<br/>
> **Datatyp:**	sträng

---

## *Ansvarig enhet*

> Obligatoriskt.

> Namnet på den kyrkliga enhet eller organsiation som ansvarar för leveransen.
 
> **Exempel:** Sunne pastorat

> **Nyckel:**	`ansvarig_enhet`<br/>
> **Datatyp:**	sträng

---

## *Ansvarig enhets ID*

> Obligatoriskt.

> En identifikator för den kyrkliga enhet eller organisation som ansvarar för leveransen, i regel organisationsnummer (utan bindestreck).
 
> **Exempel:** 2520037173

> **Nyckel:**	`ansvarig_enhet_id`<br/>
> **Datatyp:**	sträng

---

## *Bidragande organisation*

> Inte obligatoriskt.

> Namn på t.ex. konsultföretag som
 
> **Exempel:** 2520037173

> **Nyckel:**	`ansvarig_enhet_id`<br/>
> **Datatyp:**	sträng

---
