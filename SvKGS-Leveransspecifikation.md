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

 
> **Exempel:** 2023-12-31T00:00:00

> **Nyckel:**	`slutdatum`<br/>
> **Datatyp:**	sträng

---

## *Arkivbildare*

> Obligatoriskt.

> Namnet på arkivbildaren för den levererade informationen. Namnet måste finnas i Svenska kyrkans gemensamma arkivredovisning.

 
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

## *Nivå*

> Obligatoriskt.

> Den kyrkoorganisatoriska nivå som arkivbildaren tillhör. Värdet kan vara antingen "lokal", "regional" eller "nationell".
 
> **Exempel:** lokal

> **Nyckel:**	`nivå`<br/>
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

> Namn på t.ex. konsultföretag som har hjälpt till att skapa uttag för arkivering.
 
> **Exempel:** Konsultföretaget AB

> **Nyckel:**	`bidragande_organisation`<br/>
> **Datatyp:**	sträng

---

## *Informationsägare*

> Obligatoriskt.

> Namn på den kyrkliga enhet som har arkivansvar fär den levererade informationen. Namnet måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** Sunne pastorat

> **Nyckel:**	`informationsägare`<br/>
> **Datatyp:**	sträng

---

## *Informationsägares ID*

> Obligatoriskt.

> En identifikator för den kyrkliga enhet som har arkivansvar för den levererade informationen, i regel organisationsnummer (utan bindestreck).
 
> **Exempel:** 2520037173

> **Nyckel:**	`informationsägare_id`<br/>
> **Datatyp:**	sträng

---

## *Bevarande enhet*

> Obligatoriskt.

> Namn på den enhet eller organisation som tar emot leveransen och ansvarar för bevarandet. I regel är detta alltid "Kyrkostyrelsen, Dokument och Arkiv".
 
> **Exempel:** Kyrkostyrelsen, Dokument och Arkiv

> **Nyckel:**	`bevarande_enhet`<br/>
> **Datatyp:**	sträng

---

## *Bevarandesystem*

> Obligatoriskt.

> Namn på IT-system eller teknisk plattform som används för att ta emot och bevara aktuell leverans.
 
> **Exempel:** ESSArch

> **Nyckel:**	`bevarandesystem`<br/>
> **Datatyp:**	sträng

---

## *Version av bevarandesystemet*

> Obligatoriskt.

> Bevarandesystemets versionsnummer.
 
> **Exempel:** 2.0

> **Nyckel:**	`bevarandesystem_version`<br/>
> **Datatyp:**	sträng

---

## *Levererande system*

> Obligatoriskt.

> Namn på det IT-system som den levererade informationen har hämtats från, källsystemet.
 
> **Exempel:** Public 360

> **Nyckel:**	`levererande_system`<br/>
> **Datatyp:**	sträng

---

## *Versions av det levererande systemet*

> Obligatoriskt.

> Levererande systems versionsnummer.
 
> **Exempel:** 2.0

> **Nyckel:**	`levererande_system_version`<br/>
> **Datatyp:**	sträng

---

## *Leveransöverenskommelse*

> Obligatoriskt.

> Hänvisning till leveransöverenskommelse som gäller för aktuell leverans. I regel anges här ett ärendenummer i kyrkostyrelsens diarium.
 
> **Exempel:** KS 2023-0045

> **Nyckel:**	`leveransöverenskommelse`<br/>
> **Datatyp:**	sträng

---

## *Teknisk leveransöverenskommelse*

> Obligatoriskt.

> Hänvisning till leveransöverenskommelse som har specificerats i Svenska kyrkans gemensamma e-arkiv. Värdet måste vara namnet på en i ESSArch befintlig leveransöverenskommelse.
 
> **Exempel:** ERMS_VIPS

> **Nyckel:**	`leveransöverenskommelse_essarch`<br/>
> **Datatyp:**	sträng

---

## *Arkiv*

> Obligatoriskt.

> Namn på det arkiv som den levererade informationen tillhör. Namnet måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** Församlingsarkiv för Sunne församling

> **Nyckel:**	`arkiv`<br/>
> **Datatyp:**	sträng

---

## *Beståndskod*

> Obligatoriskt.

> Arkivets referenskod eller annat ID. Beståndskoden måste finnas i Svenska kyrkans gemensamma arkivredovisning.
 
> **Exempel:** SE/SVK/0976/0003

> **Nyckel:**	`beståndskod`<br/>
> **Datatyp:**	sträng

---

## *Klassificeringsstruktur*

> Obligatoriskt.

> Namn och version på den klassificeringsstruktur som är giltig för leveransen. Värdet måste vara en hänvisning till en klassificeringsstruktur som finns i Svenska kyrkans gemensamma arkivredovining.
 
> **Exempel:** KlassL_0.1_2022

> **Nyckel:**	`klassificeringsstruktur`<br/>
> **Datatyp:**	sträng

---

## *Enhet i klassificeringsstruktur*

> Obligatoriskt.

> Namn på den enhet (process) i klassificeringsstrukturen som gäller för leveransen. Värdet måste vara en hänvisning till en enhet i en klassificeringsstruktur som finns i Svenska kyrkans gemensamma arkivredovining.
 
> **Exempel:** 2.2.1

> **Nyckel:**	`klassificeringsstruktur_enhet`<br/>
> **Datatyp:**	sträng

---

## *Förteckningsplan*

> Obligatoriskt.

> Namn och version på den förteckningsplan som är giltig för leveransen. Värdet måste vara en hänvisning till en förteckningsplan som finns i Svenska kyrkans gemensamma arkivredovining.
 
> **Exempel:** Förteckningsplan Lokal nivå 2022

> **Nyckel:**	`förteckningsplan`<br/>
> **Datatyp:**	sträng

---

## *Enhet i förteckningsplan*

> Obligatoriskt.

> Namn och version på den enhet (förvaringsenhet) i förteckningsplanen som är giltig för leveransen. Värdet måste vara en hänvisning till en enhet i en förteckningsplan som finns i Svenska kyrkans gemensamma arkivredovining.
 
> **Exempel:** D1b

> **Nyckel:**	`förteckningsplan_enhet`<br/>
> **Datatyp:**	sträng

---

## *Informationstyp*

> Obligatoriskt.

> Övergripande informationstypsspecifikation. Detta måste vara en specifikation som är giltig i Svenska kyrkans gemensamma e-arkiv.
 
> **Exempel:** ERMS

> **Nyckel:**	`informationstyp`<br/>
> **Datatyp:**	sträng

---

## *Anpassad informationstyp*

> Obligatoriskt.

> Anpassad informationstyp för Svenska kyrkan. Detta måste vara en informationstyp som är giltig i Svenska kyrkans gemensamma e-arkiv.
 
> **Exempel:** SvKGS-Ärendehandlingar

> **Nyckel:**	`anpassad_informationstyp`<br/>
> **Datatyp:**	sträng

---

## *Gallring*

> Inte obligatoriskt.

> Anger om leveransen (i dess helhet) är gallringsbar. Giltiga värden är "Yes" eller "No".
>
> Om detta värde utelämnas i JSON-filen anses det betyda att värdet är "No".  E-arkivet tar i regel inte emot gallringsbar information.
 
> **Exempel:** No

> **Nyckel:**	`gallring`<br/>
> **Datatyp:**	sträng

---

## *Sekretess*

> Inte obbligatoriskt.

> Anger om leveransen innehåller information som kan omfattas av sekretess eller GDPR. Giltiga värden är "Secrecy" eller "GDPR".
>
> Om ingen sekretess eller GDPR föreligger, utelämnas värdet i JSON-filen.
 
> **Exempel:** Secrecy

> **Nyckel:**	`sekretess`<br/>
> **Datatyp:**	sträng

# Exempel på JSON-fil
```json
{
"leveransfil": "p360_36c0954c-dcc5-42aa-9e95-a7f199d5bdaf.zip",
"startdatum": "2023-01-01T00:00:00",
"slutdatum": "2023-12-31T00:00:00",
"arkivbildare": "Sunne församling",
"arkivbildare_id": "2520020674",
"nivå": "lokal",
"ansvarig_enhet": "Sunne pastorat",
"ansvarig_enhet_id": "2520037173",
"bidragande_organisation": "Konsultföretaget AB",
"informationsägare": "Sunne pastorat",
"informationsägare_id": "2520037173",
"bevarande_enhet": "Kyrkostyrelsen, Dokument och Arkiv",
"bevarandesystem": "ESSArch",
"bevarandesystem_version": "2.0",
"levererande_system": "Public 360",
"levererande_system_version": "2.0",
"leveransöverenskommelse": "KS 2023-4045",
"leveransöverenskommelse_essarch": "ERMS_VIPS",
"arkiv": " Församlingsarkiv för Sunne församling",
"beståndskod": "SE/SVK/0976/0003",
"klassificeringsstruktur": " KlassL_0.1_2022",
"klassificeringsstruktur_enhet": "2.2.1",
"förteckningsplan": "Förteckningsplan Lokal nivå 2022",
"förteckningsplan_enhet": "D1b",
"informationstyp": "ERMS",
"anpassad_informationstyp": "SvKGS-Ärendehandlingar",
"gallring": "No",
"sekretess": "Secrecy"
}
```



