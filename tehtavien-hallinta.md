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
 
On tärkeää, että kaikki kolme (kuka, mitä, miksi) kohtaa ovat esillä
tarinassa. Valmiiseen sapluunaan ei kannata hirttäytyä vaan käyttää sitä
ohjenuorana. Sapluunan käyttö varmistaa, että kaikki osat tulevat mietityiksi ja
kirjatuiksi. Mitä ytimekkäämmin ja yksiselitteisesti asiat voidaan ilmaista, sen
selkeämpää tekeminen on. Käyttäjätarinoiden hiominen on osa
suunnitteluprosessia. Yllä olevat asiat voidaan ilmaista hiukan sulavammin
ilman, että tarinoiden muoto varsinaisesti muuttuu:
 
 > "User wants to login using Google account to avoid remembering yet another password."
 
 > "Käyttäjä haluaa kirjautua Google-tunnuksilla välttyäkseen uuden salasanan muistamiselta."
 
Jos mahdollista, sana "käyttäjä" kannattaa korvata tarkemmalla roolin
nimellä ("ylläpitäjä", "matkustaja" jne.). Erityisesti niissä
tapauksissa, joissa kehittäjät tai ylläpitäjät vaativat jotakin
ominaisuutta, tämä olisi hyvä merkitä.

> "Ylläpitäjä haluaa logit katseltavaksi järjestelmään X, jotta virhetilanteiden selvittäminen on helppoa."

Erityisesti roolisanat kannattaa pitää mahdollisimman lyhyinä. Ne
toistuvat samoina tarinoiden alussa ja ihmissilmä pitkälti sivuuttaa
ne. Englannin kielessä dev ja ops lyhenteet voivat olla käteviä
kehittäjistä ja ylläpitäjistä puhuttaessa. Oleellista on kuitenkin
aina käyttää samaa termiä samasta roolista. Jokaisen projektin kohdalla
tulee miettiä, mitkä roolit ovat järjestelmälle oleellisia.

## Tekniset tehtävät

Tekniset tehtävät kirjoitetaan käyttäjätarinoiksi, jotta
kuka-mitä-miksi -mietintä tulee tehtyä ja kirjattua. Tämä voi johtaa
välillä hiukan kankeisiin tarinoihin. Lukijan kannalta on kuitenkin
yksinkertaisinta, että tehtävien muoto ei merkittävästi muutu
tehtävästä toiseen siirrytäessä.

> "Kehittäjä haluaa JMXän olevan käytössä tuotannossa, jotta järjestelmän metriikka on nähtävillä."

Tämä on todennäköisesti tuoteomistajallekin selkeämmin ymmärrettävä
asia kuin lakoninen "JMX tuotantoon" -tehtävä.

## Bugit

Bugeja, eli järjestelmän virheellistä toimintaa, on hankala kuvata
käyttäjätarinoilla. Käyttäjätarinat kertovat miten järjestelmän pitäisi toimia.

Käytännössä käyttäjätarinan toteutus on ollut
puutteellinen, jos toiminnallisuuteen liittyy virheellistä
toimintaa. Lähtökohtaisesti bugit tulisi korjata ennen kuin
toteutuksen kanssa mennään tuotantoon. Tarina ei valmistu ennen kuin
se on kunnolla toteutettu. Näissä tilanteissa varsinaista bugia ei ole
tarpeen merkitä vaan tarinaan kirjataan havaitut puutteet.

Joskus syntyy tilanteita, joissa uuden toiminnallisuuden toteuttaminen
muuttaa jo kerran toteutettuja ominaisuuksia ei-toivotulla
tavalla. Tällaisissa tilanteissa on kirjattava bugi. Oleellista
bugissa on vähintään kirjata

 1. Miten järjestelmä toimii nyt?
 2. Miten järjestelmän pitäisi toimia?
 
Esimerkiksi:

 > "Bug: Nappula on vihreä, pitäisi olla punainen."
 
Bugeja käsiteltäessä on hyvä huomata, että bugi ja sen korjaaminen
voivat olla eri tehtäviä. Erityisesti monimutkaisissa järjestelmissä voi
syntyä tilanne, jossa järjestelmässä vika on niin syvällä, että sen
korjaaminen ei onnistu yhdellä askeleella. Tällöin korjaukset tulee
kirjoittaa käyttäjätarinoilla.

 > "Bug: Järjestelmä kaatuu täydenkuun aikaan, pitäisi toimia myös kuutamolla."
 >  - "Kehittäjä haluaa järjestelmän käyttävän samaa aikavyöhykettä, jotta vertailuissa vältytään virheiltä."
 >  - "Kehittäjä haluaa tietokantaan auringon asennolle oman tilan, jotta vuorokaudenaikaa ei tarvitse arvata."
 >  - "Kehittäjä halua säilyttää Kustaa Vilkunan Almanakasta tulevan kuun tilan, jotta oman laskentaa ei tarvitse ylläpitää."
 
Tämä tekee tuoteomistajallekin selväksi, mitä askelia on otettava
bugin korjaamiseksi. Mikropalveluiden aikakaudella on myös
mahdollista, että bugin korjaaminen vaatii muutoksia useaan
järjestelmään. Nämä korjaukset menevät mahdollisesti hyvin eri aikaan
tuotantoon. Tilanne mutkistuu, jos tällaiset korjaukset eivät
ensimmäisellä kerralla onnistu vaan niitä joudutaan vielä säätämään.
Selkeintä on, että konkreettiset tehtävät ovat omia tarinoitaan.


