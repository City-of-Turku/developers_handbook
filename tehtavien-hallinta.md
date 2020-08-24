[Takaisin päätasolle](./README.md)

# Tehtävien hallinta

## Käyttäjätarinat

Tehtävienhallinnassa on käytössä useita eri järjestelmiä (mm. Trello
ja Jira). Tässä ei opastata järjestelmien yksityiskohaiseen käyttöön
vaan annetaan perusperiaatteet tehtävienhallinnan käyttämisestä.

Ketterissä projekteissa käytetään perinteisesti
käyttäjätarinoita. Lähtökohtaisesti käyttäjätarinan pitäisi
pystyä kuvaamaan kolme asiaa:

 1. Kuka?
 2. Mitä?
 3. Miksi?
 
Projektista riippuen tehtävät ovat kirjoitettu joko suomeksi tai
englanniksi. Asiat on pyrittävä kuvaamaan seuraavilla seuraavilla
tekstipohjilla.

 - `WHO wants WHAT, so WHY.`
 - `KUKA haluaa MITÄ, jotta MIKSI.`
 
Esimerkiksi:
 
 > "User wants to login using Google account, so he does not need to remember yet another password."
 > "Käyttäjä haluaa kirjautua Google-tunnuksilla, jotta hänen ei tarvitse muistaa taas uutta salasanaa."
 
On tärkeä, että kaikki kolme (kuka,mitä,miksi) kohdat ovat esilliä
tarinassa. Valmista sabluunaa tulee käyttää ohjenuorana, sille se
varmistaa, että kaikki osat tulevat mietityiksi ja
kirjatuiksi. Toisaalta, mitä ytimekäämmin ja yksiselitteisisesti asiat
voidaan ilmaista, sen selkeämpää tekeminen on. Tekstien hiominen onkin
osa suunnitteluprosessia. Yllä olevat asiat voidaan ilmaista hiukan
sulavammin ilman, että tarinoiden muoto varsinaisesti muuttuu:
 
 > "User wants to login using Google account to avoid remembering yet another password."
 > "Käyttäjä haluaa kirjautua Google-tunnuksilla välttyäkseen uuden salasanan muistamiselta."
 
Jos mahdollista sana "käyttäjä" kannattaa korvata tarkemmalla roolin
nimellä ("ylläpitäjä", "matkustaja" jne.). Eritysesti niissä
tapauksissa, joissa kehittäjät tai ylläpitäjät vaativat jotakin
ominaisuutta tämä olisi hyvä merkitä.

> "Ylläpitäjä haluaa logit katseltavaksi järjestelmään X, jotta virhetilanteiden selvittäminen on helppoa."

Erityisesti rooli sanat kannattaa pitää mahdollisimman lyhyinä. Ne
toistuvat samoina tarinoiden alussa ja ihmissilmä pitkälti sivuuttaa
ne. Englannin kielessä dev ja ops lyhenteet voivat olla käteviä
kehittäjistä ja ylläpitäjistä puhuttaessa. Oleellista on kuitenkin
aina käyttää samaa termiä samasta roolista. Projektin tulee omalla
kohdallaan miettiä, mitkä roolit ovat järjestelmälle oleellisia.

## Tekniset tehtävät

Tekniset tehtävät kirjoitetaan käyttäjätarinoiksi, jotta
kuka-mitä-miksi -mietintä tulee tehtyä ja kirjattua. Tämä voi johtaa
välillä hiukan kankeisiin tarinoihin. Lukijan kannalta on kuitenkin
yksinkertaisinta, että tehtävinen muoto ei merkittävästi muutu
tehtävästä toiseen siiryttäessä.

> "Kehittäjä haluaa JMXän olevan käytössä tuotannossa, jotta järjestelmän metriikka on nähtävillä."

Tämä on todennäköisesti tuotteomistajallekin selkeämmin ymmärrettävä
asia kuin lakoneinen "JMX tuotantoon" -tehtävä.

## Bugit

Bugeja, eli järjestelmän virheellistä toimintaa, on hankala kuvata
käyttäjätarinoilla. Käyttäjätarinat kertovat miten jäjestelmän pitäisi toimia.

Käytännössä käyttäjätarinan toteutus on ollut
puuttellinen, jos toiminnallisuuteen liittyy virheellistä
toimintaa. Lähtökohtaisesti bugit tulisi korjata ennen kuin
toteutuksen kanssa mennään tuotantoon. Tarina ei valmistu ennen kuin
se on kunnolla toteutettu. Näissä tilanteissa varsinaista bugia ei ole
tarpeen merkitä vaan tarinaan kirjataan havaitut puutteet.

Joskus syntyy tilanteita, että uuden toiminnallisuuden toteuttaminen
muuttaa jo kerran toteutettuja ominaisuuksia ei-toivotulla
tavalla. Tällaisessa tilanteessa on kirjattava bugi. Oleellista
bugissa on vähintään kirjata

 1. Miten järjestelmä toimii nyt?
 2. Miten järjestelmän pitäisi toimia?
 
Esimerkiksi:

 > "Bug: Nappula on vihreä, pitäisi olla punainen."
 
Bugeja käsiteltäessä on hyvä huomata, että bugi ja sen korjaaminen
voivat eri tehtäviä. Erityisesti monimutkaisissa järjestelmissä voi
syntyä tilanne, jossa järjestelmässä vika on niin syvällä, että sen
korjaaminen ei onnistu yhdellä askeleella. Tällöin korjaukset tulee
kirjoittaa käyttäjätarinoilla.

 > "Bug: Järjestelmä kaatuu täydenkuun aikaan, pitäisi toimia myös kuutmolla."
 >  - "Kehittäjä haluaa järjestelmän käyttävän samaa aikavyöhykettä, jotta vertailuissa vältytään virheiltä."
 >  - "Kehittäjä haluaa tietokantaan auringon asennolle oman tilan, jotta vuorokaudenaikaa ei tarvitse arvata."
 >  - "Kehittäjä haluua säilyttää Kustaa Vilkunan Almanakasta tulevan kuun tilan, jotta oman laskentaa ei tarvitse ylläpitää."
 
Tämä tekee tuoteomistajallekin selväksi, mitä askelia on otettava
bugin korjaamiseksi. Mikropalveluiden aikakaudella on myös
mahdollista, että bugin korjaaminen vaatii muutoksia useaan
järjestelmään. Nämä korjaukset menevät mahdollisesti hyvin eri aikaan
tuotantoon. Tilanne mutkistuu, jos tällaiset korjaukset eivät
ensimmäisellä kerralla onnistu vaan niitä joudutaan vielä säätämään.
Selkeintä on, että konkreettiset tehtävät ovat omia tarinoitaan.


