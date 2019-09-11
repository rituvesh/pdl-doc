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

##### TPS
I TPS ble det gjort flere modifiseringer på dataen de får fra Folkeregisteret som ikke blir videreført i PDL.
1. Person blir meldt død i NAV, får personstatus død. Dette blir ikke videreført. Se på dødsfall.
2. Person dør 19.01.2019, saksbehandling skjer 21.01.2019, NAV modifiserer gyldighetstidspunktet på personstatus død til å være 19.01.2019. Dette blir ikke videreført. Skal man vite dødsdato, se på dødsfall.

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
| UTAN (Utgått person annullert tilgang fnr) | ikke_bosatt)          |                                                                                                  |
| FØDR                                       | foedselsregistrert    |                                                                                                  |
| ABNR (Aktivt bostnr)                       | UTGÅR                 | Bost er ikke noe som ligger i Folkeregisteret og vil derfor ikke ha en folkeregisterpersonstatus |
| UFUL                                       | UTGÅR                 |                                                                                                  |

#### Spesiell informasjon

D.nr. vil i folkeregisteret ha to forskjellige statuser fremover: midlertidig og inaktiv. Det er ikke besluttet enda hvordan NAV kan nyttiggjøre seg dette. 

Begrepet utvandret er erstattet med utflytting.  

#### Master og kilder

FREG er master.

#### Historikk

##### Må analyseres.
Folkeregisteret har ikke migrert inn historikk på Folkeregisterpersonstatus. Dette er pga for dårlig datakvalitet.
Historikk vil komme på nyopprettede personstatuser.

### Todo: Oppdateres når Personstatus blir eksponert på grensesnitt 
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
      <th scope="row">Personstatus</th>
      <td>verdier: bosatt, utflyttet, død, D.nr. midlertidig, D.nr. inaktiv, forsvunnet, ikke bosatt, fødselsregistrert, opphørt </td>
      <td></td>
      <td>Obligatorisk</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">kilde</th>
      <td>FREGs kilde</td>
      <td></td>
      <td>Valgfri</td>
      <td></td>
    </tr>
    <tr>
      <th scope="row">gyldighetstidspunkt i FREG</th>
      <td></td>
      <td></td>
      <td>Valgfri</td>
      <td></td>
    </tr>
      <tr>
      <th scope="row">ajourholdstidspunkt i FREG</th>
      <td></td>
      <td></td>
      <td>Valgfri</td>
      <td></td>
    </tr>
    </tbody>
</table>

#### Filtrering
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