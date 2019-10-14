---
navn: Dødsfall
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: februar 2020
---

#### Beskrivelse

Opplysninger knyttet mot dødsfall.

#### Spesiell informasjon

*Obs obs! Vi vil etterhvert utvide med Dødsfall fra NAV*
Det vil si at man potensielt få tilbake 2 Dødsfall i oppslaget. Dersom dere kun vil ha Folkeregisteret sitt, så må dere filtrere på `metadata.master: "FREG"`.

#### Master og kilder

Folkeregisteret er master  
PDL er master for personkrets D.nr. og utvandret som FREG ikke godtar. (Under analyse).  
Dersom behovet er å benytte Folkeregisteret sine opplysninger om død må dere filtrere på master = FREG.

Mulige kilder Folkeregisteret: tingretten, legen, norsk utenriksstasjon  
Mulige kilder PDL: E500, utenlandske trygdemyndigheter

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
        <th scope="row">Dødsdato</th>
        <td>Dato der personen døde</td>
        <td>2019-11-20</td>
        <td>Ikke obligatorisk men vil som regel være oppført. Per skrivende stund, er det 1700~ personer fra Folkeregisteret der hvor dødsdato IKKE er satt.</td>
        <td>God</td>
      </tr>
    </tbody>
</table>
