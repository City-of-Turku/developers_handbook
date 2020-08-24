[Takaisin päätasolle](./README.md)

# Versionhallinta

## Gitflow

Projektien lähdekoodit ja muut tarpeelliset resurssit versioidaan
git-työkalulla. Gitin käytössä käytetään
ns. [Gitflow-lähestymistapaa](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). Kehitys
tapahtuu aina omassa haarassaan, joka lopulta liitetään
`develop`-haaraan. Kun halutut ominaisuudet on saatu kuntoon `develop`
haarassa, julkaisu erotetaan omaksi haarakseen. Lopulta jukaistu uusi
versio liitetään `master`-haaraan.

Versiot tägätään versionhallintaan muodossa "v1.2.3". Julkaisu
viimeistellään haarassa `release/v1.2` (huomaa, että viimennen
ns. patch-versionumero puuttuu).  Kun julkaisu on täysin valmis se
liitetään `master`-haaraan ja julkaisuhaara suljetaan/.

Jos tuotannon versiota on paikattava julkaisusyklin ulkopuolella
(ns. hotfix), aloitetaan korjaaminen tägätystä versiosta käyttäen
haaraa, `release/v1.2`.  Korjauksen ollessa valmis versio julkaistaan
normaalisti. Haara liitetään sekä `master`-haaraan, että
`develop`-haaraan.

## Pull requestit

Kun koodia ollaan liittämässä `develop`-haaraan, se on tehtävä pull
requestin kautta.  Tullakseen liitetyksi koodi tarvitsee Turun
kaupungin teknisen projektipäällikön sekä vähintään yhden
tiiminjäsenen puollon.

Pull requestin (PR) yhteydessä on tärkeä huomata, että tarkoituksena on
yhteisesti nostaa koodin laatua. Kyseessä ei ole vastakkainasettelu,
jossa toteuttaja yrittää saada omat tekeleensä mahdollisimman nopeasti
hyväksytyksi. Jos PR hyväksytään ilman kommentin kommenttia, kukaan ei
todennäköisesti oppinut mitään. Katselmoijien tehtävänä on tarjota
tuoreet silmäparit, joitka eivät ole vielä sokaistuneet toteuttajan
keräämistä oletuksista.

Katselmoijien tulee tarkistaa, että PR sisältää vain tarpeelliset
muutokset ja ns. commit-viestit on kirjoitettu oikein ja
kuvaavasti. Kaikkia projektissa sovittuja muotoseikkoja on
noudatettava. Tuotetun koodin pitää olla testattu ja toimivaa. Jos
jotakin mekaniikkaa on muutettu vastaavat dokumentaatiot ja
mahdolliset muut osiot myös päivitettävä. Esimerkiksi jos projektin
kääntäminen muuttuu tulee readme-tiedosto tietysti muuttaa
ajantasalle. Tämän lisäksi mahdolliset CI-työt joudutaan pävittämään.

Ei ole olemassa, mitään yksiselitteistä mittaria koodin
laadulle. Nyrkkisääntönä on, että jos katselmoijalle joudutaan
selittämään miten koodi toimii, koodin laatu ei ole riittävällä
tasolla.

## Commit viestit

Versionhallintaan tehtävien muutosten kommenttien on viitattava
tehtävänhallinan tehtävään. Itse kuvaus kirjoitetaan muodossa, joka
kuvaa tuotteen toiminnan muutoksen jälkeen. Kommentit kirjoitetaan
englanniksi.

    User can remove unnecessary address from address list (JIRA-1234)

Versionhallinta kommenteista on siivottava toisiaan korjaavat
muutokset pois ennen koodien liittämistä päähaaraan. Seuraavan
kaltaisen historian liittäminen ei ole hyväksyttävää.

    3: Added file forgoten from last commit
    2: Fix'd topic that was missing from previous commit
    1: All topics are capitalised

Muutokset tulee liittää yhdeksi ehjäksi muutokseksi.

Toisaalta erillisiä muutoksia on syytä käyttää, jotta työn vaiheistus
ja oikeellisuuden tarkastaminen on mahdollista. Esimerkiksi tiedoston
sisennyksien uudelleen järjestelyä ja varsinaista muutosta ei saa
tehdä samassa muutoksessa. Katselmoijan on käytännössä mahdoton lukea,
mitä on muuttunut. Sen sijaan muutos pitää toteuttaa toistensa päälle
rakentuvilla peräkkäisillä muutoksilla.
