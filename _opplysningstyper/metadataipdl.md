---
navn: Metadata
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: N/A
---

#### Beskrivelse
Alle opplysninger vi mottar har en god del metadata som kan benyttes til å gi mer kontekst til opplysningen.
Når vi eksponerer noe via PDL-Api, så vil alle opplysninger som PDL har lagret internt inneholde en metadatablokk.

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
        <th scope="row">opplysningsId</th>
        <td>En unik referanse til denne forekomsten av en opplysning. Dersom opplysningen kan endres, brukes denne mot Person-Mottak. Merk at denne id'en ikke er statisk og vil endre seg ved f.eks korrigeringer</td>
        <td>09c92bac-7a06-434f -b6f2-0862a6500e9a</td>
        <td>Ikke påkrevd, dette skjer når vi ikke har lagret opplysningen i PDL, men gjør et kall til andre systemer. Dette vil være dokumentert på opplysningstypen</td>
      </tr>
      <tr>
        <th scope="row">master</th>
        <td>Hvem som eier opplysningen. F.eks hvis vi får et navn med master FREG, så kan endringer KUN gjøres via Folkeregisteret. NAV kan ikke modifisere disse direkte og må i så fall gå via integrasjoner i Folkeregisteret</td>
        <td>FREG / NAV (Kan komme flere)</td>
        <td>Påkrevd. Vi vil informere om hvor opplysningen kommer fra. I dag er det i FREG og NAV, men f.eks kunne man ha utvidet med UDI og KRR dersom vi hadde tatt inn opplysnigner derifra</td>
      </tr>
      <tr>
        <th scope="row">endringer</th>
        <td>Endringer er en liste over utførte endringer på en opplysningstype. Beskrivelse av opplysningen er lengre ned</td>
        <td></td>
        <td></td>
      </tr>
    </tbody>
</table>


##### Endring
En endring er en endring som er utført på en forekomst av en opplysning. F.eks: `Opprett`, `korriger`, `opphør`, `annuller`.
Denne entiteten innkapsulerer metadataen vi har om endringen som er utført.

Tidligere fra TPS har man typisk fått endringstidspunkt, der dette blir den siste endringen. I PDL vil man få ut alle endringer over tid på en forekomst av en opplysning.

F.eks: Dersom man ønsker å presentere opprettet tidspunktet og sist endring (som blir gjort i flere saksbehandlingssystemer i dag), så vil man hente den først endringen i tid og den siste endringen.


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
        <th scope="row">type</th>
        <td>Hvilke type endring som ble utført</td>
        <td>OPPRETT</td>
        <td>Påkrevd</td>
      </tr>
      <tr>
        <th scope="row">registrert</th>
        <td>Tidspunktet endringen ble registrert</td>
        <td>2019-01-01T12:43:59</td>
        <td>Påkrevd</td>
      </tr>
      <tr>
        <th scope="row">registrertAv</th>
        <td>Ident for hvem som har utført endringen. Kan være saksbehandler ident, systembruker eller Folkeregisteret per nå</td>
        <td>Folkeregisteret / Z990200 / srvPerson-E500</td>
        <td>Påkrevd</td>
      </tr>
      <tr>
        <th scope="row">systemKilde</th>
        <td>Hvilke system endringen har kommet via</td>
        <td>FREG / srvPerson-forvalter / srvPerson-E500</td>
        <td>Påkrevd</td>
      </tr>
      <tr>
        <th scope="row">kilde</th>
        <td>Kilden for opplysningen. Når det er NAV som er Master, så er det påkrevd å oppgi kilden, men Folkeregisteret gir oss kun hvilke etat det kom fra (f.eks NAV, UDI)</td>
        <td>NAV / UDI / FREG (dersom vi ikke får noe fra Folkeregisteret) / Krankenkasse / Sykehuskassan</td>
        <td>Påkrevd</td>
      </tr>
    </tbody>
</table>