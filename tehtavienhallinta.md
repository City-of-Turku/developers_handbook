[Takaisin päätasolle](./README.md)

# Tehtävienhallinta

Tehtävienhallinnassa on käytössä useita eri järjestelmiä (mm. Trello
ja Jira). Tässä ei opasteta järjestelmien yksityiskohtaiseen käyttöön
vaan annetaan perusperiaatteet tehtävienhallinnan käyttämisestä.

## Käyttäjätarinat

Tehtävät kuvataan ketterille menetelmille tyypilliseen tapaan käyttäjätarinoina.
 Lähtökohtaisesti käyttäjätarinan pitäisi vastata kolmeen kysymykseen:

 - Kuka?
 - Mitä?
 - Miksi?
 
Projektista riippuen tehtävät voidaan kirjoittaa joko suomeksi tai
englanniksi. Kaikki projektin materiaali tulisi tehdä kuitenkin samaa kieltä
käyttäen. Kielestä riippuen käyttäjätarinat kirjoitetaan lähtökohtaisesti
seuraavalla kaavalla:

 - `WHO wants WHAT, so WHY.`
 - `KUKA haluaa MITÄ, jotta MIKSI.`
 
Esimerkiksi:
 
 > "User wants to login using Google account, so he does not need to remember yet another password."
 
 > "Käyttäjä haluaa kirjautua Google-tunnuksilla, jotta hänen ei tarvitse muistaa taas uutta salasanaa."
 
On tärkeä, että kaikki kolme (kuka,mitä,miksi) kohtaa ovat esillä
tarinassa. Valmiiseen sapluunaan ei kannata hirttäytyä vaan käyttää sitä
ohjenuorana. Sapluunan käyttö varmistaa, että kaikki osat tulevat mietityiksi ja
kirjatuiksi. Mitä ytimekkäämmin ja yksiselitteisesti asiat voidaan ilmaista, sen
selkeämpää tekeminen on. Käyttäjätarinoiden hiominen on osa
suunnitteluprosessia. Yllä olevat asiat voidaan ilmaista hiukan sulavammin
ilman, että tarinoiden muoto varsinaisesti muuttuu:
 
 > "User wants to login using Google account to avoid remembering yet another password."
 
 > "Käyttäjä haluaa kirjautua Google-tunnuksilla välttyäkseen uuden salasanan muistamiselta."
 
Jos mahdollista sana "käyttäjä" kannattaa korvata tarkemmalla roolin nimellä
("ylläpitäjä", "matkustaja" jne.). Erityisesti niissä tapauksissa, joissa
kehittäjät tai ylläpitäjät vaativat jotakin ominaisuutta, tämä olisi hyvä
merkitä. Roolien nimet kannattaa pitää lyhyinä. Vaikka roolin määritteleminen on
tärkeää, pitkät sanat vain vievät tilaa.  Oleellista on erottaa roolien
vaatimukset toisistaan. Englanninkieliset dev ja ops lyhenteet voivat olla
käteviä kehittäjistä ja ylläpitäjistä puhuttaessa. Oleellista on aina käyttää
samaa termiä samasta roolista. Projektin tulee omalla kohdallaan miettiä, mitkä
roolit ovat järjestelmälle oleellisia.

Käyttäjätarinoiden nimen/otsikon ei tarvitse olla yleismaailmallisen
kuvaava. Riittää, että projektiryhmällä on asiasta selkeä käsitys ja tämä tulee
nimessä esille. Tehtävänhallinnan kuvaus kenttä on sitä varten, että siihen
kirjoitetaan tarkempi selvitys tehtävän sisällöstä. Kuvausta kirjoitettaessa on
tärkeää määritellä, milloin tehtävä on valmis. Erityisesti laadullisiin asioihin
keskittyvien tehtävien kanssa on oltava varovaisia. Tehtävien on oltava
mahdollisimman konkreettisia. Esimerkiksi:

> "Käyttäjä haluaa paremman käyttöliittymän, jotta järjestelmän käyttö on sulavampaa"

> "Käyttäjä haluaa siirtyä ajoneuvolistauksesta suoraan ajoneuvon tietoihin, jotta järjestelmän käyttö on sulavampaa.

Ylemmän tarinan toteuttaminen on käytännössä mahdotonta. Minkälainen
käyttöliittymä on parempi ja kenen mielestä? Kuinka paljon parempi on riittävän
hyvä? Alempi tarina kertoo taas selkeän parannuskohteen. Toteutus on valmis kun
siirtyminen suoraan onnistuu.

Jotta uudet käyttäjätarinat eivät riko vanhojen tarinoiden toiminnallisuuksia,
tulisi käyttäjätarinoita varten olla automaattiset testit. Jos testin tekeminen
tuntuu vaikealta, johtuu se yleensä siitä, että tarinan valmistumisehto on
epäselvästi määritelty. Testin tekeminen ensiksi varmistaa osaltaan, että tarina
on toteutettavissa.

## Tekniset tehtävät

Tekniset tehtävät kirjoitetaan käyttäjätarinoiksi, jotta kuka-mitä-miksi
-mietintä tulee tehtyä ja kirjattua. Vaikka tämä voi johtaa välillä hiukan
kankeisiin tarinoihin, niin lukijan kannalta on yksinkertaisinta, että tehtävien
muoto ei merkittävästi muutu tehtävästä toiseen siirryttäessä.

> "Kehittäjä haluaa JMXän olevan käytössä tuotannossa, jotta järjestelmän metriikka on nähtävillä."

Tämä on todennäköisesti tuoteomistajallekin selkeämmin ymmärrettävä asia kuin
lakoninen "JMX tuotantoon"-tehtävä. Ainakin käy selväksi kenelle asia on tärkeä.

## Laadulliset vaatimukset

Järjestelmälle on syytä asettaa laadullisia vaatimuksia, jotta järjestelmä
toimii "riittävän hyvin". Yksi esimerkki on järjestelmän nopeus. Ongelma on, että
"nopeus" on suhteellista (kuten kaikki laadulliset vaatimukset).  Esimerkiksi:

> "Käyttäjä haluaa järjestelmän käytön olevan nopeaa, jotta järjestelmää on mukava käyttää"

Tarina on täysin tulkinnanvarainen. Mikä on riittävän nopeaa? Toisaalta hyvin
nopeaakin järjestelmää voi olla epämukava käyttää. Milloin tarina on valmis?
Laadullisten vaatimusten ongelmana onkin"riittävän hyvän" määritteleminen.
Käytännössä tämä usein tarkoittaa jonkinlaisten raja-arvojen määrittelemistä.
Esimerkiksi järjestelmän nopeutta voitaisiin määritellä seuraavasti.

> "Käyttäjä haluaa järjestelmän vastaavan 99% tapauksista alle 500 ms, jotta käyttäjä ei pitkästy odottelemaan"

Koko järjestelmää koskevat laadulliset vaatimukset kannattaa kirjata yhteen
paikkaan ja viitata niihin yksittäisistä tarinoista. Tällöin ne pystytään
huomioimaan testeissä. Toiminnalliset tarinat eivät ole valmiita ennen kuin ne
huomioivat kaikki laadulliset vaatimukset. Laadullisia vaatimuksia on vaikea
hallita yksittäisinä tehtävinä toiminnallisten vaatimusten joukossa.

## Bugit

Bugeja, eli järjestelmän virheellistä toimintaa, on hankala kuvata
käyttäjätarinoilla. Käyttäjätarinat kertovat miten järjestelmän pitäisi toimia
tarinan toteutuksen jälkeen. Bugi kertoo, miten järjestelmä toimii
virheellisesti juuri tällä hetkellä. Käytännössä bugi on kuvaus siitä, miten
käyttäjätarina on toteutettu puutteellisesti.

Lähtökohtaisesti tarinan ei valmistu ennen kuin se on toteutettu ilman
bugeja. Kun tarina on vielä toteuttamatta, ei bugeja tarvitse kirjata vaan
toiminnallisuuden parantelu hoidetaan itse tarinassa. Joskus ongelmat huomataan
vasta, kun tarina on jo luultu toteutetuksi. Tällaisessa tilanteessa on
kirjattava bugi. Oleellista bugissa on vähintään kirjata

 1. Miten järjestelmä toimii nyt?
 2. Miten järjestelmän pitäisi toimia?
 
Esimerkiksi:

 > "Bug: Nappula on vihreä, pitäisi olla punainen."
 
Bugeja käsiteltäessä on hyvä huomata, että bugi ja sen korjaaminen ovat eri
tehtäviä. Erityisesti monimutkaisissa järjestelmissä voi syntyä tilanne, jossa
järjestelmässä vika on niin syvällä, että sen korjaaminen ei onnistu yhdellä
askeleella. Korjaukset tulee kirjoittaa omina käyttäjätarinoinaan.

 > "Bug: Järjestelmä kaatuu täydenkuun aikaan, pitäisi toimia myös kuutamolla."
 >  - "Kehittäjä haluaa järjestelmän käyttävän samaa aikavyöhykettä, jotta vertailuissa vältytään virheiltä."
 >  - "Kehittäjä haluaa tietokantaan auringon asennolle oman tilan, jotta vuorokaudenaikaa ei tarvitse arvata."
 >  - "Kehittäjä halua säilyttää Kustaa Vilkunan Almanakasta tulevan kuun tilan, jotta oman laskentaa ei tarvitse ylläpitää."
 
Tämä tekee tuoteomistajallekin selväksi, mitä askelia on otettava bugin
korjaamiseksi. Mikropalveluiden aikakaudella on myös mahdollista, että bugin
korjaaminen vaatii muutoksia useaan järjestelmään. Nämä korjaukset menevät
mahdollisesti hyvin eri aikaan tuotantoon. Tilanne mutkistuu, jos tällaiset
korjaukset eivät ensimmäisellä kerralla onnistu vaan niitä joudutaan vielä
säätämään.  Tämän takia on selkeintä että konkreettiset tehtävät ovat omia
tarinoitaan.

Tehtävänhallinnan kykyjä linkittää tarinoita toisiinsa on syytä hyödyntää. Bugin
ratkaisuun vaadittavat tehtävät on syytä linkittää bugin alle. Toisaalta bugista
olisi hyvä olla linkki tehtävään, joka bugin on synnyttänyt, ja toisaalta
tarinoihin, joihin bugi vaikuttaa. Yksinkertaisimmillaan linkittäminen voi olla
vain maininta tehtävän kuvauksessa.



