---
navn: Adressebeskyttelse
hendelser: nei
oppslag: ja
sok: nei
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: Er tilgjengelig
---


#### Beskrivelse

Informasjon om gradering av adresseinformasjon for personer iht. Beskyttelsesinstruksen.
Dette ble tidligere omtalt som Diskresjonskode 6 og 7 fra TPS.

Merk at man kan få tomt svar (dvs ingen Adressebeskyttelse) og Ugradert. Dette er slik vi får det fra Folkeregisteret, men vi har ingen tilfeller med Ugradert hittil i Produksjon.

#### Master og kilder

Folkeregisteret er eneste kilde og master til opplysningen for NAV.
  
#### Historikk

PDL-Api eksponerer historikk dersom det er ønsket. Dette kan styres via et flagg i spørringen.
Regelen for utledelse av gjeldende verdi er slik:
Sorter på `folkeregistermetadata.gyldighetstidspunkt`, plukk den siste (altså høyeste dato), så sjekk om denne har en `folkeregistermetadata.opphoerstidspunkt` som er etter nå-tidspunktet.

Visuelt eksempel:
```
|----->
             |-----| (opphørt)
      |----->

Sortert:
|---->|----->|-----|
```

Her er da den siste opphørt og ingen er dermed gjeldende. Dersom flagget `historikk: false` er sendt inn i grensesnittet, så vil denne regelen bli kjørt og ingen resultat kommer tilbake.

#### Informasjonselementer

<table class="table">
    <thead>
        <tr>
            <th>Informasjonselement</th>
            <th>Beskrivelse</th>
            <th>Eksempel</th>
            <th>Kompletthet</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Gradering</th>
            <td>Graderingsnivået på adressebeskyttelsen. <br>
            <br>
            Mulige verdier: <br>
            Ugradert: Ingen behov for gradering.<br>
            <br>
            Fortrolig (Kode 7 fra TPS): graderingen fortrolig i henhold til Beskyttelsesinnstruksen.<br> 
            Benyttes dersom det vil kunne skade offentlige interesser, en bedrift, en institusjon eller en enkeltperson at dokumentets innhold blir kjent for vedkommende.<br>
            <br>
            Strengt fortrolig (Kode 6 fra TPS): Gradering strengt fortrolig i henhold til Beskyttelsesinnstruksen.<br>
            Benyttes dersom det vil kunne forårsake betydelig skade for offentlige interesser, en bedrift, en institusjon eller en enkeltperson at dokumentets innhold blir kjent for uvedkommende.
            </td>
            <td></td>
            <td>obligatorisk</td>
        </tr>
        <tr>
          <th scope="row">Folkeregistermetadata</th>
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

##### Folkeregistermetadata

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
          <td>Obligatorisk</td>
        </tr>
        <tr>
          <th scope="row">Gyldighetstidspunkt</th>
          <td>Når denne Adressebeskyttelsen er gyldig fra og med</td>
          <td>Obligatorisk</td>
        </tr>
        <tr>
          <th scope="row">Opphoerstidspunkt</th>
          <td>Opphørstidspunktet for opplysningen, se kapittel om Historikk for mer informasjon</td>
          <td>Valgfri</td>
        </tr>
        <tr>
          <th scope="row">Kilde</th>
          <td>Opphavet til endringen i Folkeregisteret.</td>
          <td>God</td>
        </tr>
        <tr>
          <th scope="row">Aarsak</th>
          <td>Beskrivelse fra Folkeregisteret, noe variabelt hva som står her og hvor nyttig det kan være</td>
          <td>Variabelt</td>
        </tr>
    </tbody>
</table>
