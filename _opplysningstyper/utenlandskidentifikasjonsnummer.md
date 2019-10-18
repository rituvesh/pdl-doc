---
navn: Utenlandsk Identifikasjonsnummer
hendelser: ja
oppslag: ja
sok: ja
produsent-freg: nei
produsent-nav: nei
tilgjengelig-fra: Er tilgjengelig
---

#### Beskrivelse

Identifikator utstedt av myndigheter i et annet land.

#### Spesiell informasjon

Med utenlandsk ID mener vi personidentifikasjonsnummer.
Saksnummer eller identifikasjonsdokumentnummer (passnummer) anses ikke som en utenlandsk ID.

Brukes for samhandling med utenlandske trygdemyndigheter, verifisering og identifisering.


#### Master og kilder

NAV og FREG som master.

Dersom NAV er master er utenlandske trygdemyndigheter kilde
Dersom FREG er master er kilden til FREG kilden (f.eks. skatteetaten, UDI).

#### Historikk

PDL-Api eksponerer historikk dersom det er ønsket. Dette kan styres via et flagg i spørringen.
Regelen for utledelse av gjeldende verdi er slik:
Er feltet `opphoert: true` så er det en historisk opplysning.


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
            <th scope="row">UtenlandskIdentifikasjonsnummer</th>
            <td>Identifikator utstedt av myndigheter i et annet land.</td>
            <td>123 010190B456</td>
            <td>Obligatorisk</td>
            <td>God dersom PDL er master, varierende når FREG er master</td>
        </tr>
        <tr>
            <th scope="row">Utstederland</th>
            <td>Land som har utstedt identifikasjonsnummeret, angis som landkode</td>
            <td>DEU</td>
            <td>Obligatorisk</td>
            <td>God dersom PDL er master, varierende når FREG er master</td>
        </tr>
        <tr>
            <th scope="row">Opphørt</th>
            <td>Informasjon om at en Utenlandsk ID ikke lengre er gyldig i utstederlandet</td>
            <td>Ja/nei</td>
            <td>Obligatorisk</td>
            <td>Det er sjelden at vi får informasjon om at en Utenlandsk ID ikke lengre er i bruk fra utstederlandet.</td>
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
