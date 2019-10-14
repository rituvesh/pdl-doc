---
navn: Navn
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: november 2019
---

#### Beskrivelse

Personens navn.

#### Spesiell informasjon

Folkeregisteret kommer til å støtte støtte utvidede tegnsett når de tar over som autorativ kilde på navn fra DSF (gamle Folkeregisteret).
Dette inkluderer samiske regn, samtidig kommer de til å gjøre en ny vurdering på bruken av majuskel / minuskel form (hele navn i store bokstaver vs ikke). Det er ikke fastsatt hva de ender på, 
men dersom man er avhengig av at det er på store bokstaver, kan det være nyttig å ta en `toUpperCase()` på dette når dere henter informasjonen fra PDL.

Folkeregisteret kommer også til å utvide lengden på ForkortetNavn fra 25 (i TPS sammensattNavn) til å være 40 tegn når de tar over fra DSF.

*Obs obs! Vi vil etterhvert utvide med Navn fra NAV*
Det vil si at man potensielt få tilbake 2 navn i oppslaget selv når man ikke spør etter historikk. Dersom dere kun vil ha Folkeregisteret sitt, så må dere filtrere på `metadata.master: "FREG"`. 

#### Master og kilder

Folkeregisteret og NAV vil være master.
Folkeregisteret vil ha den største populasjonen, men på personer som kun finnes i NAV (tidligere BOST) eller personer som har utvandret, så kan det være grunn for NAV å legge til et nytt navn for å få igjennom utbetaliger.

#### Historikk

Ja.

PDL-Api eksponerer historikk dersom det er ønsket. Dette kan styres via et flagg i spørringen.

*Folkeregisteret*
Folkeregisteret vil migrere navn, men de vet ikke alltids når et navn var gyldig. Dvs de vet at en person har hatt navnet Ola, så Hans, men ikke når de var. Dette skyldes mangel på metadata tilknyttet navneendringer.
Dette gjør det noe vanskeligere for PDL og NAV når man skal utlede hvilke navn som er gjeldende (nåværende navn) ettersom vi må se på et sekvensnummer (plassering i en liste).

Regel for utledelse av gjeldende navn fra Folkeregisteret i PDL-Api:
Sorter på `folkeregistermetadata.sekvens` i stigende rekkefølge. Det høyeste tallet er den som er gjeldende fra Folkeregisteret.

*TPS*
TPS har lenge hatt støtte for et NAV navn, men de har kun eksponert ett navn ut på tjenesten. Her velger TPS den som ble registrert sist.
Dersom dere ønsker det samme, så kan man sette: `historikk: false`, så får man potensielt tilbake 2 navn. Så ser man på `metadata.endringer.registrert`. Merk at `endringer` er en liste som da burde sorteres på tid og ta den siste. 

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
      <th scope="row">Fornavn</th>
      <td>Fornavn på person</td>
      <td></td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Mellomnavn</th>
      <td>Mellomnavn på person</td>
      <td></td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Etternavn</th>
      <td>Etternavn på person</td>
      <td></td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Forkortet navn</th>
      <td>Personnavn som benyttes ved maskinelle utskrifter (opptil 40 tegn)</td>
      <td></td>
      <td>Valgfri</td>
      <td>Ulik kvalitet: uklar når feltet er fylt ut for de med under 40 tegn, samt vilkårlig rekkefølge</td>
    </tr>
    <tr>
      <th scope="row">Originalt navn</th>
      <td>Personen navn i opprinnelig tegn før translitterering</td>
      <td></td>
      <td>Valgfri</td>
      <td>Ukjent, ny opplysning</td>
    </tr>
    <tr>
      <th scope="row">Folkeregistermetadata</th>
      <td>Inneholder all metadata vi har fått fra Folkeregisteret.</td>
      <td>n/a</td>
      <td>Valgfri - Avhengig av om navnet kommer fra Folkeregisteret</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Metadata</th>
      <td>Se felles definisjon</td>
      <td>n/a</td>
      <td>Obligatorisk</td>
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
      <td>Tidspunktet opplysningen ble opprettet i Folkeregisteret, ofte ukjent på migrert data fra DSF</td>
      <td>Valgfri</td>
    </tr>
    <tr>
      <th scope="row">Gyldighetstidspunkt</th>
      <td>Når navnet gjelder fra. Mangelful informasjon, noe som gjør at vi må ta inn sekvens. Les Historikk lengre opp</td>
      <td>Valgfri</td>
    </tr>
    <tr>
      <th scope="row">Opphoerstidspunkt</th>
      <td>Ikke oppført på navn, et annet navn overtar</td>
      <td>Ikke relevant</td>
    </tr>
    <tr>
      <th scope="row">Kilde</th>
      <td>Opphavet til endringen i Folkeregisteret.</td>
      <td>Valgfri</td>
    </tr>
    <tr>
      <th scope="row">Aarsak</th>
      <td>Beskrivelse fra Folkeregisteret, noe variabelt hva som står her og hvor nyttig det kan være</td>
      <td>Variabelt</td>
    </tr>
    <tr>
      <th scope="row">Sekvens</th>
      <td>Når navnet kommer fra Folkeregisteret, vet vi ikke alltids gyldighetstidspunkt. Se Historikk lengre opp for forklaring av bruk</td>
      <td>Obligatorisk</td>
    </tr>
    </tbody>
</table>


