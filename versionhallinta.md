[Takaisin päätasolle](./README.md)

# Versionhallinta

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

