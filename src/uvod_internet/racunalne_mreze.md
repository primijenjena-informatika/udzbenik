## Računalne mreže

U početku su računala bila ogromni strojevi, zujimali su cijele sobe i bili su sporiji od najsporijeg pametnog mobitela.
I što je najbitnije, nisu bila povezana.
Jedno računalo je bilo samo za sebe, nije imalo pristup ostalima, a to je znatno ograničavalo njihovu funkcinonalnost.
Podaci su morali biti prebacivani između računala pomoću fizičkih uređaja, diskete, a to je potrajalo i nije bilo praktično za velike udaljenosti.

Informatičari su to ubrzo shvatili te nije prošlo mnogo vremena od razvoja prvih računala do razvoja prve veće računalne mreže.
Ta je mreža bila **ARPANET**.
Razvila ju je američka agencija ARPA, sada zvana DARPA, 1969.
Do 1971. je imala 15 računala povezana na nju.
Za razliku od današnjeg Interneta, ARPANET bio je znatno manje sofisticiran, sigurnosne mjere nisu postojale, umreženi računala bilo je malo i bio je spor.
Ključna razlika je činjenica da su ARPANET i slične mreže koristili većinom informatički stručnjaci, sveučilišta i vlada, a ne i svakodnevni građani.

Međutim, ARPANET je bio ključan korak u razvoju modernog Interneta.
ARPANET je bio rani primjer većeg distribuiranog sustava.
Distribuirani sustavi su ključni sastojak modernog računarstva jer omogućuju podjelu rada na više računala, a to znatno povećava performanse.
Jedno računalo nije dovoljno snažno za zadatke koji zahtjevaju veliku količinu računalnih resursa.
Očiti primjeri su znanstveni izračuni, npr. simulacija proteina ili treniranje velikih jezičnih modela kao GPT-4.
Naravno, sam Internet je najveći primjer masovnog distribuiranog sustava.

> [!DEFINICIJA]
> **Distribuirani sustav** je sustav računalne mreže u koju su povezana dva ili više zasebna računala koja koriste svoje računalne resure za izvršavanje zajedničkog zadatka ili cilja.

Danas je sve više i više uređaja umreženo.
Štoviše, svjetska ekonomija ovisi o Internetu.
Tijekom zadnjih nekoliko godina, sve je više i Internet of Things (IoT) uređaja, npr. pametni televizori, frižideri, termostati i slično.

### Osnove vrste i svrha mreža

Internet kao koncept najlakše se može zamisliti kao "mreža od mreža".
Računalne mreže postoje kako bi omogućile međusobno povezivanje računala i drugih uređaja u svrhe međusobne komunikacije.

Te računalne mreže od kojih se sastoji Internet uključuju one najmanje, **LAN** (engl. *Local Area Network*) mreže koje se nalaze u kućama i stanovima svih ljudi.

> [!DEFINICIJA] 
> **LAN** je vrsta lokalne mreže koja povezuje uređaje na lokalnom prostoru, npr. kućanstvo, sveučilište ili tvrtka.

One se obično sastoje od rutera, nekoliko računala i mobitela, televizora te još neke opreme.
Sljedeća najbitnija razina mreže je **WAN** (engl. *Wide Area Network*).
Glavna razlika između WAN i LAN mreža je u geografskom području koje zauzimaju.
WAN mreže će obično imati naprednije sustave koji su potrebni za upravljanje tako velikim prostorom.

> [!DEFINICIJA] 
> **WAN** je vrsta mreže koja se sastoji od velikog broja uređaja, najčešće i druge LAN mreže, s velikim opsegom, npr. grad ili država.

Još kategorija računalnih mreža postoje, uključujući **Personal Area Network (PAN)** i **Metropolitan Area Network (MAN)**.
PAN mreže su nekoliko metara u veličini.
Primjer takve mreže su mobitel i slušalice spojene pomoću WiFi-a ili Bluetootha.
MAN mreže obično su one mreže koje povezuju veće područje, recimo neki grad ili naselje.

Pristup Internetu daju pružatelji internetskih usluga (engl. *Internet Service Provider*, **ISP**).
Primjeri ISP-ova u Hrvatskoj su Hrvatski Telekom, Optima Telekom, A1 i drugi.

> [!DEFINICIJA]
> **ISP** je organizacija (u većini slučajeva komercijalna tvrtka) koja pruža internetske usluge drugim osobama i organizacijama.

### Komponente mreža

Za veliku većinu osoba, pristup Internetu dobiti će u obliku uređaja koji se zove **ruter** (od engl. *router*).
Ruter je uređaj koji služi kao glavna pristupna točka Internetu, na njega se, žično ili bežično, povezuju drugi uređaji koji zahtjevaju pristup Internetu, ali i ostalim uređajima u LAN mreži.
Njegova svrha je komunikacija između uređaja u njegovoj mreži i šireg Interneta.
On odašilje i prima (te onda šalje uređaju koji je namijenjeni primatelj) pakete podataka koje šalju i primaju uređaji povezani u mrežu putem rutera.


> [!DEFINICIJA]
> **Ruter** je uređaj koji povezuje računalne mreže te računala u njima tako što koordinirate slanje i primanje paketa podataka. Najčešće povezuje lokalnu mrežu s Internetom.

![Dijagram jednostavne LAN mreže.](./img/lan-diagram.png)

*Dijagram jednostavne LAN mreže s ruterom i nekoliko uređaja povezanih na njega. Kompliciranije LAN mreže mogu imati i mrežni preklopnik (engl. *switch*). Izvor: Cloudflare.*

Komponente mreže prikazane na Slici 1.1 jesu one najčešće.
Međutim, postoje i druge komponente mreža.
Ruter, recimo, nije nužan da bi se stvorila mreža.
Primjer uređaja koji može zamjeniti neke svrhe rutera je **mrežni preklopnik**.
On povezuje računala u mrežu u obliku zvijezde tako što koordinira slanje poruka između računala i omogućava im da komuniciraju međusobno.
Glavna razlika između preklopnika i rutera je ta što preklopnik ne može sam povezati svoju mrežu s vanjskim svijetom Interneta.
Međutim, preklopnici su često spojeni na ruter te tako mogu povezati računala s ostatkom Interneta.

> [!DEFINICIJA]
> **Mrežni preklopnik** je uređaj koji povezuje računala unutar mreže tako što šalje podatkovne pakete na njihovo odredište.
> 
![Dijagram LAN mreže.](./img/switch-diagram.png)

*Dijagram LAN mreže s mrežnim preklopnikom. Izvor: Cloudflare.*
