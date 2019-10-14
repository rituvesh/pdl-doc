---
navn: Folkeregisterpersonstatus
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: Februar 2020
---

#### Beskrivelse

Folkeregisterpersonstatus beskriver personens tilknytting til Folkeregisteret.

Merk: Folkeregisteret anbefaler å IKKE benytte seg av Folkeregisterpersonstatus til noe annet enn å se på den gjeldende statusen. 
Den er direkte knyttet mot saksbehandling som skjer i Folkeregisteret, ikke mot når ting skjer i virkeligheten. 

F.eks: At en person dør 19.01.2019 (en lørdag), blir saksbehandlet i Folkeregisteret 21.01.2019. Dette vil da føre til et gyldighetstidspunkt 21.01.2019.

##### Beskrivelse av statusene
###### Bosatt
Registreringsstatus i Folkeregisteret for en person som oppholder seg lovlig i en norsk kommune i minst seks måneder.
* Personstatusen bosatt benyttes om personer som har eller skal ha opphold i Norge i 6 måneder eller mer. Dersom en person innfrir kravet til bosetting, skal personen tildeles fødselsnummer.
* Personer som skal ha personstatus bosatt (enten eller):
  -	Personer som fødes i Norge, med en eller to bosatte foreldre
  -	Personer som innflytter til Norge, med hensikt å oppholde seg i landet i 6 måneder eller lengre

###### Utflyttet
Registreringsstatus i Folkeregisteret for en person som er vedtatt utflyttet fra Norge iht. kriterier i Folkeregisterloven § 4-3.

* Personstatusen utflyttet benyttes om personer med fødselsnummer som ikke er bosatt i Norge
* Personer som skal ha personstatus «utflyttet» (enten eller):
  - Personer som melder flytting, og får innvilget utflytting fra Norge av Folkeregisteret
  - Personer som ikke har hatt opphold i Norge i over 6 måneder 
  - Personer som ikke får innvilget eller fornyet oppholdstillatelse
  - Personer som har ukjent oppholdssted i 2 år, og det blir truffet vedtak om utflytting

###### Forsvunnet
Registreringsstatus i Folkeregisteret for en person som er blitt borte i forbindelse med ulykke, naturkatastrofe, forbrytelse eller er savnet på sjøen, i fjellet eller lignende. Personer som har forsvunnet fra samfunnet.

* Personer som vil få personstatus forsvunnet:
  - Personer med fødsels- eller d-nummer som meldes til Folkeregisteret som forsvunnet av politi eller påtalemyndighet.

###### Død
Registreringsstatus i Folkeregisteret for en person som er erklært død av lege eller domstolen.

* Personstatusen død benyttes om personer med enten fødsels- eller d-nummer som er registrert døde i Folkeregisteret.
* Personstatusen død kan beskrives som en «sluttstatus», som innebærer at det kun gjøres korrigeringer og ikke vil gjøres nye endringer på personen i folkeregisteret for annet enn kontaktinformasjon for dødsbo etter endringene i forbindelse med dødsfallet
* Personer som vil få personstatus død (enten eller):
  - Personer med fødsels- eller d-nummer som dør i Norge, meldt av lege
  - Personer med fødsels- eller d-nummer som erklæres døde ved dødskjennelse fra Tingretten (dødsformodningsdom)
  - Personer som dør i utlandet, som meldes fra utenriksstasjonene

###### Opphørt
Registreringsstatus i Folkeregisteret for personinformasjon som ikke korresponderer med en fysisk person.

* Personstatusen opphørt benyttes om personer som er tildelt personidentifikator i folkeregisteret, hvor persondokumentet ikke lenger er gyldig for en person. Dette vil være tilfelle for personer hvor man i etterkant finner ut at en opprettelse av en folkeregisterperson ikke skulle vært gjennomført.
* Personstatusen opphørt signaliserer at identiteten i Folkeregisteret ikke representerer en person med en tilknytning til samfunnet, og er å anse som en «sluttstatus» på lik linje med død.
* Personer som vil få personstatus opphørt:
  - Falsk identitet
  - Annullert fødsel
  - Annullert tildeling av d-nummer
  - Annullert tildeling av fødselsnummer

###### Fødselsregistrert
Registreringsstatus i Folkeregisteret for en person som er født i Norge, men som ikke oppfyller kravene til å oppnå registreringsstatus bosatt.

* Personstatusen fødselsregistrert benyttes om personer som er født i Norge, og oppfyller kravet til tildeling av fødselsnummer, men som ikke skal registreres som bosatt.
* Denne statuskoden bygger på at Folkeregisteret er det offisielle fødselsregister i Norge og derfor kan utstede fødselsattester med sikker notoritet for denne gruppen


###### Midlertidig
Registreringsstatus i Folkeregisteret for en person med d-nummer som har eller har hatt en midlertidig tilknytning til Norge og som kan eller har kunnet oppholde seg lovlig i landet i opptil seks måneder per opphold.

* Personstatusen midlertidig benyttes for personer som er tildelt d-nummer, og som er å regne som aktive i det norske samfunnet. 
* Personer som vil få personstatus midlertidig:
  - Person som er tildelt d-nummer frem til gyldighetsperioden på 5 år utløper
  - Personer med reaktivert d-nummer som følge av forespørsel fra rekvirent

###### Inaktiv
Registreringsstatus i Folkeregisteret for en person med d-nummer som har vært inaktiv i en regelbestemt tid.

* Personstatusen inaktiv benyttes for personer som er tildelt d-nummer, og som er å regne som inaktive i det norske samfunnet. Det vil si at det ikke er registrert noen aktivitet. (Ikke registrert noen aktivitet hos Skatteetaten mht. inntekt, endringer i Folkeregisteret osv.)


###### Ikke Bosatt
Registreringsstatus i Folkeregisteret for en person som ikke er offisielt bosatt i Norge.

* Personstatusen ikkeBosatt benyttes for norske statsborgere som har behov for fødselsnummer, men som ikke er bosatt i Norge.
* Person som vil få personstatus ikkeBosatt:
  - Norsk borger født i Norge og utflyttet før 1.10.1964 eller norsk borger født i utlandet og som aldri har vært bosatt i Norge
  -Personer som har fått annullert sin innflytting (innvandring)

###### Aktiv
Oppgitt personstatus fra Folkeregisteret til konsumenter uten hjemmel til taushetsbelagt informasjon for personer med personstatus forsvunnet, fødselsregistrert, midlertidig og ikkeBosatt.

* Personstatusen aktiv er en status som ikke finnes lagret i Registeret, men som gis til konsumenter uten rettighet til taushetsbelagt personstatus.


##### TPS
I TPS ble det gjort flere modifiseringer på dataen de får fra Folkeregisteret som ikke blir videreført i PDL.
1. Modifisering av Folkeregisterpersonstatus på bakgrunn av saksbehandling i NAV. F.eks: Person blir meldt død i NAV, får personstatus død. Dette blir ikke videreført. Se på dødsfall.
2. Modifisering av gyldighetstidspunktet til å sammenfalle med tidspunkt i virkeligheten. F.eks: Person dør 19.01.2019, saksbehandling skjer 21.01.2019, NAV modifiserer gyldighetstidspunktet på personstatus død til å være 19.01.2019. Dette blir ikke videreført. Skal man vite dødsdato, se på dødsfall.
3. Spærre på oppslag mot opphørte personer. Personer som hadde personstatus opphørt kastet feilmelding fra TPS og var dermed ikke mulig å få tilbake, i PDL vil disse bli returnert.

Overgang fra TPS til PDL på kodeverk:

| TPS                                        | PDL / Folkeregisteret | Beskrivelse                                                                                      |
|--------------------------------------------|-----------------------|--------------------------------------------------------------------------------------------------|
| BOSA                                       | bosatt                |                                                                                                  |
| DØD                                        | doed                  |                                                                                                  |
| DØDD (Død Dnr)                             | doed                  |                                                                                                  |
| UTPE                                       | opphoert              |                                                                                                  |
| ADNR                                       | inaktiv               |                                                                                                  |
| ADNR                                       | midlertidig           |                                                                                                  |
| FOSV                                       | forsvunnet            |                                                                                                  |
| UTVA                                       | utflyttet             |                                                                                                  |
| UREG                                       | ikke_bosatt           |                                                                                                  |
| UTAN (Utgått person annullert tilgang fnr) | ikke_bosatt           |                                                                                                  |
| FØDR                                       | foedselsregistrert    |                                                                                                  |
| ABNR (Aktivt bostnr)                       | utgår                 | Bost er ikke noe som ligger i Folkeregisteret og vil derfor ikke ha en folkeregisterpersonstatus |
| UFUL                                       | utgår                 |                                                                                                  |

#### Spesiell informasjon

###### Dnummer personer
D.nr. vil i folkeregisteret ha to forskjellige statuser fremover: midlertidig og inaktiv. Det er ikke besluttet enda hvordan NAV kan nyttiggjøre seg dette.

#### Master og kilder

FREG er master.

#### Historikk

Folkeregisteret har ikke migrert inn historikk på Folkeregisterpersonstatus. Dette er pga for dårlig datakvalitet.
Historikk vil komme på nyopprettede personstatuser.

PDL-Api eksponerer den historikken vi har dersom det er ønsket. Dette kan styres via et flagg i spørringen.
Regelen for utledelse av gjeldende verdi er slik:
Sorter på `folkeregistermetadata.gyldighetstidspunkt`, plukk den siste (altså høyeste dato) (null first). Det vil ikke forekomme noe opphørstidspunkt på denne opplysningen ettersom opphør er en egen personstatus.
Det er alltids en annen som overtar for den forrige personstatusen.

OBS OBS: Folkeregisteret har ofte satt `null` (uspesifisert) start-tidspunkt på de opplysningene de har migrert inn ettersom de ikke vet hva gyldighetstidspunktet er. 

Visuelt eksempel:
```
---1--->
                 |---3--->
        |---2--->

Sortert:
---1--->|---2--->|---3--->
```
1. `folkeregistermetadata.gyldighetstidspunkt = null`
2. `folkeregistermetadata.gyldighetstidspunkt = 2019-01-23`
3. `folkeregistermetadata.gyldighetstidspunkt = 2019-11-30`

Dersom man spesifiserer `historikk: false` i grensesnittet, vil kun nr 3 blir returnert.

### Informasjonselementer
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
      <th scope="row">Status</th>
      <td>verdier: bosatt, utflyttet, død, D.nr. midlertidig, D.nr. inaktiv, forsvunnet, ikke bosatt, fødselsregistrert, opphørt </td>
      <td></td>
      <td>Obligatorisk</td>
      <td>God på nye, ingen historikk</td>
    </tr>
    <tr>
      <th scope="row">ForenkletStatus</th>
      <td>Forenklet folkeregisterpersonstatus ettersom flere av statusene etter gjennomgang med fagsidene ikke gir stor mening i NAV. Vi tilbyr begge, men forenklet status er mer knyttet mot fellesbehovene i NAV.</td>
      <td>Se mappingtabell lengre ned</td>
      <td>Obligatorisk</td>
      <td>God.</td>
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
          <td>Valgfri</td>
        </tr>
        <tr>
          <th scope="row">Gyldighetstidspunkt</th>
          <td>Når denne Folkeregisterpersonstatusen er gyldig fra og med</td>
          <td>Valgfri. Migrert kan ha `null` (uspesifisert), nye vil ha tidspunkt</td>
        </tr>
        <tr>
          <th scope="row">Opphoerstidspunkt</th>
          <td>Vil aldri forekomme på Folkeregisterpersonstatus</td>
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

##### Mapping mellom Status og Forenklet status

| Status                                     | Forenklet                      |
|--------------------------------------------|--------------------------------|
| bosatt                                     | bosattEtterFolkeregisterloven  |
| utflyttet                                  | ikkeBosatt                     |
| forsvunnet                                 | forsvunnet                     |
| doed                                       | doedIFolkeregisteret           |
| opphoert                                   | opphoert                       |
| foedselsregistrert                         | ikkeBosatt                     |
| midlertidig                                | dNummer                        |
| inaktiv                                    | dNummer                        |


#### Filtrering fra Folkeregisteret (I mottak inn i NAV)
Når vi får personstatus fra Folkeregisteret, så skjer det ved svært skjeldne tilfeller (hittil 12) at de saksbehandler et opphør, for så å rette dette opp samme dag uten å slette opphørsstatusen.
Dvs at personen ender opp med f.eks: 
```
|-- Bosatt -->
              |-- Opphoert -->
              |-- Bosatt   --> (gjeldende)
```
I disse tilfellene vil PDL filtrere bort Opphoert ettersom det i neste runde blir vanskelig å finne ut hvilke personstatus som skal legges til grunn.
F.eks:
```
|-- Bosatt -->
              |-- Opphoert -->
              |-- Bosatt   -->
                             |-- Død --> (gjeldende)
```
I dette tilfellet har vi ikke gjeldende flagget fra folkeregisteret til å hjelpe oss med å velge hvilke av opphoert og bosatt vi skal ta inn. Dermed beholder PDL den SISTE på samme gyldighetstidspunkt.
Så i PDL blir det da:
```
|-- Bosatt -->
             |-- Bosatt   -->
                            |-- Død -->
```