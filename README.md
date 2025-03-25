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

S obzirom na sve veću potražnju za učinkovitim upravljanjem osobnim financijama, osobito među
studentima koji se prvi put suočavaju s financijskom neovisnošću, korisno je imati pristup
aplikaciji koja omogućava praćenje i analizu prihoda i rashoda. Ručno vođenje financija često je zamorno i sklono
pogreškama, zbog čega je potreban sustav koji će olakšati ovaj proces i omogućiti donošenje pametnijih
odluka o potrošnji.

Sustav za praćenje osobnih financija ( u daljnjem tekstu SPOF), riješenje opisano u ovom dokumentu, 
omogućuje praćenje financijskih aktivnosti, unos podataka o prihodima i rashodima u sustav, analizu unesenih podataka, te
generiranje izvještaja i statistike na temelju unesenih informacija. Korištenje ove aplikacije potiče
optimizaciju rashoda i osvješćivanje potrošnje po kategorijama.


### Definicije, akronimi i skraćenice

Termin | Objašnjenje
-|-
SPOF | Sustav za praćenje osobnih financija
PBZ | Privredna Banka Zagreb

### Reference 



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
statistike prihoda i rashoda po kategorijama te generiranje izvještaja o potrošnji.


### Karakteristike korisnika

Korisnik aplikacije SPOF je "student" koji ujedno ima želju pomnije pratiti vlastite financije.
Student kao korisnik ima napredno znanje korištenja aplikacija, osnovno znanje statistike i
organizacije osobnih financija.


### Ograničenja

Zbog zaštite podataka korisnika, pojedini korisnik "student" ne smije imati pristup podatcima
drugog korisnika. SPOF aplikacija je zamišljena kao standalone aplikacija koja nije integrirana
sa drugim sustavima. Hardverski resursi prosječnog računala su dovoljni za pokretanje i korištenje
aplikacije. Zahtjev potražitelja ograničava razvoj aplikacije u C# programskom jeziku i korištenje
SQL baze podataka za stalnu pohranu unesenih informacija. 

### Pretpostavke i ovisnost

Model praćenja financija je jednostavan model koji podržava unos 
i različite načine prikaza unesenih podataka. Model kao takav nije podložan promjeni.
Dodatni zahtjevi bi mogli uključivati širi spektar prikaza, statističke analize
i izvoza podataka.

### Ostalo


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

Identifikator | FZ-1
-|-
Zahtjev | Sustav će omogućiti pristup samo autentificiranim korisnicima
Obrazloženje | SPOF mora ograničiti pristup osjetljivim podacima korisnika tako da ih samo isti smije čitati i unositi.
Način provjere | Upis ispravnih korisničkih podataka treba rezultirati uspješnom autentifikacijom i omogućiti korisniku daljnji rad u sustavu. U slučaju neispravnih korisničkih podataka autentifikacija treba biti neuspješna i neće biti moguć rad u sustavu.
Prioritet [1-5] | 1
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-2
-|-
Zahtjev | Sustav će omogućiti ručni unos i pohranu prihoda korisnika
Obrazloženje | SPOF mora imati mogućnost unosa prihoda korisnika po kategoriji pomoću forme za unos koji će se pohraniti u bazu podataka.
Način provjere | Upisani iznos mora biti broj - novčani iznos ograničen na dvije decimale, korisnik mora unjeti kategoriju prihoda.
Prioritet [1-5] | 1
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-3
-|-
Zahtjev | Sustav će omogućiti unos i pohranu rashoda korisnika
Obrazloženje | SPOF mora imati mogućnost unosa rashoda korisnika po kategoriji pomoću forme za unos koji će se pohraniti u bazu podataka.
Način provjere | Upisani iznos mora biti broj - novčani iznos ograničen na dvije decimale, korisnik mora unjeti kategoriju rashoda.
Prioritet [1-5] | 1
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-4
-|-
Zahtjev | Sustav će omogućiti tablični prikaz prihoda i rashoda korisnika
Obrazloženje | SPOF mora imati mogućnost tabličnog prikaza unesenih prihoda i rashoda.
Način provjere | -
Prioritet [1-5] | 1
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-5
-|-
Zahtjev | Sustav će omogućiti pie-chart prikaz rashoda
Obrazloženje | SPOF mora imati mogućnost grafičkog prikaza rashoda u obliku pie-charta.
Način provjere | -
Prioritet [1-5] | 1
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-5
-|-
Zahtjev | Sustav će omogućiti generiranje izvještaja
Obrazloženje | SPOF mora imati mogućnost generiranja izvještaja po kategoriji i vremenskom razdoblju, izvještaji se kreiraju kroz formu na grafičkom sučelju.
Način provjere | Forma ne omogućava slobodan unos vrijednosti, u slučaju da nema podataka u periodu ili kategoriji izvještaj je prazan
Prioritet [1-5] | 1
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-6
-|-
Zahtjev | Sustav će omogućiti grafički prikaz usporednih trendova prihoda i rashoda 
Obrazloženje | SPOF mora imati mogućnost grafičkog prikaza usporednih trendova prihoda i rashoda u jednom grafu.
Način provjere | -
Prioritet [1-5] | 1
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-7
-|-
Zahtjev | Sustav će omogućiti generiranje izvještaja
Obrazloženje | SPOF mora imati mogućnost generiranja izvještaja po kategoriji i vremenskom razdoblju, izvještaji se kreiraju kroz formu na grafičkom sučelju.
Način provjere | Forma ne omogućava slobodan unos vrijednosti, u slučaju da nema podataka u periodu ili kategoriji izvještaj je prazan
Prioritet [1-5] | 2
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

Identifikator | FZ-8
-|-
Zahtjev | Sustav će omogućiti generiranje izvještaja
Obrazloženje | SPOF mora imati mogućnost generiranja izvještaja po kategoriji i vremenskom razdoblju, izvještaji se kreiraju kroz formu na grafičkom sučelju.
Način provjere | Forma ne omogućava slobodan unos vrijednosti, u slučaju da nema podataka u periodu ili kategoriji izvještaj je prazan
Prioritet [1-5] | 2
Izvor/Porijeklo | Nastavnici na kolegiju Programsko inženjerstvo

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

