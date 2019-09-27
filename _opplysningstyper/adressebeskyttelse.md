---
navn: Adressebeskyttelse
hendelser: nei
oppslag: ja
sok: nei
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: februar 2020
---


#### Beskrivelse

Informasjon om gradering av adresseinformasjon for personer iht. Beskyttelsesinstruksen.
Dette ble tidligere omtalt som Diskresjonskode 6 og 7 fra TPS.

Merk at man kan få tomt svar (dvs ingen Adressebeskyttelse) og Ugradert. Dette er slik vi får det fra Folkeregisteret, men vi har ingen tilfeller med Ugradert hittil i Produksjon.

#### Master og kilder

Folkeregisteret er eneste kilde og master til opplysningen for NAV.
  
#### Historikk

Vi får historikk fra Folkeregisteret og dette blir IKKE eksponert på grensesnittet i første omgang.
Det legges opp til at dette kan legges på ved senere anledning dersom behovet oppstår. 
Dersom dette blir innført senere, så settes en default på at konsumenter kun skal få ut gjeldende opplysninger (dvs ikke historikk) slik at det ikke feiler for eksisterende konsumenter.

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
          <th scope="row">Metadata</th>
          <td>Se felles definisjon</td>
          <td>n/a</td>
          <td>Valgfri</td>
          <td>God</td>
        </tr>
    </tbody>
</table>