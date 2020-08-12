# Turun kaupungin ohjelmistokehittäjän käsikirja

> Dokumentin kieliasu ja rakenne on vielä viimeistelemätön ja
> asiasisältö tarkastamaton. Tarkoitus on kerätä kommentteja dokumentin
> suunnasta, jotta se saadaan menemään heti alussa oikeaan suuntaan.

## Dokumentin tarkoitus

Tämän dokumentti kuvaa Turun kaupungin ohjelmistojen kehityksessä
käytetyt käytännöt kehittäjän näkökulmasta.  Käsikirjan viimeisin
versio on saatavissa XXXX. Virheitä ja parannuksia voi toimittaa XXXX.
Tämän dokumentin pitäminen versionhallinnassa (esim github)
mahdollistaisi muutoksien selkeän ehdottamisen. Tällöin dokumentista
voitaisiin tuottaa web-sivu ja linkitykset toimisivat paremmin.

## Käytänteet ja työkalut

### Yleistä

Turun ohjelmistokehitys tapahtuu inkrementaalisella ja iteratiivisella
mallilla seuraavissa toisistaan erilisissä vaiheissa.

 * Kehitys
 * Testaus
 * Operointi

Kehitysvaiheen, jota tämä dokumentti pääasiassa käsittelee,
tarkoituksena on selvittään toteutukselle asetettavat vaatimukset ja
laatia niiden mukainen ratkaisu. Testauksen tehtävänä on varmistaa,
että tuote vastaa sille asetettuja odotuksia. Molemmat vaiheet
käyttävät samoja vaatimuksia. Operointi vastaa järjestelmän
päivittämisestä tuotantoon, sekä päivittäisestä ylläpidosta, että
valvonnasta.

Testaus ja operointivaiheet tuottavat kehitysvaiheelle arvokasta
palautetta tuotteen toiminnasta, joka osaltaan ohjaa
kehitystyötä. Tämän takia on tärkeä, että ensimmäisestä sprintistä
lähtien saadaan tuotettua koodia tuotantoon asti. Projektin (tuotteen
omistajan) on varmistettava, että testaus ja operointi resurssit ovat
riittäviltä osin käytettävissä.

Koodin laittaminen tuotantoon ei tarkoita, että sitä tarjotaan
laajalle asiakasjoukolle. Asiakkaille julkaisemin on erillinen
toimenpide, jonka suunnittelu kuuluu viimekädessä
tuotteenomistajalle. Tuotteen omistajan on kuitenkin tärkeä
tarkastella sovelluksen toimintaa tuotantojärjestelmästä.

> Tässä pitäisi lisäksi kertoa oleelliset yhteystiedot sekä käytetty
> pikaviestipalvelu TEAMs sekä sen rakenne. Tai viittaus siihen mistä
> tiedot löytyvät.

### Menetelmä

Kehitystyössä käytetään scrum-menetelmää. Sprintin pituus on 2
viikkoa. Sprintti aloitetaan maanantaina aloituspalaverilla ja
lopetetaan seuraavan viikon perjantaina tulosten katselmoinnilla, jota
seuraa retrospektiivi.

> Perinteisesti ketterissä menetelmissä mennään tuotantoon sprintin
> aikana. Asiat eivät ole valmiita ennen kuin ne ovat
> tuotannossa. Asioiden erottaminen kolmeen osaan aiheuttaa
> aikataulullisia ongelmia. Yksi tapa on ketjuttaa vaiheet (ensin
> kehitys, sitten testaus, sitten tuotantoon). Kahden viikon
> sprinteillä tämä tarkoittaa 6 viikon läpijuoksuaikaa minimissään,
> mikä on hyvin hidas. Toinen vaihtoehto on suorittaa kaikki vaiheet
> eri toimijoiden kesken saman 2 viikon jakson aikana, mutta tämän
> orkestrointi on yleensä hyvin vaikeaa. Lisäksi ongelmana on se, että
> alkusprintistä kehitystyössä on kiirettä ja loput organisaation osat
> pyörittelevät sormiaan. Loppuviikosta taas on toisten päin. Kiireen
> ja työttömyyden vaihtelu ei ole kovin mielekästä.
>
> Riippuen siitä miten työt tilataan, niin voi olla hyvä kuvata
> menetelmä tarkemmin tai jättää kuvaus kokonaan pois. Jos tilataan
> valmiita tiimejä, niin menetelmän kuvaamisella ei ole niin
> merkitystä.
>
> Asiakaan tahtotilaa pitää tältä osin tarkentaa, jos tämän ajatellaan kuuluvan dokumentin sisältöön.

Tuotteen omistajan (product owner) vastuulla on, että työlista
(backlog) on kunnossa ja ajan tasalla. Viimeistään sprintin alkaessa
tehtävillä on oltava kuvaus ja kokoarvio. Tämä vaatii vaihtelevan
määrän suunnittelupalavereita sprintin aikana.

Kehitystiimi vastaa siitä, että toteuttaa tuotteen omistajalle
sprintin aloituksessa lupaamansa asiat siten, että työtä ei näiden
osalta jää seuraavaan sprinttiin. Lisäksi tiimi tuottaa suunnitelmia
ja aikatauluarvioita tuotteen omistajan tarpeen mukaan.

Jokaisen tiimin ja toteen omistajan toimintaa tukemassa on scrum
master, jonka vastuulla on tukea scrum-menetelmän käytössä niin tiimiä
kuin tuotteenomistajaakin. Scrum master voi toimi useamman tiimin
palveluksessa ja tarvittaessa hän järjestää menetelmän mukaisia
tilaisuuksia (aloitus-, suunnittelu-, lopetuspalavereita ja
retrospektiivejä). Lähtökohtaisesti pitäisi pyrkiä siihen, että tiimi
pitämään tilaisuudet yhdessä tuotteenomistajan kanssa suoraan.

### Viestintä

Käytettävät viestintävälineet kiireellisyysjärjestyksessä

 * Puhelin
 * Pikaviestin
 * Sähköposti
 
Tavoiteltu toimintatapa on hoitaa asiat sähköpostilla. Jos asian
läpikäyminen vaatii enemmän kuin yhden sähköpostikierroksen on
suositeltavaa sopia palaveri sähköpotilla. Tilanteissa, joissa
tarvitaan nopea vastaus ja kaksisuuntaisuutta puhelin ja pikaviestintä
voidaan käyttää.

### Pääsynhallinta

Oikeuksien jakamisesta vastaa XXXX.

> Tähän voisi kertoa, mitä kautta kehittäjät saavat tarvittavat
> oikeudet töiden tekemiseen. Voi olla, että tämä kannattaa jakaa
> alikohtien alle (mistä saa CI-järjestelmään oikeudet yms). Jätän sen
> nyt tähän muistuttamaan asiasta.

### Projektilta vaadittava infrastruktuuri

> Tähän lukuun on tarkoitus kuvata, mitä ei teknisiä vaatimuksia
> projektin pyörittämiselle on. Tämä ei eroa uusien tai vanhojen
> projektien osalta. Uutta projektia tehtäessä kyvykkyys on
> rakennettava, vanhan tapauksessa on tarkistettava, että kyvykkyys on
> kehittäjä käytössä.
> 
> Tämä on "paras arvaus" -tasoa ja vaatii lisätietoa asiakkaalta.

Riippumatta toteutustekniikasta projektilla tulee olla seuraavat resurssit käytössään.

 * Versionhallinta
 * Tehtävienhallinta
 * CI-ympäristö
 * Esituotantoympäristö
 * Tuotantoympäristö
 
> näiden lisäksi erillinen testausympäristö? Tuotetaanko palveluista
> jonkinlaista palvelukatalogia/arkkitehtuurikuvausta jonnekin? Kuka
> nämä perustaa?

Kehitystiimin vastuulla on huolehtia, että nämä ovat kunnossa ja
tiimillä on kyvykkyys saada tuote käyttöön. Esituotanto- ja
tuotantoympäristöt järjestetään pyytämällä XXXX. Tuotteen
päivittäminen tapahtuu toimittamalla se XXXXX, jossa se ensin
testataan.

### Versionhallinta

> Gitflow malli ei ole erityisen ketterä. Se tukee huonosti
> nykyaikaista muutoksesta tuotantoon ajatusta. Lähestymistavassa iso
> määrä koodia kasataan ennen päivityksen tekemistä ja tämä
> hankaloittaa virhetilanteiden selvittämistä (mahdollisia vikakohtia
> on paljon). Lähestymistapa vaatii, että versioiden sisällöt on
> suunniteltu hyvin etukäteen. Lisäksi helposti käy niin, että syntyy
> useita tuettuja versioita, jotka syövät kehitysresursseja.
>
> Lisäksi lähestymistapa vaatii useamman CI-jobin kuin yksinkertaisemmat lähestymistavat.

Projektien lähdekoodit ja muut tarpeelliset resurssit versioidaan
git-työkalulla. Gitin käytössä käytetään ns. Gitflow lähestymistapaa
(https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). Kehitys
tapahtuu aina omassa haarassaan, joka liitetään develop-haaraan. Kun
halutut ominaisuudet on saatu kuntoon develop haarassa koodit
liitetään master-haaraan ja uusi versio julkaistaan.

Kun koodia ollaan liittämässä develop-haaraan, siitä on tehtävä
ns. pull request. Tullakseen liitetyksi koodi tarvitsee XXXX.

> Yleensä pull requestin liittäminen voi vaatia esimerkiksi, että
> yksikkötestit menevät lävitse, staattiset koodi analysaattorit eivät
> löydä huomautettavaa ja kaksi kehittäjää puoltaa koodin liittämistä.
> 
> Kehittäjien puolto on hankala asia tilattaessa koodia
> ulkopuolelta. Ostotiimillä on erityisen kovat paineet saada asioita
> aikaiseksi ja kaikkien firmojen tapauksessa ei ole todennäköistä,
> että kehittäjät torppaisivat toistensa koodia.
>
> Mahdollisia malleja on tiimien yli menevä ristiin
> katselmointi. Ongelmana tässä on, että jos katselmoijalla ei ole
> mitään suhdetta katselmoitavaan koodiin, ei katselmoijalla ole
> suurta intressiä koodin laadun tarkkailuun.
>
> Ostettaessa koodia ulkopuolelta tilaajan olisi hyvä tarkkailla
> koodin laatua. Välttämättä tämä ei resurssien puuteen vuoksi ole
> mahdollista. Pelkkä pull requestien lukeminen alkaa myös puuduttaa
> hyvin nopeasti.

Versionhallintaan tehtävien muutosten kommenttien on viitattava
tehtävänhallinan tehtävään. Itse kuvaus kirjoitetaan muodossa, joka
kuvaa tuotteen toiminnan muutoksen jälkeen. Kommentit kirjoitetaan
englanniksi.

    User can remove unnecessary address from address list (JIRA-1234)

> Commit-viestien muodon kanssa kannattaa olla tarkkana. Jos jokainen
> kehittäjä kirjoittelee omalla tyylillään repo on äkkiä
> sotkussa. Toisaalta pitää olla resursseja vahtia, että sääntöjä
> noudatetaan

Versionhallinta kommenteista on siivottava toisiaan korjaavat
muutokset pois ennen koodien liittämistä päähaaraan.


### CI-ympäristö

CI-järjestelmänä on käytössä XXXX. Järjestelmään lisätään uusia töitä XXXX.

Projektilla tulee olla CI-järjestelmässä seuraavat työt:

 * Pull requestin tarkastus
 * Develop haaran kääntäminen
 * Julkaisuversion luonti

Projektin rakentamisen (eng. build) on toimittava
komentoriviltä. CI-työt eivät saa sisältä logiikkaa, jota tarvitaan
sovelluksen rakentamiseen tai tarkastamiseen. CI-järjestelmä vain
suorittaa saman komentoriviltä käytettävissä olevan komennon
automaattisesti ja tarkistaa tuloksen (esim. ”make
test”). Rakentamisen on tarkistettava yksikkötestien onnistuminen sekä
käytettyyn toteutusteknologiaan sopivan staattisen koodianalysaattorin
(ns. lintter) tulokset. Projektin rakentamisen on toimittava samasta
versionhallinan kohdasta samalla tavalla.

Projektin julkaistu versio siirretään talteen XXXX.

CI-töissä on oleellista, että logiikka ei valu kyseisiin
töihin. Muussa tapauksessa sovellukseen itseensä oleellisesti kuuluva
logiikka sijaitsee jossakin muualla kuin ko. projektin
versionhallinnassa. Kehittäjän on pystyttävä suorittamaan samat temput
omalla koneellaan kuin mitä CI-järjestelmä tekee. Tämä helpottaa
ongelmien korjaamista ja paikantamista.

> Tästä puuttuu automaatio muutosten viemiseksi automaattisesti
> tuotantoon. Lisäksi pitää miettiä miten CI-järjestelmä
> konfiguroidaan. Esimerkiksi Jiran tapauksessa olisi hyvä käyttää
> ohjelmallista rajapintaa. Tämä on toisaalta monelle tiimille
> yksistään liian hankala vaatimus. Tällöin voidaan yleisesti
> käytetyille projektityypeillä määritellä valmiit työt.

### Tehtävienhallinta

Projektin tehtävien hallinta tapahtuu JIRAssa.

> Tähän pitää kuvata tehtävien tilat, käytetyt sanamuodot usein
> käytetään ns. user story muotoa (As an user, I want XXXX, so that
> YYYY). Tämä johtaa usein melko pitkiin otsikoihin. Tätä voi lyhentää
> esim muodolla User wants XXXX so that. Lisäksi kieli pitäisi
> päättää. Koodin kieli (englanti) puoltaisi englannin
> käyttämistä. Usein projektin osallistujat ovat suomenkilisiä ja
> toimiminen vieraalla kielellä hankaloittaa kommunikointia (suomeksi
> muoto ”Käyttäjänä haluan xxxx, jotta yyyy).

### Versiointi

Projektit versioidaan SemVer määrityksen mukaisesti kolmella pisteellä
erotetulla numerolla (https://semver.org/). Erityisen tärkeää tämä on
kirjastojen sekä ulkoisia rajapintoja sisältävien tuotteiden kanssa.

### Dokumentaatio

Versionhallinnan tulee sisältää vähintään readme.md niminen tiedosto,
joka on kirjoitettu Markdown-kielellä. Tiedoston tulee kuvata
versionhallinnan sisältö, projektin kääntämisen ja käyttöönoton
vaiheet.

> Mitä muuta tarvitaan? Onko (mikro)palveluista jonkinlaista palvelurekisteriä?

### Koodin lisenssointi

Minkälainen lisenssointipolitiikka halutana määritellä? Vai halutaanko määritellä minkäälaista?

Turun kaupunki määrittelee projekti kohtaisen lisenssoin

### Toteutustekniikan valinta

#### Arkkitehtuuri

> Tämän kirjoittamiseen tarvitaan enemmän tietoa asiakaan ympäristöistä.

#### Ohjelmointikielet

Mitä kielten versioita käytetään? Onko merkitystä millä kielellä toteutetaan?

##### Java

##### Python

##### JavaScript

#### Kirjastot

> Tarvitaan tietoa mitä kirjastoja/frameworkejä on käytössä, jos niitä
> halutaan käydä tässä tarkemmin lävitse.  Kolmannen osapuolen
> kirjastoja valittaessa on otettava huomioon koodin lisensointiin
> liittyvät asiat.

##### React

React on vain niin sanottu view-kerros se tarvitsee käytännössä
tuekseen muita kirjastoja/komponentteja, jotta sovelluksen rakenne on
järkevä.

## Huomioitavat vaatimukset

### Yleistä projektin rakenteesta

#### Projektin on sisällettävä readme.md

#### Julkaisuversion rakentamisen on oltava toistettavaa

Järjestelmän on samassa versionhallinnan kohdassa oltava samanlainen
eri ajanhetkinä. Käytännössä tämä tarkoittaa sitä, että ulkoisten
riippuvuuksien versiot on kiinnitettävä ja oleellisia resursseja ei
voida ladata palveluita, jossa ne voivat muuttua (tai poistua).

#### Projektin rakenteen ja nimeämisen pitää kuvastaa sovelluksen toimintaa

Tyypillinen tapa rakentaa projekti on jakaa projekti käytetyn
frameworking mukaisiin osiin. Nämä nimet ovat hyvin geneerisiä ja
johtavat esimerkiksi seuraavankaltaiseen hakemistolistaukseen
projektin päätasoilla.

    public_transportation/
       views/
       controllers/
       repositories/

Listaus sopisi mihinkä tahansa järjestelmään. Se ei kerro lukijalle
järjestelmästä yhtään mitään. Toinen yhtä informatiivinen tapa on
luetella projektissa käytettävät työkalut ja jakaa koodi niiden alle.

    public_transportation/
        packer/
        cloudformation/
        ansible/
        python/
        java/
        react/

Kumpaakin tapaa tulisi välttää ja käyttää korkeintaan syvällä
projektin hakemistorakenteessa. Projektin rakenteen tulisi pyrkiä
kommunikoimaan, mistä sovelluksessa on kysymys. Esimerkiksi
seuraavasti:

    public_transportation
        timetables/
            editor/
            viewer/
   
Luonnollisesti käytetyt työkalut ja tekniikat luovat nimeämiseen omat
rajoitteensa. Järkevän rakenteen luomiseen kannattaa kuitenkin käyttää
vaivaa, koska koodia kirjoitetaan viimekädessä ihmiselle. Tietokone
ymmärtää koodin rakenteesta riippumatta.

#### Lisää….

### Saavutettavuus (WCAG2.1 AA)

### Tietosuoja ja yksityisyys

### Tietoturva

 

## Keskeneräistä sisältöä ja ajatuksia

 * Turun kaupungin projektien rakenne kehityspäätöksestä tuotantokäyttöön.
 * Uuden ja ylläpitävän kehityksen erityispiirteet
 * Projektin lähtötiedot
 * Projektin tuotokset
 * Käytetyt työkalut ja niihin liittyvät toimintamallit
 * Toteutusteknologiat ja niiden valinta
 * Ohjelmiston rakenne ja koodin muotoilu
 * Projektinhallinta
 * Versionhallinta
 * Dokumentaatio
 * Viestintä
 * Pääsynhallinta
 * Sovelluksien toimintaan liittyvät lainsäädännölliset ja muut vaatimukset.
  * Saavutettavuus (WCAG2.1 AA)
  * Yksityisyys (EU ja kansalliset asetukset)
  * Yleisimpien haavoittuvuuksien välttäminen (OWASP 10)
  * Tiedon ja tietoliikenteen salaukseen liittyvät seikat
 * Definition of Done
 * Rajapintojen toteutuksessa huomioitavat asiat
 * Datan varastoinnissa huomioitavat asiat
 * Tuotantoonsiirrossa huomioitavat seikat



Minkälainen paketointi?

Operointi IT-palvelulle

Monitoroinnit miten on hoidettu?

Tämän kehityksen huomioiminen aikatauluarvionnissa, konfiguroinnit ja asennus dokumentaatio








