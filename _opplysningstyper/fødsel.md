---
navn: Fødsel
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: september 2019
---

#### Beskrivelse
Fødselsopplysninger fra Folkeregisteret. Det vil på et hvert tidspunkt kun være en forekomst av fødsel per person fra Folkeregisteret.
Dvs at alle endringer er korrigeringer.

##### TPS
TPS utleder i dag fødselsdato basert på fødselsnummer/dnummer. Dette har fungert i hovedsak greit, men Folkeregisteret har nå lagt opp til at man kan ha identer som har en annen fødselsdato enn det som står i identen.

Eksempel ved rekvirering av dnummer kan man spesifisere at fødselsdato er ukjent. 
Vi er påkrevd å sende inn en dato men da er praksisen slik at man setter rekvireringsdato. 
F.eks: 2019-09-19 (rekvireringsdato), men bytter ut år med fødselsår, altså fødselsår 1989 blir da: 1989-09-19. Dette fører til et dnummer som har fødselsdato 01-01-2019 (fra Folkeregisteret), men en ident som begynner med 590989. 
TPS vil da utlede fødselsdato til å være 19-09-1989.

Folkeregisteret har også lagt opp til at man fra dem kan få fødselsår, men IKKE fødselsdato. Dette er for å støtte caset over der man egentlig ikke vet dato.
Dette har begynt å bli tatt i bruk i Folkeregisteret og dermed også PDL, men vil ikke reflekteres i TPS.

Data som er migrert fra DSF til det nye Folkeregisteret og der fødselsdato egentlig er ukjent, vil ha dårlig kvalitet ettersom de setter fødselsdato basert på dnummeret.


#### Master og kilder

FREG er master  
PDL er master for personkrets D.nr. og utvandret som FREG ikke godtar. (Under analyse)

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
        <th scope="row">Fødselsdato</th>
        <td>Dato en person er født</td>
        <td>2019-11-20</td>
        <td>Valgfri</td>
        <td></td>
      </tr>
      <tr>
        <th scope="row">Fødselsår</th>
        <td>Årstall en person er født, vil alltids være utfylt fra Folkeregisteret, men kan forekomme NAV opplysninger der man f.eks kun har land + sted. Dvs hvis master = FREG, så vil alltids dette feltet være utfylt.</td>
        <td>2019</td>
        <td>Valgfri</td>
        <td></td>
      </tr>
      <tr>
        <th scope="row">Fødested</th>
        <td>Sted en person er født</td>
        <td>Oslo S.S</td>
        <td>Valgfri</td>
        <td></td>
      </tr>
      <tr>
        <th scope="row">Fødekommune</th>
        <td>Angis som kommunenummer (Kun angitt for fødeland Norge)</td>
        <td>0301</td>
        <td>Valgfri</td>
        <td></td>
      </tr>
      <tr>
        <th scope="row">Fødeland</th>
        <td>Angis som landkode</td>
        <td>NOR</td>
        <td>Valgfri</td>
        <td></td>
      </tr>
  </tbody>
</table>

#### Filtrering
Folkeregisteret har oppført i sin informasjonsmodell at det kun kan være en fødsel, men i tjenestekontrakten kan man få en liste og ved få tilfeller har man flere men kun en gjeldende.
Vi beholder kun den ene gjeldende fra Folkeregisteret og dersom man får et nytt innslag i Folkeregisteret, så fører det til en korrigering i NAV. Dette skjer ved svært få tilfeller. 
