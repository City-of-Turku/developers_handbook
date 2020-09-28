# Turun kaupungin ohjelmistokehittäjän käsikirja

Tästä versionhallinasta löytyvät Turun kaupungin
ohjelmistokehityksessä käytettävät käytännöt kehittäjän
näkökulmasta. Korjauksia virheisiin ja yleisiä parannuksia voi
toimittaa tekemällä pull requestin.

## Käytänteet ja työkalut

 * [Ohjelmistokehityksen vaiheet](./vaiheet.md)
 * [Projektinhallintamalli (Scrum)](./projektinhallintamalli.md)
 * [Viestintä](./viestinta.md) 
 * [Koodin lisensointi](./koodin-lisensointi.md)
 * [Dokumentaatio](./dokumentaatio.md)
 * [Versiointi](./versiointi.md)
 * [Tehtävien hallinta](./tehtavien-hallinta.md)
 * [Versionhallinta](./versionhallinta.md)
 * [Definition of Done](./definition-of-done.md) 
 * [Ohjelmointikielet](./ohjelmointikielet-ja-kirjastot.md)
 * [Arkkitehtuuri](./arkkitehtuuri.md)
 * [Yhteiskehittäminen](./yhteiskehittaminen.md)
 * [CI-Ympäristö](./ci-ymparisto.md)
 * [Projektin infrastruktuuri](./projektin-infra.md) 
 * [Pääsynhallinta](./paasynhallinta.md)
  
## Vaatimukset

 * [Projektilla on oltava readme tiedosto](./vaatimukset/0001-readme-vaaditaan.md)
 * [Projektin kääntymisen on oltava toistettavaa](./vaatimukset/0002-toistettavat-buildit.md)
 * [Projektin tiedosto- ja hakemistorakenteen on oltava kuvaava.md](./vaatimukset/0003-kuvaava-projektin-rakenne.md)
 * [Väärin muotoiltujen lähdekooditiedostojen pitää estää projektin kääntyminen](./vaatimukset/0004-virheellinen-muotoilu-estaa-buildin.md)
 
### Ehdotuksia vaatimuksiksi

> Tähän on kirjoitettu tarkempia vaatimuksia koodille.
>
> Näistä voidaan valita halutut ja muokata ne lopulliseen muotoonsa.

#### Koodin laatu


##### (Yksikkö)testien on oltava nopeita (alle 2 minuuttia).

Järjestelmän yksikkötestien ajamiseen ei tulisi kulua muutamia
sekunteja kauempaa. Ison järjestelmän ollessa kyseessä testien
ajamiseen käytetty aika luonnollisesti kasvaa. Aika ei kuitenkaan saa
ylittää 2 minuuttia.

Liian pitkä testien ajoaika aiheuttaa testien jakamisen ryhmiin,
joista vain osaa ajetaan jatkuvasti. Tämä johtaa siihen, että
järjestelmän automaattinen testaus rapautuu, mikä lopulta estää
järjestelmän testaamisen.

Testiajat pysyvät lyhyenä, kun testit eivät tarvitse toimiakseen
jatkuvasti oikeaa tietokantaa, tiedostoja yms. Näiden käyttö tulee
erottaa helposti korvattavissa olevalla rajapinnalla, jotta testit
voivat korvata ne testitoteutuksella. Sen sijaan, että jokainen testi
testaisi sivutuotteenaan myös tietokantaa kannattaa tietokannan
toimintaan liittyvät testit jakaa omaksi kokonaisuudekseen.

##### Kaikki koodi tuotetaan kirjoittamalla testi ensin

Koodia tuotetaan _aina_ seuraavalla syklillä:

 1. Testi halutulle toteutukselle
 2. Epäonnistunut ajo
 3. Toteutus
 4. Onnistunut ajo
 6. Siisti toteutus
 7. Onnistunut ajo.
 5. Aloita alusta


Testin tulee olla selkeästi kirjoitettu ja dokumentoida
toiminnallisuus. Testit muodostetaan kolmesta osasta: arrange, act ja
assert. Testien nimissä pyritään seuraavaan muotoon.

    [Testattavan_metodin_nimi]_should_[haluttu_lopputulos]_when_[tilanne]
    
Jos osilla ei ole merkitystä niistä voidaan luopua. Samoin metodin
nimi voidaan joutua korvaamaan yleisemmällä testattavalla asialla,
jotta nimi olisi kuvaavampi.

Esimerkki testi:
    
    def display_should_return_result_when_equal_sign_has_been_entered(self):
        # Arrange
        c = Calculator()
        # Act
        c.enter("1")
        c.enter("+")
        c.enter("1")
        c.enter("=")
        result = c.display()
        # Assert
        self.assertEqual(result, "2")
        
Yksinkertaisimmissa tapauksissa arrange-osuudesta voidaan luopua.

    def upper_should_capitalize_every_letter(self):
        # Act
        result = 'foo'.upper()
        # Arrange
        self.assertEqual(result, 'FOO')
 
 
Yleensä osa kehitysvaiheessa tarpeellisista testeistä muuttuu
tarpeettomiksi toiminnallisuuden valmistuessa. Tämän takia myös testit
on muokattava helposti ymmärrettävään ja muokattavaan muotoon. Usein
tämä tarkoittaa testien yhdistämistä ja poistamista. Testit ovat
viime kädessä ajantasaisin dokumentaatio siitä, miten järjestelmän on
ajateltu toimivan.

 
##### (Yksikkö)testien on katettava koko koodi

Projektin yksikkötestien on katettava koko projekti. Käytännössä
testikattavuustyökalut eivät pysty aina tunnistamaan kaikkien rivien
ajamista, joten työkalujen ilmoittama kattavuus voi olla alle 100%.
Lisäksi on mahdollista, että rivien testaaminen kerran ei riitä, jotta
kaikki tilanteet tulisivat katetuksi.



#### Suorituskyky

##### Järjestelmän on reagoitava käyttäjän toimenpiteisiin näkyvästi alle 500 ms

Järjestelmän on reagoitava käyttäjän syötteeseen alle 500 ms. Jos
käyttäjä käynnistää raskaan operaation, jota ei ole mahdollista
suorittaa näin nopeasti, järjestelmä voi esimerkiksi ilmoittaa
operaation käynnistyneen ja arvion toimenpiteen kestosta.

Vaatimusta tarkennetaan tilaajan toimesta projektikohtaisesti.

##### Järjestelmän on reagoitava näkyvästi käyttäjän toimenpiteisiin 99.9% tapauksissa alle 100 ms

> Tämä on esimerkkinä. En tiedä kannattaako lähteä yleisesti määrittelemään näin tarkkaa tilannetta.
> Projektikohtaisesti nämä kannattaa määritellä.


#### Tietoturva

##### Järjestelmän turvallisuus ei saa perustua toimintalogiikan salassapitämiseen

Järjestelmän tietoturvaa mietittäessä tulee lähteä siitä, että järjestelmän
toiminta on kaikkien tiedossa. Järjestelmän tulee suunnitella siten, että
mahdolliselle murtautujalle voidaan huoletta antaa kaikki tieto järjestelmän
toiminnasta. Lähdekoodien, rajapintojen ja salausalgoritmien tunteminen ei saa
helpottaa hyökkääjän toimintaa.

Esimerkiksi tieto rajapinnan olemassaolosta ei saa mahdollistaa sen luvatonta
kutsumista.  Tämän sijaan kutsujat on tunnistettava ja valtuutettava
oikein. Tietojen salaus pitää olla rakennettu niin, että salatussa muodossa
olevat tiedot voidaan antaa hyökkääjälle ja kertoa miten ne on salattu,
vaarantamatta tietoturvaa.


##### Salasanoja ei saa laittaa versionhallintaan suojaamattomana

Versionhallintaan ei lähtökohtaisesti tallenneta salasanoja ollenkaan. Tietyissä
tilanteissa provisiointi (ympäristön automaattinen pystyttäminen) voi vaatia
salasanojen tallentamista koodien yhteyteen. Tällaisessa tilanteessa salasanat
tulee salata algoritmilla, jonka salausavaimen vahvuus on vähintään 128
bittiä. Tällaisessa tilanteessa on myös mietittävä kuinka salausavaimen jakelu
ja kierrättäminen hoidetaan turvallisesti. Salausavainta ei saa tallentaa
versionhallintaan.

##### Salasanojen vertaileminen on tehtävä hash-arvojen avulla

Käyttäjien salasanoja ei saa milloinkaan tallentaa selväkielisenä. Yleensä
salasanan tallennetaan vertailemista varten tällöin tallennetaan salasanasta
laskettu hash-arvo ja verrataan tätä käyttäjän syöttämän salasanan tuottamaan
vastaavaan arvoon. Yleisesti algoritmi näyttää seuraavalta

    hash = hashAlgoritmi(suola+erotin+salasana) // erotin voi olla vaikka ":"
    
Suolana voi käyttää mitä tahansa merkkijonoa, joka on jokaiselle
käyttäjälle yksilöllinen. Jos suolana käyttää esimerkiksi käyttäjän
tunnistetta ei sitä tarvitse tallentaa erikseen. Algoritmi on hyvä
merkitä ylös. Tallennettava merkkijono voi näyttä esimerkiksi
seuraavalta.

    *sha3-256*ded5910fafe7e22b374e139b911a9fba66c5854413e78e8d6d9b273068e34bef960a9e907ce3117bbc7907673107b03d8648ca3b3bbb6c319877f71dba31dedb

Vertailu tapahtuu seuraavasti

    onkoSalasanaOikein(käyttäjä, salasana):
        algoritmi, odotettuHash, suola = lataaKannastaKäyttäjänAlgoritmiHashJaSuola(käyttäjä)
        laskettuHash = algoritmi(suola+erotin+salasana)
        return odotettuHash == laskettuHash

Hashien tuottamiseen käytetään turvalliseksi tunnettua kryptokgrafista
funktiota. Koska hash-algoritmeista löytyy aika ajoin
turvallisuusongelmia algoritmia joutuu tulevaisuudessa todennäköisesti
vaihtamaan. Tämän takia käytetty algoritmi on hyvä merkitä ylös.

Toteutuksen on oltava sen verran turvallinen, että käytetyn koodin ja
käyttäjien "salasanojen" julkaiseminen tässä muodossa ei vaaranna
järjestelmän turvallisuutta.


##### Sisään tuleva data on validoitavat

Järjestelmän on varmistuttava sisään tulevan datan oikeellisuudesta ja
virheellinen data tulee hylätä. Järjestelmän tulee selvitä
tilanteesta, jossa datan syntaksi poikkeaa odotetusta tai dataa tulee
liikaa tai liian vähän. Erityisesti on varmistuttava datan
lähettäjästä ja siitä, että lähettäjällä on lupa lähettää kyseinen
data järjestelmään.


##### Virheilmoitukset eivät saa paljastaa järjestelmän sisäistä toimintaa

Järjestelmä ei saa tuottaa käyttäjän näkyville tietoa ohjelman sisäisestä
tilasta esimerkiksi tulostamalla ns. stack trace ruudulle virheen sattuessa.
Tämä on tyypillisesti oletustapa käsitellä järjestelmässä syntyneet
virheet. Vaikka tiedoista ei olisikaan varsinaista hyötyä,
oletusvirheilmoitusten käyttäminen antaa hyökkääjälle kuvan, että järjestelmän
virheen käsittelyä ei ole mietitty kunnolla. Tämä voi houkuttaa hyökkääjiä
järjestelmän kimppuun.


##### Virheilmoituksen pitää sisältää tunniste virhetilanteeseen

Virhetilanteen syntyessä käyttäjälle on kerrottava, miten hän voi korjata
syntyneen ongelman. Tukeen yhteyden ottamista varten käyttäjälle voidaan kertoa
generoitu tunniste (esim. "virheen tunniste 8c244ce8"). Tunniste on hyvä lisätä
myös logeihin. Tällöin tuki löytää juuri tämän virhetilanteen helposti.


##### Varmuuskopiot eivät saa pitää sisällään salasanoja selväkielisenä tai salattuna. Suolatut hashit ovat ok

Järjestelmä on rakennettava siten, että varmuuskopiot eivät pidä sisällään
salasanoja. Jos tuotantokoneissa on tiedostoissa salasanoja (kuten yleensä on)
näitä koneita ei varmuuskopioida.

Jos jostakin syystä varmuuskopioita joudutaan tekemään siten, että ne sisältävät
salasanoja, tulee salasanat kierrättää varmuuskopioinnin yhteydessä.

##### Tuotantopalvelimet eivät saa pitää sisällään mitään varmuuskopioimisen arvoista. Järjestelmä on voitava palauttaa toimintaan versionhallinnasta

Järjestelmä on suunniteltava siten, että tuotantokoneiden pystyttäminen on
nopeaa ilman varmuuskopioita. Usein tämä tarkoittaa versionhallinnassa olevan
automaation rakentamista.

##### Liikenne on salattava vähintään TLS 1.2

Tietoliikenne on ulkoverkossa salattava vähintään TLS 1.2:lla. Salaamaton
verkkoliikenne (esimerkiksi tuotantokoneen ja kannan välillä) on välitettävä
verkossa, joka on ulkopuolisilta suljettu. Salaamatonta verkkoliikennettä tulee
välttää myös sisäverkossa toimittaessa.

##### Ulos menevä data on siistittävä

Järjestelmän tuottamat tulosteet ovat siistittävä siten, että ulostulomuodon
syntaksia ei voida rikkoa. Hyvin yksinkertaisena esimerkkinä tuotettaessa
"-merkeillä ympäröityjä merkkijonoja on mietittävä, miten ratkaistaan tilanne,
jossa data itsessään pitää sisällään "-merkin. Yleinen tapa on sopia syntaksi,
jolla voidaan osoittaa varatun merkin olevan osa dataa (esim. \-merkki).

     "Esimerkissä "-merkki on ongelmallinen"   # Virheellinen muoto. Ei ole selvää missä jono loppuu
     "Esimerkissä \"-merkki on ongelmallinen"  # Esimerkiksi näin

Se, miten tuotettua dataa joudutaan käytännössä siistimään, riippuu paljon itse
järjestelmästä. Tyypillisiä tilanteita on SQL-kutsujen tuottaminen kantaa varten
tai HTML-sivujen rakentaminen selaimelle vietäväksi. Yleensä siistiminen
hoidetaan kirjastojen avulla. Virheet näissä tilanteissa johtavat muun muassa
[SQL-injektion](https://owasp.org/www-community/attacks/SQL_Injection) ja
[XSS-hyökkäyksen](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A7-Cross-Site_Scripting_(XSS))
mahdollisuuteen.

Logi on yksi ulostulon muoto, joka helposti sivuutetaan. Vaikka kirjasto
huolehtisi ulostulon siistimisen sinänsä voi olla, että se ei rajaa tulosteen
pituutta. Jos virhetilanteissa logitetaan käyttäjän lähettämä kutsu
sellaisenaan,voi tämä mahdollistaa hyökkäyksen, jossa logiin tuotetaan
gigatolkukka roskaa.

Viittauksissa ulkoisiin järjestelmiin tai komentorivien käskyjen tuottamisessa
on oltava myös tarkkana. Jos järjestelmä käyttää käyttäjän syötettä
huolimattomasti tiedostonimen tai linkin generoimiseen voi hyökkääjä saada ".."-
tai "/"-merkinnällä aikaan yllättäviä sivuvaikutuksia.


#####  Varmuuskopioista on voitava palauttaa päivän tarkkuudella alla 2 kk takainen tilanne

Järjestelmä on suunniteltava siten, että järjestelmä voidaan palauttaa
tarkkuudella johonkin viimeisen 2 kk aikana olleeseen tilanteeseen, jollei
projektille muuta määritellä.

##### Juoksevia (ja muita ennustettavia) tunnisteita tulee välttää

Järjestelmän paljastamat tiedot on hyvä pyrkiä pitämään sellaisina, että niistä
ei voi tehdä ylimääräisiä päätelmiä. Tietokannoissa tyypillisesti käytetyt
nousevat tunnisteet paljastavat yleensä ylimääräistä tietoa.

Esimerkiksi jos uuden käyttäjätunnuksen numero on 12304 tästä voidaan päätellä
käyttäjien määrää. Jos seuraavalla viikolla uuden käyttäjän tunniste on 12406
voidaan jo alkaa päättelemään kaikkien tunnusten summittaista luontiaikaa. Jos
murtautuja tietää suunnilleen ajankohdan jolloin kohde on rekisteröitynyt
järjestelmään, hän voi päätellä millä välillä kohteen käyttäjän tunniste on. Tai
kääntäen hyökkääjä voi päätellä tunnuksen luontiajankohdan
tunnisteesta. Yksinään tällaiset tiedot harvoin ovat ongelmia, mutta useista
lähteistä koostettu tieto saattaa johtaa järjestelmän suojausten ohittamiseen.

Tyypillinen tapa kiertää ongelmaa on käyttää
[UUID-tunnisteita](https://en.wikipedia.org/wiki/Universally_unique_identifier).
Merkkijonosta "08657ea1-0b6a-4338-9e59-6080c1bb1082" voi päätellä huomattavasti
vähemmän kuin esimerkiksi käyttäjänumerosta.

Tämän lisäksi arvattavat tunnisteet mahdollistavat yksinkertaisesti eri
tunnisteiden kokeilemisen. Jos on olemassa mahdollisuus, että jokin resurssi ei
ole suojattu oikein ja tunnisteen tiedetään olevan järjestysluku, hyökkääjä voi
yksinkertaisesti vain käydä tunnisteita läpi kunnes tärppää. Tämä ei käytännössä
onnistu UUIDtä käytettäessä.

##### CSRF-hyökkäykset pitää estää

Järjestelmän on varmistuttava, että kutsua ei ole generoitu 3. osapuolen
toimesta luvatta. Esimerkiksi jos tietoja voidaan tuhota GET-pyynnöllä
osoitteeseen `/resurssi/123/delete`, voi ulkopuolinen hyökkäysivusto saada
käyttäjän selaimen tekemään kyseisen kutsun ilman käyttäjän lupaa. Kyseisiä
hyökkäyksiä kutsutaa
[CSRF-hyökkäyksiksi](https://owasp.org/www-community/attacks/csrf).

Järjestelmän toiminta on suunniteltava siten, että selaimen
huijaaminen 3. osapuolen toimesta ei ole mahdollista. Käytännössä tätä voidaan
välttää siten, että GET-kutsut eivät koskaan muuta järjestelmän tilaa. Tämän
lisäksi voidaan joutua käyttämään erillistä kertaköyttöistä tunnistetta kutsujen
valtuuttamiseen. Tunnistetta generoitaessa on varmistuttava, että sitä ei voida
arvata ulkopäin.


#### Tietosuoja

#####  Käyttäjän (henkilö)tietoja ei saa logittaa tarpeettomasti

Käyttäjän tietoja ei saa päätyä logiin tarpeettomasti. Erityisesti salasanaa ei
saa logittaa missään tilanteessa. Jos käyttäjään on viitattava tulee käyttää
käyttäjän tunnistetta.

Kannattaa huomioida, että IP-osoitteita on pidetty henkilötietoina. Koska
henkilötietoja sisältävien logien käyttämistä koskevat tiukemmat säännöt
kannattaa logit rakentaa siten, että pääasiassa virheen käsittelyssä käytetty
logi ei sisällä tietoa käyttäjästä.

##### Käyttäjän tietojen (myös logi tietojen) katsomisesta on pidettävä kirjaa

Järjestelmä on rakennettava siten, että käyttäjän tietojen katsomisesta jää
merkintä. Tämä sääntö koskee niin tietokantaa kuin esimerkiksi logeja. Tietojen
katselusta tulee kirjata, mitä tietoja on katseltu ja miksi. Jos mahdollista
järjestelmän tulisi olla koneellinen. Tällöin tietokantaan ei saa olla pääsyä
ohi auditointijärjestelmän. Käyttäjällä on oikeus saada tietoonsa kuka hänen
tietojaan on katsellut ja miksi.

##### Mahdollisista tietoturvaloukkauksista on ilmoitettava viipymättä

Tietoturvaloukkauksista on ilmoitettava lain mukaan 72 tunnin kuluessa
tietosuojavaltuutetun toimistoon. Turun kaupunki huolehtii ulkoisesta
viestinnästä ja tietoturvaloukkausten ilmoittamisesta. Tämä vaatii, että
kaupunki on tietoinen loukkauksesta. Mahdollisesta loukkauksesta on ilmoitettava
kaupungin edustajalle viipymättä.

Tietoturvaloukkauksia ovat muun muassa murtautumiset järjestelmään, salaisten
tietojen puutteellinen suojaus (verkkolevyt, rajapinnat yms.), perusteeton logien
katselu tai tietokannan selaaminen.


##### Käyttäjän tietoja ei saa tallenta ilman lupaa

Kehittäjän on hyvä tutustua [Turun tietosuoja
sivuun](http://www.turku.fi/tietosuoja).  Tämän lisäksi on varmistuttava, että
sovellukseen liittyvä [rekisteriseloste](https://rekisteri.turku.fi/Saabe_data/)
on ajan tasalla. Käyttäjästä ei saa kerätä mitään tietoja, joiden tallentamiseen
hän ei ole erikseen antanut lupaa.

Lupa on muistettava pyytää, jos käyttäjää seurataan esimerkiksi analytiikkaa
varten (Google analytics). Pelkästään evästeiden käyttäminen HTTP-sessiota
varten ei vaadi lupaa käyttäjältä.

##### Käyttäjän tiedot on saatava ulos järjestelmästä

Järjestelmän on suunniteltava siten, että käyttäjästä kerätty data on saatavissa
ulos järjestelmästä. Tietojen tulee olla käyttäjälle helposti luettavissa ja
hyödynnettävässä muodossa.

Jos kyseisen kaltaiseen tietoon ei ole olemassa yleisesti käytössä olevaa
tiedostomuotoa, käytetään JSON-muotoa.

##### Järjestelmän on mahdollistettava käyttäjien tietojen tuhoaminen

Järjestelmän on mahdollistettava käyttäjän kaikkien tietojen poistaminen, joita
kaupunki ei tarvitse lakisääteisten velvollisuuksien hoitamisessa.

Tietojen poistamisessa on huomioitava myös tietokantojen varmuuskopiot ja
logit. Jos järjestelmä joudutaan palauttamaan varmuuskopiosta, käyttäjän tiedot
eivät saa palautua järjestelmään. Koska tietojen poistoon on aikaa kuukausi
kannattaa pyrkiä henkilötietoja sisältävien logien tallentaminen rajoittaa
kuukauden pituuteen (jos lait ja asetukset eivät muuta vaadi).

#### Järjestelmän monitorointi

##### Projektien tulee tarjota metriikka statsd-muodossa
Sovelluksen tulee lähettää sovelluksen metriikat
[statsd](https://github.com/statsd/statsd) muodossa kyseisen palvelimen porttiin
8125, josta ne voidaan tarvittaessa toimittaa eteenpäin.

Metriikka on toimitettava:

   * Rersurssipoolien koosta ja käytetyistä resursseista.
   * Käsiteltyjen pyyntöjen määrästä ja kestosta operaatiokohtaisesti.
   
   
##### Logi tuotetaan JSON-muodossa stdout-virtaan

Järjestelmän tulee tuottaa logi suorana tulosteena normaaliin stdout:iin JSON-muodossa.

Viestin pitää sisältää vähintään seuraavat kentät:

  * msg - viesti
  * level - viestin taso (critical, error, warning, info, debug, trace)
  * time - tapahtumaaika (UTC) muodossa "2020-09-16T10:08:00.123Z".
  * corrId - Correlation id, UUID, joka pysyy samana saman kontekstin (esim. palvelimelle tehty pyyntö) lokiriveille.
   
Esimerkiksi:
   
    {"time":"2020-09-15T15:11:12.113Z","level":"info","corrId":"9a63fcb6-3867-48d9-a5d1-edb4fd04042b","msg":"Application v1.2.3 started."}
    
#### Saavutettavuus

Turun kaupungin web-järjestelmien taso on [WCAG
2.1](https://www.w3.org/TR/WCAG21/)-määritelmän mukainen AA-taso. Chrome
selaimen Lighthouse-työkalua voidaan käyttää kehittäjän apuna saavutettavuus
ongelmien löytämisessä.
 
# Muuta ajattelemisen aihetta

 * [The twelve-factor methodology](https://12factor.net/)
 * [The Principles of Clean Architecture by Uncle Bob Martin](https://www.youtube.com/watch?v=o_TH-Y78tt4)
 * [Näin keräät ja käytät lokitietoja](https://www.kyberturvallisuuskeskus.fi/fi/ajankohtaista/ohjeet-ja-oppaat/nain-keraat-ja-kaytat-lokitietoja)




























