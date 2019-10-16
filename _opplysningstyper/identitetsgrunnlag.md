---
navn: Identitetsgrunnlag
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: desember 2019
---

#### Beskrivelse

Opplysninger som danner grunnlaget for, og tiltroen til, den identiteten som er registrert i Folkeregisteret.
Denne har ikke eksistert i Folkeregisteret før og mange personer vil derfor mangle denne egenskapen. Det vil i praksis bety at verdien er INGEN_STATUS.

PDL har ikke gått igjennom NAV sitt bruksbehov for denne opplysningen i detalj. Vi vil gjerne ha tilbakemelding dersom konsumenter tar denne i bruk.

##### Beskrivelse av statusene
###### Ingen Status
En status som viser at personens identitet hittil ikke har vært omfattet av offisielle kontrolltiltak i regi av Folkeregisteret eller utlendingsmyndighetene.

###### Ikke Kontrollert
En status som viser at personens identitet ikke er kontrollert ved personlig fremmøte for Skatteetaten eller utlendingsmyndighetene.
Personen har ikke møtt til identitetskontroll, men kopier av identifikasjonspapirer kan likevel være innsendt til folkeregistermyndigheten.

###### Kontrollert
En status som viser at personens identitet er kontrollert ved personlig fremmøte for Skatteetaten eller utlendingsmyndighetene med fremvisning av pass eller tilsvarende.
Identitetsgrunnlagsstatus kontrollert er satt etter gundig identitetskontroll hvor det er stadfestet samsvar mellom person og legitimasjonsdokument etter en taktisk og teknisk vurdering.


#### Master og kilder

Folkeregisteret.

#### Historikk

Ja, vi får historikk, men kun på nye personer ettersom dette er ny informasjon som ikke eksisterte i DSF.

PDL-Api eksponerer den historikken vi har dersom det er ønsket. Dette kan styres via et flagg i spørringen.
Regelen for utledelse av gjeldende verdi er slik:
Sorter på `folkeregistermetadata.gyldighetstidspunkt`, plukk den siste (altså høyeste dato). 

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
        <th scope="row">Status</th>
        <td>Status fra Folkeregisteret, se forskjellige statuser lengre opp under beskrivelse</td>
        <td></td>
        <td>Obligatorisk</td>
        <td>God</td>
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
        <tr>
          <th scope="row">Sekvens</th>
          <td>Ikke relevant</td>
          <td>Fraværende</td>
        </tr>
    </tbody>
</table>