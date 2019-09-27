---
navn: Kontaktinformasjon for dødsbo
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: april 2019
---

#### Beskrivelse

Kontaktpersonen er en person, organisasjon eller advokat, og er den som tingretten sender original skifteattest til. Mottaker av
skifteattesten er informert om at hun/han er oppført som kontaktperson for dødsboet i folkeregisteret. 
Kontaktinformasjon for dødsbo inneholder enten en person (via identifikasjonsnummer eller fødselsdato + navn), en advokat eller en organisasjon. En av disse vil alltids være til stede.

#### Spesiell informasjon

Kontaktinformasjon dødsbo foreligger når skifteattesten er utstedt fra Tingretten. NAV kan bruke informasjonen for kontakt med dødsboet, 
og den kan da erstatte c/o adresser o.a. som må brukes når det ikke er noen kontaktinformasjon tilgjengelig.

#### Master og kilder

Opplysningen kommer kun fra Folkeregisteret og kan ikke ajourholdes av NAV.
Folkeregisterets kilder vil kunne være: tingretten, og pårørende ved endringer av informasjon.

#### Historikk

Eksponert via PDL-Api. Dersom behovet er å kun vise den gjeldende, er regelen for å finne den som følgende:
Sorter på `gyldigFraOgMed`, plukk den siste (altså høyeste dato), så sjekk om denne har en `gyldigTilOgMed` (Opphørstidspunkt).

#### Datakvalitet
**Utenlandske adresser**

Det er tilfeller av kontaktinformasjon for dødsbo med utenlandsk adresse hvor adressefeltene blir vist feil. F.eks. ved at hele adressen kommer på adresselinje 1. 

**Ukjent gateadresse**

«UKJENT GATEADRESSE» står oppført i adresselinje-feltet selv når kontaktperson bor på et sted som ikke har gateadresse. Dette betyr ikke nødvendigvis at den er ukjent, det er mulig at det er ingen gateadresse der vedkommende bor. 


#### Informasjonselementer
Note: Man må ha en av: Person som kontakt, advokat som kontakt eller organisasjon som kontakt.

<table class="table">
  <thead>
    <tr>
      <th>Informasjonselement</th>
      <th>Beskrivelse</th>
      <th>Kodeverdier</th>
      <th>Kompletthet</th>
      <th>Kvalitet</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <th scope="row">Skifteform</th>
      <td>Fra Tingretten angis skifteformen for booppgjøret.</td>
      <td>offentlig, annet</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Attestutstedelsesdato</th>
      <td>Attestutstedelsesdato for skifteattest</td>
      <td>dato</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Person som kontakt</th>
      <td>Dersom en person er kontakt, benyttes denne</td>
      <td>n/a (Se definisjon lengre ned)</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Avokat som kontakt</th>
      <td>Dersom en advokat er kontakt, benyttes denne</td>
      <td>n/a (Se definisjon lengre ned)</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Organisasjon som kontakt</th>
      <td>Dersom en organisasjon er kontakt, benyttes denne</td>
      <td>n/a (Se definisjon lengre ned)</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Adresse</th>
      <td>Kontaktadresse i Norge eller utlandet for person, advokat eller oganisasjon</td>
      <td>n/a (Se definisjon lengre ned)</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">GyldigFraOgMed</th>
      <td>Tidspunktet opplysningen gjelder ifra. Denne er hentet fra Folkeregisteret sitt gyldighetstidspunkt.</td>
      <td>2019-11-23T12:34:59</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">GyldigTilOgMed</th>
      <td>Tidspunktet opplysningen gjelder til. Denne er hentet fra Folkeregisteret sitt opphoerstidspunkt.</td>
      <td>2019-11-30T14:24:39</td>
      <td>Valgfri</td>
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

##### Person som kontakt

Det er en privatperson som er kontaktperson og entiteten inneholder enten en identifikator (fødsel- eller d-nummer) eller identifiserende informasjon som fødselsdato og navn.
Eksempel på der hvor navn blir benyttet navn i stede for identifikator er utenlandske personer.

<table class="table">
  <thead>
    <tr>
      <th>Informasjonselement</th>
      <th>Beskrivelse</th>
      <th>Kodeverdier</th>
      <th>Kompletthet</th>
      <th>Kvalitet</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <th scope="row">Fødselsdato</th>
      <td>Fødselsdato på person som kontakt. Ikke påkrevd selv når det er en person uten identifikasjonsnummer</td>
      <td>2019-11-30</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Personnavn</th>
      <td>Inneholder fornavn (påkrevd), mellomnavn (valgfri) og etternavn (påkrevd)</td>
      <td></td>
      <td>Obligatorisk dersom person ikke har identifikasjonsnummer</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Identifikasjonsnummer</th>
      <td>Fødsel- eller d-nummer på personen</td>
      <td>291185xxxxx</td>
      <td>Obligatorisk dersom person har Identifikasjonsnummer</td>
      <td>God</td>
    </tr>
  </tbody>
</table>

##### Advokat som kontakt

Person som ervervsmessig yter rettshjelp, og som kan opptre i retten på vegne av sine klienter.
Det er et norskt eller utenlandsk advokatkontor som er bobestyrer.

<table class="table">
  <thead>
    <tr>
      <th>Informasjonselement</th>
      <th>Beskrivelse</th>
      <th>Kodeverdier</th>
      <th>Kompletthet</th>
      <th>Kvalitet</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <th scope="row">Personnavn</th>
      <td>Inneholder fornavn (påkrevd), mellomnavn (valgfri) og etternavn (påkrevd)</td>
      <td></td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Organisasjonsnavn</th>
      <td>Navnet til organisasjonen. Det kan være en utenlandsk organisasjon</td>
      <td>Testify Advokatfirma AS</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Organisasjonsnummer</th>
      <td>Organisasjonsnummeret til den norske organisasjonen, ikke utfylt på utenlandske organisasjoner</td>
      <td>123456789</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
  </tbody>
</table>

##### Organisasjon som kontakt

Norsk eller utenlandsk organisasjon som tar hånd om boet.

<table class="table">
  <thead>
    <tr>
      <th>Informasjonselement</th>
      <th>Beskrivelse</th>
      <th>Kodeverdier</th>
      <th>Kompletthet</th>
      <th>Kvalitet</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <th scope="row">Kontaktperson</th>
      <td>Inneholder fornavn (påkrevd), mellomnavn (valgfri) og etternavn (påkrevd)</td>
      <td></td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Organisasjonsnavn</th>
      <td>Navnet til organisasjonen. Det kan være en utenlandsk organisasjon</td>
      <td>Test Pinsemenighet</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Organisasjonsnummer</th>
      <td>Organisasjonsnummeret til den norske organisasjonen, ikke utfylt på utenlandske organisasjoner</td>
      <td>123456789</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
  </tbody>
</table>

##### Adresse

Kontaktadresse i Norge eller utlandet for person, advokat eller organisasjon.
Formatet er slik det lagres hos Domstolsadministrasjonen.
Adresselinjene inneholder fritekst fordelt på maksimum to linjer.

<table class="table">
  <thead>
    <tr>
      <th>Informasjonselement</th>
      <th>Beskrivelse</th>
      <th>Kodeverdier</th>
      <th>Kompletthet</th>
      <th>Kvalitet</th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <th scope="row">Adresselinje1</th>
      <td>Fritekstfelt for adresse</td>
      <td>Emigrantgata 123</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Adresselinje2</th>
      <td>Fritekstfelt for adresse</td>
      <td></td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Poststedsnavn</th>
      <td>F.eks by</td>
      <td>VETLANDA</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Postnummer</th>
      <td>Postnummeret</td>
      <td>57432</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Landkode</th>
      <td>Postnummeret</td>
      <td>SWE</td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
  </tbody>
</table>