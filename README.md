# codelijst-csor-parameter

Codelijst van parameters voor het **Chemische Stoffen en Omgevingsparameters-Register (CSOR)**, gepubliceerd als Linked Data door het [Departement Omgeving](https://omgeving.vlaanderen.be) van de Vlaamse overheid.

## Inhoud

Een **parameter** specificeert een soort uitspraak over een variabele door deze te koppelen aan de context waarin de observatie gebeurt (drager) en de wijze waarop de observatie gebeurt (soortwaardebepaling). Voorbeelden zijn "PCB 49 in waterstaal" of "Totaal N-ethylperfluoroctaansulfonamide in waterbodem".

De codelijst bevat:
- ~4.400 parameters (`csor:Parameter`)
- ~3.200 organisatiespecifieke referenties (`csor:OrganisatieSpecifiekeReferentie`) — vnl. legacy-ID's van VMM

## Bestanden

De codelijst wordt aangeboden in drie RDF-serialisaties:

| Bestand | Formaat |
|---|---|
| `parameters.ttl` | Turtle |
| `parameters.nt` | N-Triples |
| `parameters.rj` | RDF/JSON |
| `parameters_report.ttl` | SHACL-validatierapport |

Pad: `src/main/resources/be/vlaanderen/omgeving/data/id/conceptscheme/csor/parameter/`

## Datamodel

Elke parameter is een `skos:Concept` binnen het conceptschema `https://data.omgeving.vlaanderen.be/id/conceptscheme/csor/parameter` en heeft volgende eigenschappen:

Named graph (Virtuoso): `https://data.omgeving.vlaanderen.be/id/graph/codelijst-csor-parameter`


| Eigenschap | Beschrijving |
|---|---|
| `skos:prefLabel` | Voorkeurslabel (nl) |
| `skos:notation` | Notatie (gelijk aan prefLabel) |
| `csor:variabele` | De gemeten variabele |
| `csor:drager` | De drager / matrix (bv. waterstaal, waterbodem) |
| `csor:soortWaardebepaling` | Wijze van waardebepaling |
| `csor:parameterAspecten` | Aanvullende aspecten van de parameter |
| `csor:resultaatTypes` | Toegelaten resultaattypes |
| `csor:symbool` | Chemisch symbool of afkorting |
| `csor:cas` | CAS-nummer |
| `csor:eionetDD` | Eionet Data Dictionary-referentie |
| `csor:saroadCode` | SAROAD-code |
| `csor:organisatieSpecifiekeReferenties` | Koppelingen naar organisatiespecifieke ID's |
| `owl:deprecated` | Geeft aan of de parameter nog geldig is |

## Namespaces

| Prefix | URI |
|---|---|
| `csor:` | `https://data.omgeving.vlaanderen.be/ns/csor#` |
| `skos:` | `http://www.w3.org/2004/02/skos/core#` |
| `iadopt:` | `https://w3id.org/iadopt/ont/` |
| `qudt:` | `http://qudt.org/schema/qudt/` |

## Validatie

Het bestand `parameters_report.ttl` bevat het SHACL-validatierapport op basis van `csor-constraints:ParameterShape`. Gekende aandachtspunten:
- Parameters met een `csor:afleidingen`-eigenschap die niet voorzien is in de gesloten shape.
- Parameters waarbij `skos:notation` niet uniek is.

## Build

Het project gebruikt Maven. Gegenereerde artefacten komen terecht in de `target/`-map.

## Licentie

[GNU General Public License v3.0](LICENSE)
