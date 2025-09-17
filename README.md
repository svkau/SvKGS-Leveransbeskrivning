# SvKGS-Leveransbeskrivning. Version 1.1

## Ändringar i denna version

| Ändringstyp       | Fältnamn                      | Beskrivning / Kommentar                                                                 |
|-------------------|-------------------------------|------------------------------------------------------------------------------------------|
| 🆕 Nytt fält       | `diarium_kod`                 | Kod i diariesystem för det diarium som leveransen avser                                 |
| 🆕 Nytt fält       | `diarium_namn`                | Namn i diariesystem på det diarium som leveransen avser                                 |
| 🆕 Nytt fält       | `kontrollsumma`              | Kontrollsumma för ZIP-filen (fanns tidigare men var ej obligatorisk)                    |
| 🆕 Nytt fält       | `algoritm`                   | Algoritm för kontrollsumma (fanns tidigare men var ej obligatorisk)                     |
| 🗑️ Borttaget fält  | `nivå`                        | Kyrkoorganisatorisk nivå (enum: Församling/pastorat, Stift, Nationell nivå)             |
| 🗑️ Borttaget fält  | `bevarande_enhet`            | Enhet som tar emot leveransen (enum: Kyrkostyrelsen, Dokument och Arkiv)                |
| 🗑️ Borttaget fält  | `bevarandesystem`            | IT-system för bevarande (enum: ES Solutions, ESSArch)                                   |
| 🗑️ Borttaget fält  | `bevarandesystem_version`    | Versionsnummer för bevarandesystemet                                                    |
| 🔧 Justering       | `minLength: 1`                | Tillagt på många strängfält för att förhindra tomma värden                              |
| 🔧 Justering       | `required`-lista              | Utökad med flera fält, bl.a. `kontrollsumma`, `algoritm`, `diarium_kod`, `diarium_namn` |
| 🔧 Justering       | `$id`                         | Ändrad URL för schemaidentifierare                                                      |


## Innehåll

[Specifikation](SvKGS-Leveransbeskrivning.md)

[JSON-schema för leveransbeskrivning](leveransbeskrivning_diarium_schema_1_1.json)

[Exempel på leveransbeskrivning](P360_5c3ccbc2-d929-4b4d-be31-d642cabb595d.json)

[Exempel på leveranspaket](P360_5c3ccbc2-d929-4b4d-be31-d642cabb595d.zip)
