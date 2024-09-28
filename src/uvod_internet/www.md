## World Wide Web

World Wide Web je stvorio znanstvenik u CERN-u Tim Berners-Lee. CERN je mjesto gdje fizičari bombardiraju čestice s drugim česticama u nadi da će otkriti kako radi svemir. Međutim, Berners-Lee, koji je bio manje zainteresiran za uništavanje svijeta od ostalih, je vidio problem u trenutnom načinu djeljenja informacija između znanstvenicima. On je predložio ideju hiperteksta. Hipertekst je tekst koji u sebi ima poveznice na druge povezane tekstove. Vidio je priliku da se taj koncept napravi pomoću TCP/IP-a. Godine 1990. je napravio prvu verziju **HTTP-a** (engl. *HyperText Transfer Protocol*). HTTP je isto aplikacijski protokol.

Ta je ideja vrlo brzo zaživjela i drugi znanstvenici, ali i drugi korisnici, su se ubrzo pridružili. Ubrzo je osnovan World Wide Web Consortium (**W3C**), neprofitna organizacija s ciljem poboljšanja Weba. Web i Internet se često poistovjećuju, ali oni nisu ista stvar. Web je skup aplikacija koji leže na temelju Interneta, kao što vidimo.

### HTTP i prijatelji

#### TLS/SSL

Suvremeni HTTP je znatno drugačiji od originalne verzije. Kao i SMTP, bio je napravljen u doba kada računalna sigurnost nije bila u prvom planu jer je vrlo malo ljudi zapravo koristili računala. Pa tako nije imao ugrađenu podršku za enkripciju komunikacije između HTTP servera i preglednika. Ta je mana ubrzo uočena kada je Web postajao sve popularniji. Tvrtka Netscape, koja je tada proizvodila poznati web preglednik Netscape Navigator, razvila je prvu verziju protokola za sigurnu komunikaciju pomoću HTTP-a, **SSL** (engl. *Secure Sockets Layer*). SSL je uklopljen u HTTP kao unaprijeđeni protokol **HTTPS**. Danas je **TLS** (engl. *Transport Layer Security*) zamjenio SSL.

#### Klijenti i serveri

HTTP server se često naziva i **web server**. HTTP koristi **HTTP metode** za izvršavanje zahtjeva. Metoda govori koja vrstu akcije izvršava određeni URL na serveru. HTTP zahtjev se sastoji od metode, URL-a zahtjeva, tijela (sadržaja) zahtjeva, verzije HTTP-a i *headera* koji sadrže metapodatke o zahtjevu.

| **Metoda** | **Svrha metode**                                                                                                                                           |
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| GET          |  Dobivanje informacija o nekom resursu, npr. korisnicima, od servera. GET zahtjev ne smije imati tijelo.                                             |
| POST         |  Stvaranje novog resursa na serveru, npr. novog korisnika. Obično sadrži tijelo, npr. ime, email i lozinka korisnika.                                |
| PUT          |  Promjena resursa na serveru, npr. lozinka korisnika, tako što server zamjeni cijeli resurs.                                                         |
| PATCH        |  Promjena resursa na serveru tako što server zamjeni samo taj podatak koji se mjenja.                                                                 |
| DELETE       | Brisanje resursa sa servera.                                                                                                                                    |

**Tablica 1:** Popis najčešćih HTTP metoda i njihovih svrha.

Svaki HTTP zahtjev mora dobiti i odgovor koji se sastoji od HTTP koda i tijela odgovora. Tijelo nije obavezno.

| **Kod odgovora**     | **Značenje**                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------|
| 200 OK                    | Zahtjev je uspješno izvršen, zatražene informacije su poslane u odgovoru.                                     |
| 201 Created               | Zahtjev je uspješno izvršen, novi resurs je stvoren na serveru.                                               |
| 307 Temporary Redirect    | Server preusmjeri zahtjev s istom metodu na drugi URL.                                                                    |
| 400 Bad Request           | Klijent je krivo formatirao zahtjev.                                                                                      |
| 401 Unauthorized          | Zahtjev nije uspio, klijent se prvo mora autentificirati, odnsono reći tko je.                                |
| 403 Forbidden             | Klijent nema dozvolu pristupiti tom resursu.                                                                              |
| 404 Not Found             | Zatraženi resurs ne postoji na serveru.                                                                                   |
| 500 Internal Server Error | Postoji problem na serverskoj strani koja onemogućuje izvršavanje zahtjeva.                                   |

**Tablica 2:** Popis najbitnijih kodova HTTP odgovora i njihovih značenja.

HTTP kodovi 200--299 označuju uspješan zahtjev, 300--399 preusmjeravanje, 400--499 klijentsku pogrešku i 500--599 serversku pogrešku.

Poznati web serveri uključuju Nginx i Apache HTTP Server. Tijelo HTTP zahtjeva i odgovora može biti bilo koji oblik podataka. Tip podataka se određuje pomoću `Content-Type` headera. Kada preglednik otvara neku stranicu, web serveru će poslati `GET` zahtjev na domenu, odnosno IP adresu, te stranice. Server će vratiti odgovor s kodom `200 OK` ako stranica postoji ili `404 Not Found` ako ne postoji. Ako postoji, također će vratiti i tijelo sa HTML kodom stranice.

Tijela HTTP zahtjeva koji se šalju nekom API-u obično zapisuju pomoću **JSON-a** (engl. *JavaScript Object Notation*). To je format koji je čitljiv računalima i ljudima, a relativno je jednostavan. Prije se koristio **XML** (engl. *Extended Markup Langauge*), ali ga je JSON zamjenio jer je jednostavniji i sadrži manje sigurnosnih propusta.

### Programiranje na Webu

Kada je Berners-Lee napravio HTTP, želio je napraviti jednostavan jezik za izradu web stranica. Odlučio je napraviti *markup jezik*. To je jednostavan jezik, bazirao ga je na SGML jeziku. Nazvan je **HTML** (engl. *HyperText Markup Language*).

```html
<!DOCTYPE html>
<html>
<head>
  <title>Naslov stranice</title>
</head>
<body>
  <h1>Naslov</h1>
  <p>Ovo je paragraf teksta.</p>
</body>
</html>
```

**Primjer 1:** Osnovna struktura HTML dokumenta.

Dakle, stranice su na početku bile jednostavne, tekst s poveznicama, nisu ni imale slike. Kasnije je HTML dobio i sposobnost dodavanja slika, naravno, i drugih vrsta medija. Međutim, HTML nema mogućnost promjenu stila web stranice, npr. boju teksta ili font teksta ili lokaciju elemenata. Za to je napravljen **CSS** (engl. *Cascading Style Sheets*).

```css
body {
  background-color: #f0f0f0;
  font-family: Arial, sans-serif;
}

h1 {
  color: #333;
  text-align: center;
}
```

**Primjer 2:** CSS kod koji mjenja izgled naslova i pozadine na stranici.

Ubrzo su programeri željeli i mogućnost dodavanje interaktivnosti web stranicama. Do tada su web stranice bile statičke: korisnici nisu mogli interaktirati s njima. **JavaScript** (JS) je programski jezik koji je napravio Brendan Eich u 10 dana namjenjen da posluži kao jednostavni jezik za skriptiranje na web stranicama. U početku je to i bio, koristio se isključivo na web stranicama. Bio je na neki način baziran na Javi jer je tada Java bila vrlo popularna pa je Netscape, tvrtka koja je zaposlila Eicha da napravi JS, želio da bude slična Javi. S vremenom su se Java i JavaScript krenuli razilaziti. Dakle, JavaScript nije jednostavnija verzija Jave nego je svoji samostalan jezik.

Od 2009. JS se sve više koristi za programiranje i izradu servera, mobilnih i desktop aplikacija i drugih proizvoda. To je omogućio Ryan Dahl, koji je 2009. napravio Node.js, izvršno okruženje koje JavaScriptu daje sve biblioteke i sposobnosti koju imaju ostali jezici. Pod time uglavnom govorimo o pristupu resursima operacijskog sustava, npr. pristup datotekama, mreži, itd.

Godine 2017. je izašao **WebAssembly** (WASM), međukod koji omogućuje da se gotovo bilo koji programski jezik izvršava na web stranicama. Većina popularnih programskih jezika imaju barem djelomičnu podršku za WASM.

```javascript
document.querySelector("button").addEventListener("click", function() {
  alert("Button clicked!");
});
```

**Primjer 3:** JavaScript kod koji otvara dijalog na kojem piše `Button clicked!` kada se pritisne tipka.
