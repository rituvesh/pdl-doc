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
Fødselsopplysninger fra Folkeregisteret. Det vil på et hvert tidspunkt kun være en forekomst av fødsel fra Folkeregisteret.
Dvs at alle endringer er korrigeringer.

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
