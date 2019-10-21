---

---

#### Generelt

Persondataløsningen (PDL) er et register med forskjellige tjenester som til sammen skal dekke NAVs behov for grunnleggende personopplysninger. Løsningen leveres av MFN-prosjektet, og skal erstatte dagens TPS-løsning.

PDL vil løpende ta i mot personopplysninger fra flere kilder (i sanntid), deriblant nytt folkeregister hos Skatteetaten - Freg. Dette blir en forbedring sammenlignet med TPS, som blir oppdatert daglig via nattlig ajourholdsfil fra DSF (Det Sentrale Folkeregisteret). PDL vil i tillegg ivareta NAVs ansvar for oppdatere Folkeregisteret.

PDL vil i en periode eksistere i paralell med TPS. Det vil gjennomføres et eget migreringsløp for å få alle NAVs systemer over fra TPS til PDL. Dette arbeidet vil i hovedsak skje i 2020 og 2021. 

#### Konseptet Master. Paralell sannhet
PDL innfører begrepet Master. Alle opplysningstyper vil registreres med en master under `metadata`. Masteren angir hvor opplysningen kommer ifra og hvor man eventuelt må gå for å få den endret.

I motsetning til i TPS, vil PDL aldri tilby overskriving av opplysninger fra andre mastre direkte, f.eks. Folkeregisteret. NAV kan legge til egne opplysninger, men disse vil da registres med PDL som master. Dersom man ønsker å få oppdatert opplysninger som ligger i en annen master enn PDL, må dette gå igjennom den masteren sin rutine for oppdatering av opplysninger.

Det er noen opplysninger Folkeregisteret gjerne vil ha fra NAV, dette inkluderer blant annet Dødsfall. Dette vil PDL sende over til Folkeregisteret og dette kan da komme tilbake som et dødsfall fra Folkeregisteret.
Men i dette tilfellet, så vil vi også registrere et Dødsfall i NAV ettersom vi ikke har noen garanti for at Folkeregisteret tar hensyn til informasjonen vi gir dem. Dersom de tar det inn, vil hendelsesforløpet være noe ala:
2019-01-20: Registrert død i NAV
2019-02-04: Registrert død i Folkeregisteret basert på informasjon fra NAV
Her ender vi opp med at vi har 2 dødsfall i PDL, ett som kom 2019-01-20 der hvor PDL er master og ett fra 2019-02-04 fra Folkeregisteret. Begge kan ha samme dødsdato.
Dette kaller vi i PDL Paralell sannhet og er i hovedsak noe vi prøver å unngå, men det vil forekomme.

#### PDL / TPS

##### Et register
PDL har noen grunnleggende forskjeller fra TPS. TPS tar inn data, maserer den, endrer og tilgjengeliggjøre endret data som er skreddersydd for NAV sine behov. 
Dette har ført til at man i TPS har en god del tjenester som fungerer forskjellig, akkurat for å tilfredsstille forskjellige behov.
PDL sin tilnærming er å være et mye mer registerbasert system, at vi ikke skreddersyr dataen vi mottar, men at vi heller analyserer dataen og tilgjengeliggjør det vi slik at konsumentene selv kan benytte dataen slik de selv ønsker.

Eksempel: Ved flytting, får vi 3 forskjellige datoer fra Folkeregisteret (DSF også). TPS, basert på forretningsregler valgte TPS en av de og eksponerte den ene til konsumenten uten å si noe om hvilke som ble valgt.

Dette gjør vi ikke i PDL. I PDL vil vi heller eksponere alle 3 datoene pluss forklare hvilke regler som ble kjørt i TPS dersom man ønsker den samme verdien. PDL skal stå for et godt faktagrunnlag, men konsumentene der ute skal selv kunne bestemme bruken basert på deres behov.
Det vil også si at vi som løsning ikke kan fikse på dataen dersom vi får dårlig data. PDL sitt argument da er at det å eksponere data med noe mangler kan være nyttig (der konsumentene nå kan selv se at her er det noen mangler) enn at vi skal prøve å gjøre dataen bedre.
PDL må dermed analysere og dokumentere eventuelle avvik/kvalitetsbrister som følger med en opplysningstype (f.eks har man alltids gyldighetstidspunkt på navn? hvis ikke, hvordan kan det brukes?).

##### Flere kilder, flere verdier. Paralelle sannheter
TPS har i en årrekke stått for å lage en konsolidert sannhet om hvordan en bruker skal representeres. Denne konsoliderte sannheten blir lagd på bakgrunn av et stort sett med forretningsregler som har blitt formet over tid.
Eksempel: Får navnet Ola fra Folkeregisteret. NAV mener at personen heter Hans men Folkeregisteret vil ikke endre. For å få utbetalinger til å gå igjennom, har man endret navnet fra Ola til Hans. Nå heter personen Ola i Folkeregisteret, Hans i NAV.
Dette gjør ikke PDL, vi vil presentere begge disse sannhetene til konsumentene og dere må selv stå ansvarlig for hvilke verdier dere har lyst til å benytte. Reglene for TPS vil være dokumentert under opplysningstypen. Regelen i eksemplet over er at TPS velger det siste navnet (basert på registreringstidspunkt).

Visualisert:
```
Folkeregisteret:
---- Ola Nordmann ---->
                      |---- Ola Svenske ---->

NAV:
                          |---- Hans Nordmann ----->
```
For videre utredelse, les om `Konseptet Master` lengre opp.

##### Distribusjonsmeldinger
TPS tilbyr distribusjonsmeldinger via MQ. Dette tilbyr også PDL men via Apache Kafka.
TPS sine distrubjonsmeldinger er av den varianten som vi kaller "tykke", dvs at man får en Fødselsmelding som inneholder barn, mor, far.
Dette gjør ikke PDL. PDL vil tilby mer grannulerte meldinger som Fødsel opprettet, som KUN inneholder opplysninger rundt førsel, ikke relasjoner.  

Se lengre ned under `Livshendelser` for mer informasjon.

#### Historikk
TPS har i dag egne tjenester for å hente ut historikk. PDL vil tilby en filtreringsmulighet i tjenestene sine for å kun få ut gjeldende verdier. 
I eksemplet over med navn vil man da få tilbake `Ola Svenske` og `Hans Nordmann` ettersom de er gjeldende fra hver sin master.
PDL vil også forklare alle reglene som går inn i å utlede gjeldende verdier, så dersom man ønsker å gjøre dette selv, så kan dere benytte samme forretningsregler. 

##### Bruk av gyldighetstidspunkt
TPS og mange andre registre i NAV har til nå benyttet seg av begrepet `gyldigFom` (gyldigFraOgMed) og `gyldigTom` (gyldigTilOgMed). Noe av dette vil tildels fases ut. F.eks er det ikke alle opplysningstyper som har et opphørstidspunkt (disse får da ikke gyldigTom).

###### Gyldighetstidspunkt (GyldigFom)
Navn:
```
|--- Ola --->|--- Hans --->|--- Knut --->
```
Ett navn blir overtatt av et annet. Det er ikke noe gyldigTom på de forrige navnene. 
Denne formen vil gå igjen på mange opplysningstyper, blant annet: Navn, Sivilstand, Kontaktinformasjon for Dødsbo, m.m..

Noen opplysningstyper vil ha en annen form der hvor dataen viser til en sluttstatus. F.eks:
```
|--- Bosatt --->|--- Utvandret --->|--- Opphørt --->
```
Denne varianten finnes blant annet på Folkeregisterpersonstatus og Sivilstand. Du vil med andre ord alltids ha en "kategori/status".

###### Gyldighetstidspungt (GyldigFom) og Opphørstidspunkt (GyldigTom)
Statsborgerskap:
```
|--- SWE ------>
  |--- DNK -|
```
Her har man 2 forskjellige uavhengige opplysninger som løper. Det at man har et Svensk statsborgerskap påvirker ikke det Danske. Det Danske kan være utløpt mens Svenske enda er aktivt.

###### Kombinasjon: 
Adressebeskyttelse
```
|--- StrengtFortrolig --->
                         |--- Fortrolig ---|
```
Her er det en kombinasjon der hvor man har hatt StrengFortrolig (tidligere Kode 6), så fått Fortrolig som har blitt opphørt og man har ikke lengre noen adressebeskyttelse.

#### Tilgangskontroll
PDL har en noe annen tilgangskontroll enn hva man er vandt med i NAV sammenheng. Vi krever et token for hvem du er og et token som sier hvor du kommer ifra (systemtoken).
Dette er fordi vi baserer oss på noe vi kaller delegert tilgangskontroll. Vi har ikke kontroll på om saksbehandler har tilgang til ett og annet saksbehandlingssystem i NAV, så dermed krever vi systemtokenet for å håndheve at du faktisk har tilgang til et system i NAV.
Systemet blir også sjekket mot Tema og hjemmel. Hjemmel i denne forstand er en mapping mellom opplysningstype og hjemmel, der hvor hjemmel er koblet mot tema.

Dermed, for å hente informasjon fra PDL, så kreves følgende:
```
Authorization: Bearer [Token]
Nav-Consumer-Token: Bearer [Token] (systembruker)
Tema: GEN/PEN/o.l.. (NAV Tema)
```
Vi vil sjekke mot ABAC om systembrukeren har tilgang til Tema'et, f.eks srvPen har tilgang til tema PEN. Et tema er så knyttet opp mot flere opplysningstyper. F.eks tema PEN kan ha tilgang til navn, kjønn, fødsel, m.m., men kan mangle noen.
PDL begrenser ikke noe mer enn på opplysningstype nivå, så har man tilgang til Navn så kan man få alt under navn (data, metadata, o.l.).

#### Tjenester
PDL tilbyr noen forskjellige tjenester som konsumenter kan benytte for å hente data.

##### Oppslag
Direkte oppslag på identifikator (dnr, fnr, aktørId) via et GraphQL endepunkt. GraphQL tilbyr muligheten til å spesifisere helt ned på feltnivå hvilke informasjon man ønsker tilbake.
Vi anbefaler sterkt at dere prøver ut spørringer ved bruk av GraphiQL eller Altair, eventuelt nyere versjon av Postman som har støtte for GraphQL.
GraphQL fungerer slik at PDL-Api (vår tjeneste) tilgjengliggjøre et endepunkt. Dette endepunktet gir både skjema og data. For å hente ut data må dere autoriseres og autentiseres, men skjema kan alle hente.
URL: https://pdl-api.nais.adeo.no/graphql for prod eller https://pdl-api.nais.preprod.local/graphql for preprod.

Eksempel på spørring der man skal ha tilbake informasjon om navn.
Denne kan legges inn i f.eks Altair.
```
query($ident: ID!, $navnHistorikk: Boolean!){
  hentPerson(ident: $ident) {
	navn(historikk: $navnHistorikk) {
	  fornavn
	  mellomnavn
	  etternavn
	  forkortetNavn
	  originaltNavn {
	    fornavn
	    mellomnavn
	    etternavn
	  }
    }
  }
}
```

`Ident` og `navnHistorikk` er her satt som variabler. Disse må passeres inn i requesten.
```
{
    "query": "<graphQL query>",
    "variables": {
        "ident":"12345678910",
        "navnHistorikk: true
    }
}
```

GraphQL påkrever ikke bruk av variabler, men PDL ønsker STERKT at dette blir benyttet. 
Dette er fordi GraphQL må på hver request validere om alle feltene stemmer med skjema. Dette tar litt ekstra tid, men dersom man benytter variabler, så kan denne vurderingen bli cachet og brukt for raskere oppslag.


##### Søk
TBD.

##### Mottak av opplysninger
PDL har flere mottakskanaler for opplysninger fra verden rundt. En slik kanal er det vi kaller `freg-mottak`. Dette er mottakskanalen fra Folkeregisteret, men vi har også egne REST endepunkter for å opprette opplysninger der hvor PDL er master.
Dette skjer via Person-Mottak der hvor PDL står ansvarlig for å sende informasjonen til korrekte systemer i NAV. F.eks så blir dødsfall sendt til PDL, Folkeregisteret og TPS.

##### Livshendelser
PDL tilbyr hendelser i regi av personen via topicen `aapen-person-pdl-leesah-v1` (Leesah som i Livet Er En Strøm Av Hendelser). Denne topicen kan sammenlignes med dagens distribusjonsmeldinger fra TPS.
Topicen vil inneholde opplysninger på et relativt lavt nivå samtidig som vi ikke garanterer at de blir sendt ut i riktig rekkefølge. Dvs, dersom man vil ha få med seg at Mor har fått en relasjon til Barn, så ikke vent på relasjonsmelding fra barn til mor.
Vent på melding at mor har fått relasjon til barn. Vi vil sende ut for begge retninger.

##### Persondokument
PDL tilbyr en topic for alle persondokumenter på alle personer i Norge. 
Denne topicen blir som om man hadde gjort en spørring via PDL-Api på alle opplysninger og alle felt. Dette kan benyttes til å holde lokale caches av PDL oppdatert.
Merk at vi p.t. ikke har planer om å tilby en egen uten historikk, dvs at man selv må stå ansvarlig for å utlede gjeldede verdier dersom man ønsker å kun ha dette.
Vi stiller også en god del krav til hvordan dataen behandles, selv om det kun er fra system til system ettersom man får litt mer enn hva man potensielt har hjemmelsgrunnlag til å hente.

##### Person-Forvalter / Endre Person
PDL tilbyr en egen brukerflate for å oppdatere personopplysninger. Denne bruker Person-mottak på baksiden.

#### Test
PDL er i hovedsak kun i Q2 og har kun syntetiske / konstruerte personer som testgrunnlag. I tillegg har vi en populasjon fra Folkeregisteret som kan benyttes som tverretatelig testdata.
Dolly integrerer mot oss for å opprette opplysninger, men alt dette går via `Person-testdata`. Denne kan fint benyttes av andre dersom dere har lyst til å håndtere testdata selv, men vi vil gjerne være med i en dialog for hvordan dette benyttes.
