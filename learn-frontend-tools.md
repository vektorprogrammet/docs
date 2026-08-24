# Lær frontend biblioteker og verktøy vi bruker i Vektorprogrammet

## Lær Tanstack Query

Tanstack query er biblioteket vi bruker for å la frontend snakke med backend.
Det er i essens limet som binder frontend sammen med backend.

### Fetch-kall

Det er viktig å forstå at det er fullt mulig å skrive en Javascript, Typescript
eller React-applikasjon som snakker med backend uten å bruke biblioteker i det hele
tatt.
Javascript har nemlig [Fetch API-en](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)
som alle kan bruke til å gjøre [HTTP-kall](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview)
til serveren.

### Hvorfor Tanstack Query?

> There are only two hard things in Computer Science: cache invalidation and
> naming things.
> *— Phil Karlton*

Et relevant spørsmål å stille er hvorfor vi trenger å bruke Tanstack Query dersom
man uten biblioteker kan gjøre kall til serveren.
Svaret ligger i at det å gjøre server-kall i seg selv ikke er veldig vanskelig.
Det som er vanskelig består av to deler:

- Organiserer koden som kaller på serveren
- Gjøre så få og så effektive kall som mulig

#### Organisering av kode

Når det kommer til programmering er det å organisere koden slik at den er lett
å forså, og har god struktur en vanskelig og tidkrevende oppgave.
Uten biblioteker må vi finne på denne organiseringen selv, som tar lang tid og
er en kjedelig oppgave.

Med biblioteker som Tanstack Query er det standarder vi kan velge følge som gjør
det lett å starte kodingen og holde den organisert for fremtiden.
Dermed kan vi fokusere på andre og mer interessante ting.

#### Effektive kall

Det å gjøre effektive kall til databasen krever at kallene minimerer to dimensjoner.
Den viktigste dimensjonen er antall server-kall.
Vi burde prøve å gjøre så få kall som mulig for å ikke overhvelme serveren.
Når du skriver server-kall er det viktig å tenke på at hver eneste bruker av nettsiden
vår kommer til å gjøre disse kallene til samme server.
Særlig i opptaksperioden kan dette bety at opptil tusen personer går inn på nettsiden
iløpet av en arbeidsdag.

Mindre viktig er størrelsen på server-kallene.
Det viktigste her er at man tenker på at det å hente ut alt for mye data kan føre
til at brukere som bruker mobildata får drenert all dataen de har den måneden kun
ved å gå inn på nettsiden vår.
Derfor bør du tenke deg om to ganger dersom du vurderer å hente 1000 bilder fra
serveren når du har tenkt å filtrere bort 990 av dem.

Tanstack Query hjelper oss med disse dimensjonene.

- caching, som begrenser antall server-kall
- gjentar kall som feilet flere ganger for å se om kallet denne gangen var gyldig
- oppdaterer data automatisk fra serveren

### Lær deg Tanstack Query ved hjelp av internett

OBS: Tanstack Query het før React Query, derfor vil mange på internett fortsatt
omtale biblioteket som det.

Det blir dumt om dokumentasjonen skal inneholde en hel masse dokumentasjon om hvordan
man bruker biblioteket.
Det finnes mange andre på internett som kan lære det bedre enn det går ann å skrive
her.
Bruk denne oversikten til å finne informasjon på nettet selv om hvordan tanstack
query fungerer.

Først og fremst har Tanstack Query en liste over offesielle community resources
som de anbefaler for å lære seg Tanstack Query.

- [Tanstack Querys offesielle community resources](https://tanstack.com/query/latest/docs/community-resources)

Tanstack Query har også offsesiell dokumentasjon, som kan være litt vanskelig å
finne frem i. Derfor har jeg samlet noen sider der det er nyttig å gå igjennom etterhvert.

- Se [Tanstack Query Guides](https://tanstack.com/query/latest/docs/framework/react/guides/important-defaults)
for å få informasjon om de forskjellige funksjonalitetene til Tanstack Query.
- Se [Tanstack Query API Reference](https://tanstack.com/query/latest/docs/reference/QueryClient)
for å se spesifikk teknisk kode-info.
- [Basic Tanstack Query example](https://tanstack.com/query/latest/docs/framework/react/examples/simple)

Youtube har også utrolig mange tutorials for å lære seg tanstack query.

- [React Query in 100 seconds](https://www.youtube.com/watch?v=1fUBWAETmkk&pp=ygUOdGFuc3RhY2sgcXVlcnk%3D)
- [Tanstack Query - How to become a React Query god](https://www.youtube.com/watch?v=mPaCnwpFvZY)

For deg som liker kort-format legger jeg ved to Youtube Shorts som forklarer noen
detaljer i Tanstack Query, kanskje du kan lure algoritmen til å lære deg mer. :D

- [Advanced React Query pattern](https://www.youtube.com/shorts/RR6R1NVkm5k?feature=share)
- [How to use React Query correctly](https://www.youtube.com/watch?v=0NU9aCTLopo)

Ikke minst er Tanstack Query åpen kildekode, og den finner du på Github.

- [Offesiell Github kildekode](https://github.com/TanStack/query)

### Våre Tanstack Query standarder

TODO: det kommer mer informasjon her når vi har landet på hvordan vi skal bruke
Tanstack Query i Vektorprogrammet.
