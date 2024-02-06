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



# 3. Dataelement med exempel

## 3.1. Övergripande information om XML-dokumentet

Kontroll är ett obligatoriskt element som beskriver själva XML-filen och vad den innehåller.
Den underlättare förståelsen av informationen, om XML-filen skulle separeras från arkivpaketet.

### Elementlista 1. Kontroll

---

#### ERMS-SVK:1 - *Identifikator*

(ERMS1)

> Identifierar ERMS-dokumentet

> Obligatoriskt. Elementet får upprepas.

> Tre identifikatorer måste användas: arkivbildarens namn och id samt ärendets nummer. Se exempel nedan.

> **XML-element:**	`identification`<br/>
> **Datatyp:**	string

---

#### ERMS-SVK:2 - *Typ av identifikator*

(ERMS2)

> Beskrivning av identifikatorn.

> Obligatoriskt. Värdet väljs från [Värdelista 1](ERMS-SVK-ARENDE-vardelistor.md#erms-svk-arende-v%C3%A4rdelista-1---typ-av-identifikator).

> **XML-element:**	`identification/@identificationType`<br/>
> **Datatyp:**	string

---