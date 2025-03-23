# IPS_PI projekt: Sustav za praćenje osobnih financija

## Uvod

### Svrha

Ovaj dokument prezentira skup softverskih zahtjeva namjenjen razvoju
i validaciji softvera za praćenje osobnih financija. Zahtjevi su postavljeni 
djelomično od strane kolegija Programsko Inženjerstvo na Fakultetu Organizacije i Informatike,
koji određuju format solucije, a djelomično od strane studenta koji ima
slobodan izbor zahtjeva koje će obraditi u sklopu kolegija.

Ciljna skupina su osoblje fakulteta koji će ocjenjivati studentski rad, i
student koji će se referencirati na skup zahtjeva u budućim zadatcima koje
treba obaviti u sklopu kolegija. 

Struktura dokumenta se temlji na predlošku IEEE 830-1998
Recommended Practice for Software Requirements Specifications


### Opseg

U doba pisanja ovoga dokumenta problem koji je nastao u trenutnoj
Hrvatskoj ekonomiji, konkretno financijskoj situaciji pojedinca i obitelji
je značajna promjena cijena i omjera cijena određenih usluga i dobara. Uvođenje
EUR umijesto HRK je još jedan faktor koji doprinosi teškoćama pri subjektivnoj
procijeni vrijednodnosti dobara i usluga. 

Sustav za praćenje osobnih financija ( u daljnjem tekstu SPOF), riješenje opisano u ovom dokumentu, omogućuje
korisniku da prati prihode i rashode pojedinca ili kućanstva, te na taj način potiče
optimizaciju rashoda i osvješćivanje potrošnje po kategorijama.

SPOF podržava unos prihoda i rashoda kroz sučelje, te osnovnu statističku analizu
prihoda i rashoda po kategorijama.


### Definicije, akronimi i skraćenice

Termin | Objašnjenje
-|-
SPOF | Sustav za praćenje osobnih financija
PBZ | Privredna Banka Zagreb


### Reference 

Referencirajte sve dokumente, web stranice, standarde, druge
specifikacije koji se spominju u SRS-u.

### Struktura dokumenta

Ukratko opišite kako je ostatak dokumenta organiziran i što sadrži.

## Općeniti opis


### Perspektiva proizvoda

SPOF je software koji se može koristiti kao alternativa
izvoda bankovnih aplikacija gdje, u slučaju velikog broja transakcija,
korisnik vrlo teško može doći do relevantnih informacija o potrošnji.
U konkretnom slučaju PBZ aplikacije korisnik ima mogućnost pretrage pojedinih transakcija
i statistiku prihoda i rashoda na mjesečnoj bazi, ali aplikacija ne pruža 
mogućnost kategorizacije troškova ili dublje statističke analize.

SPOF je standalone softversko riješenje koje ne ovisi o direktnim integracijama
sa drugim softwareom, unos prihoda i rashoda ovisi isključivo o korisniku.

### Funkcije proizvoda

Funkcionalnosti SPOF aplikacije obuhvaćaju unos novčane vrijednosti i kategorije 
pojedinih prihoda i rashoda, pregled unesenih prihoda i rashoda, prikaz 
statistike prihoda i rashoda 


### Karakteristike korisnika

Identificirajte grupe/uloge korisnika za koje očekujemo da će koristiti
softversko rješenje (npr. nastavnik, profesor, administrator, blagajnica,
bankovni službenik, računovođa, …). Navedite opće karakteristike
identificiranih korisnika, navedite po čemu se oni razlikuju. To može
uključivati razinu obrazovanja, iskustva, računalne i tehničke pismenosti,
zatim predviđenu učestalost korištenja softverskog rješenja, razinu
dodijeljenih dozvola, skupa funkcija softvera kojeg će koristiti.

### Ograničenja

Navesti aspekte problemske domene i samog rješenja koji mogu
djelovati ograničavajuće na razvoj softverskog rješenja. To može
uključivati: zakonske i korporativne propise i regulative (npr. GDPR
odredbe, fiskalizacija, sigurnosne politike, i sl.); hardverska ograničenja
(npr. u razvoju za male uređaje – baterija, memorija, procesor,
mogućnost povezivanja, i sl.); potrebu za prilagodbom drugim sustavima
(npr. interakcija s postojećim i potencijalno zastarjelim sustavima);
sigurnosnu kritičnost aplikacije (npr. u slučaju da aplikacija upravlja
opasnim strojevima, medicinskim uređajima, ili radi sa osjetljivim i
povjerljivim podacima, i sl.); zahtjeve za pouzdanošću (npr. može biti
zahtijevano korištenje određenog pristupa, alata praksi i standarda u
programiranju, modeliranju i testiranju softverskog rješenja i sl.)

### Pretpostavke i ovisnost

Navedite pretpostavke i otvorena pitanja (za razliku od poznatih
činjenica) čiji naknadni ishod može utjecati na zahtjeve navedene u
ovom dokumentu. To su vrlo često okolnosti koje nisu pod našom
odgovornosti (npr. ako postoji vjerojatna mogućnost ili najava promjene
zakonske regulative koja će rezultirati modificiranjem definiranih
zahtjeva; ili izlazak nove verzije API-ja o kojem naš softver ovisi).

### Ostalo

Navedite ostale aspekte problemske domene i budućeg softverskog
rješenja koje smatrate bitnima a koji nisu predviđeni u ostalim dijelovima
dokumenta.

## Funkcionalni zahtjevi

Definirajte funkcionalne zahtjeve za softversko rješenja i to na način da
pružite dovoljno informacija dizajnerima i programerima da mogu
započeti sa osmišljavanjem i implementacijom rješenja, a testerima da
osmisle testne slučajeve. Zahtjevi navedeni ovdje se temelje na
funkcijama proizvoda opisanim u poglavlju 2.2., ali su opisani s višom
razinom detalja. Fokus je na funkciji i ograničenjima sustava. Svakom
zahtjevu treba dodijeliti jedinstven identifikator. Zahtjeve je moguće 
i grupirati po različitim kriterijima, kao npr. korisnicima (nastavnik,
student, blagajnik, administrator…), slučaju korištenja, domenskim
konceptima, i sl.
Za svaki zahtjev potrebno je ispuniti sljedeću tablicu:


Identifikator | Jedinstveni identifikator zahtjeva.
-|-
Zahtjev | Opis zahtjeva u obliku „Sustav će omogućiti <funkcionalnost> <objekt> uz <ograničenja>“. Stil pisanja treba biti ujednačen. Prilikom formulacije vodite se prihvaćenim smjernicama za definiranje zahtjeva, kao npr. onima navedenim u INCOSE Smjernicama za pisanje zahtjeva.
Obrazloženje | Obrazloženje zašto zahtjev postoji/zašto je potreban.
Način provjere | Kriterij provjere ili testni scenarij koji će omogućiti utvrđivanje je li zahtjev ispunjen ili nije.
Prioritet [1-5] | Prioritet zahtjeva (1 – najveći prioritet, 5 najmanji prioritet)
Izvor/Porijeklo | Naziv dokumenta kojim je zahtjev propisan ili dionika koji je podnio zahtjev.

### Dinamika realizacije zahtjeva

Navedite hoće li svi zahtjevi biti realizirani u inicijalnoj verziji softvera, ili
će neki biti ostavljeni za buduće verzija. Navedite ukoliko postoje još neki
zahtjevi koje se planira realizirati u budućnosti

## Nefunkcionalni zahtjevi

### Izgled softvera

Navedite zahtjeve (ukoliko postoje) koji su povezani s izgledom i
vizualnim stilom softvera. To može uključiti zahtjeve da se npr. koristi
formalan i korporativan stil (u slučaju poslovne aplikacije), ili zaigran stil
(npr. računalna igra za djecu); zahtjev za korištenjem konkretne palete
boja ili kontrola kako bi aplikacija bila u skladu s brendiranjem poduzeća
i sl.

### Upotrebljivost softvera

Navedite zahtjeve (ukoliko postoje) koji su povezani s lakoćom učenja i
korištenja softvera, prilagodbom za osobe s poteškoćama, lokalizacijom.
To može uključiti zahtjeve vezane uz krivulju učenja, brzinu korištenja
aplikacije (npr. brzina unosa podataka), lakoću pamćenja opcija softvera,
frekvenciju grešaka koje korisnik napravi u radu sa softverom,
mogućnost odabira jezika, mogućnost korištenja od strane slijepih osoba
i sl.

### Performanse softvera

Navedite zahtjeve (ukoliko postoje) koji su povezani s performansama
softvera. To može uključiti zahtjeve vezane uz brzinu procesiranja
zadataka, odziv, preciznost rezultata, kapacitet pohrane, skalabilnost,
dostupnost sustava i sl.

### Izvođenje softvera i okruženje

Navedite zahtjeve (ukoliko postoje) koji su povezani s izvođenjem
softvera i okruženjem u kojem se softver izvodi. To može uključivati
zahtjeve vezane uz fizičko okruženje u kojem se nalazi sustav (glasno
okruženje, jako osvjetljenje, prašina i sl.), drugi postojeći sustavi unutar
kojih se softver treba izvoditi ili s kojima treba imati interakciju
(operacijski sustav, drugi softver od kojeg preuzimamo podatke ili ih
šaljemo).

### Sigurnost i privatnost

Navedite zahtjeve (ukoliko postoje) koji su povezani sa pitanjima
sigurnosti i privatnosti podataka, te standardima i propisima vezanima
uz tu problematiku. To može uključivati zahtjeve za korištenjem
propisanih sigurnosnih procedura, tehnologija, usklađenost sa pravnim
okvirima i sl.

### Ostalo

Navedite ostale nefunkcionalne zahtjeve koji nisu prethodno navedeni.

## Skice zaslona 

Vizualizirajte značajke interakcije između krajnjeg korisnika i softverskog
rješenja kroz skice zaslona (engl. wireframe). Svrha skica je da na
vizualan način predočimo i komuniciramo što aplikacija treba raditi, a ne
da izradimo realan dizajn grafičkog sučelja. Pri tome skice možete na bilo
koji način nacrtati (npr. ručno na papiru + slikanje s mobitelom, MS Paint,
MS Word, Excel…)

