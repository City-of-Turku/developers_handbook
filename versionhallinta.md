[Takaisin päätasolle](./README.md)

# Versionhallinta

## Gitflow

Projektien lähdekoodit, ja muut tarpeelliset resurssit, versioidaan
git-työkalulla. Gitin käytössä käytetään
ns. [Gitflow-lähestymistapaa](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). Kehitys
tapahtuu aina omassa haarassaan, joka lopulta liitetään `develop`-haaraan. Kun
halutut ominaisuudet on saatu kuntoon `develop` haarassa, julkaisu erotetaan
omaksi haarakseen. Lopulta julkaisuhaara liitetään liitetään `master`-haaraan ja
julkaistaan

Versiot tägätään versionhallintaan muodossa "v1.2.3". Julkaisu
viimeistellään haarassa `release/v1.2` (huomaa, että viimeinen
ns. patch-versionumero puuttuu).  Kun julkaisu on täysin valmis se
liitetään `master`-haaraan ja julkaisuhaara suljetaan.

Jos tuotannon versiota on paikattava julkaisusyklin ulkopuolella
(ns. hotfix), aloitetaan korjaaminen tägätystä versiosta käyttäen
haaraa, `release/v1.2`.  Korjauksen ollessa valmis versio julkaistaan
normaalisti. Haara liitetään `master`-haaraan lisäksi `develop`-haaraan.

## Pull requestit

Kun koodia ollaan liittämässä `develop`-haaraan, se on tehtävä pull
requestin (PR) kautta. PR:n otsikon ja kuvauksen tulee noudattaa PR:n muotoiluohjeistusta
(kts. [PR template](./docs/pull_request_template.md)) 
Tullakseen liitetyksi koodi tarvitsee Turun kaupungin teknisen projektipäällikön 
sekä vähintään yhden tiiminjäsenen puollon. Tämän lisäksi CI-ajon on mentävä lävitse
(kts. [CI-ympäristö](./ci-ymparisto.md))

PR:n yhteydessä on tärkeä huomata, että tarkoituksena on
yhteisesti nostaa koodin laatua. Kyseessä ei ole vastakkainasettelu,
jossa toteuttaja yrittää saada omat tekeleensä mahdollisimman nopeasti
hyväksytyksi. Jos PR hyväksytään ilman kommentin kommenttia, kukaan ei
todennäköisesti oppinut mitään. Katselmoijien tehtävänä on tarjota
tuoreet silmäparit, jotka eivät ole vielä sokaistuneet toteuttajan
keräämistä oletuksista.

Katselmoijien tulee tarkistaa, että PR sisältää vain tarpeelliset muutokset ja
ns. commit-viestit on kirjoitettu oikein ja kuvaavasti. Kaikkia projektissa
sovittuja muotoseikkoja on noudatettava. Tuotetun koodin pitää olla testattua,
yksinkertaista, selkää ja toimivaa. Jos jotakin mekaniikkaa on muutettu,
dokumentaatio sekä muut resurssit on myös päivitettävä. Esimerkiksi jos
projektin kääntäminen muuttuu, tulee readme-tiedostoa muuttaa kuvaamaan uusi
tilanne. Tämän lisäksi mahdolliset CI-työt on päivitettävä toimimaan uuden
systeemin kanssa.

Ei ole olemassa mitään yksiselitteistä mittaria koodin laadulle. Nyrkkisääntönä
on, että jos katselmoijalle joudutaan selittämään, miten koodi toimii, koodin
laatu ei ole riittävällä tasolla.

## Commit-viestit

Versionhallintaan tehtävien muutosten kommenttien on viitattava
tehtävänhallinan tehtävään. Itse kuvaus kirjoitetaan muodossa, joka
kuvaa tuotteen toiminnan muutoksen jälkeen. Kommentit kirjoitetaan
englanniksi.

    User can remove unnecessary address from address list (JIRA-1234)

Versionhallinta kommenteista on siivottava toisiaan korjaavat muutokset pois
PRän hyväksymistä. Seuraavan kaltaisen historian liittäminen ei ole
hyväksyttävää.

    3: Added file forgoten from last commit
    2: Fix'd topic that was missing from previous commit
    1: All topics are capitalised

Muutokset tulee liittää yhdeksi ehjäksi muutokseksi (kts. [git-dokumentaatio](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)):

    1: All topics are capitalised (JIRA-2345)

Tämä ei tarkoita, että kaikki muutokset olisi syytä yhdistää. Erillisiä
muutoksia on syytä käyttää, jotta työn vaiheistus ja oikeellisuuden
tarkastaminen on mahdollista. Esimerkiksi tiedoston sisennyksien uudelleen
järjestelyä ja varsinaista muutosta ei saa tehdä samassa
muutoksessa. Katselmoijan on käytännössä mahdoton lukea, mitä on muuttunut. Sen
sijaan muutos pitää toteuttaa toistensa päälle rakentuvilla peräkkäisillä
muutoksilla.
