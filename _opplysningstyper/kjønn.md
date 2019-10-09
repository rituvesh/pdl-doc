---
navn: Kjønn
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: september 2019
---

#### Beskrivelse

Informasjon om personens kjønn.

#### Spesiell informasjon

Folkeregisteret støtter ikke ukjent kjønn. Det vil derfor være tider der hvor man har et annet kjønn i NAV.

#### Master og kilder

FREG er master
PDL kan være master for personkrets D.nr. og utvandret dersom personen har 3. kjønn 


#### Historikk

Ja. Vi får historikk fra Folkeregisteret, men kun fra migreringspunktet og fremover (Migrering fra DSF til Modernisert Folkeregister).

PDL-Api eksponerer den historikken vi har dersom det er ønsket. Dette kan styres via et flagg i spørringen.
Regelen for utledelse av gjeldende verdi er slik:
Sorter på `folkeregisterMetadata.gyldighetstidspunkt`, plukk den siste (altså høyeste dato) (null first). Det vil ikke forekomme noe opphørstidspunkt på denne opplysningen ettersom man vil alltids ha ett kjønn.

OBS OBS: Folkeregisteret har ofte satt `null` (uspesifisert) start-tidspunkt på de opplysningene de har migrert inn ettersom de ikke vet hva gyldighetstidspunktet er. 

#### Informasjonselementer
<table class="table">
  <thead>
    <tr>
        <th>Informasjonselement</th>
        <th>Beskrivelse</th>
        <th>Eksempel</th>
        <th>Kompletthet</th>
        <th>Kvalitet</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <th scope="row">Kjønn</th>
        <td>Gyldige verdier: mann, kvinne (3. kjønn når PDL er master)</td>
        <td></td>
        <td>Obligatorisk</td>
        <td>God</td>
    </tr>
    <tr>
      <th scope="row">FolkeregisterMetadata</th>
      <td>Inneholder all metadata vi har fått fra Folkeregisteret.</td>
      <td>n/a</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Metadata</th>
      <td>Se felles definisjon</td>
      <td>n/a</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
  </tbody>
</table>

##### FolkeregisterMetadata

Inneholder metadata som vi har fått fra Folkeregisteret.

<table class="table">
  <thead>
    <tr>
      <th>Informasjonselement</th>
      <th>Beskrivelse</th>
      <th>Kompletthet</th>
    </tr>
  </thead>
  
  <tbody>
        <tr>
          <th scope="row">Ajourholdstidspunkt</th>
          <td>Tidspunktet opplysningen ble opprettet i Folkeregisteret</td>
          <td>Valgfri</td>
        </tr>
        <tr>
          <th scope="row">Gyldighetstidspunkt</th>
          <td>Når denne Folkeregisterpersonstatusen er gyldig fra og med</td>
          <td>Valgfri. Migrert kan ha `null` (uspesifisert), nye vil ha tidspunkt</td>
        </tr>
        <tr>
          <th scope="row">Opphoerstidspunkt</th>
          <td>Vil aldri forekomme på Kjønn</td>
          <td>N/A</td>
        </tr>
        <tr>
          <th scope="row">Kilde</th>
          <td>Opphavet til endringen i Folkeregisteret. Kan f.eks være NAV, UDI, Politiet, Skatteetaten.</td>
          <td>God</td>
        </tr>
        <tr>
          <th scope="row">Aarsak</th>
          <td>Beskrivelse fra Folkeregisteret, noe variabelt hva som står her og hvor nyttig det kan være</td>
          <td>Variabelt</td>
        </tr>
    </tbody>
</table>