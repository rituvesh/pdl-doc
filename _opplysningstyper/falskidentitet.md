---
navn: Falsk Identitet
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: Er tilgjengelig
---
#### Beskrivelse

Identitet som tilhører en annen enn den som benytter den, eller ikke tilhører noen i det hele tatt, men presenteres som om den er reell.

#### Spesiell informasjon

Når det foreligger gyldig vedtak/dom om at en identifikator er bygd på uriktige opplysninger og identifikatoren skal opphøres fra folkeregisteret.
Identifikatorer som er merket med Falsk ID vil automatisk også ha personstatus opphørt.

#### Master og kilder

FREG er master.

#### Historikk

Nei, anses som en sluttstatus.

#### Informasjonselementer

En av `rettIdentitetVedOpplysninger`, `rettIdentitetVedIdentifikasjonsnummer` eller `rettIdentitetErUkjent` må være utfylt.


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
      <th scope="row">erFalsk</th>
      <td>Ukjent, alltids true i data vi har sett fra produksjon</td>
      <td>true</td>
      <td>Obligatorisk</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Rett identitet ved opplysninger</th>
      <td>navn, fødselsdato og statsborgerskap</td>
      <td></td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Rett identitet ved identifikasjonsnummer</th>
      <td>f.nr. eller d.nr.</td>
      <td></td>
      <td>Valgfri</td>
      <td>God</td>
    </tr>
    <tr>
      <th scope="row">Rett identitet er ukjent</th>
      <td></td>
      <td></td>
      <td>Obligatorisk dersom rett identitet ved opplysninger/id-nummer ikke er fylt ut</td>
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

