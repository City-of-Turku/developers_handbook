[Takaisin päätasolle](./README.md)

# CI-ympäristö

Turun kaupungin palveluvälän integraatioalusta on kuvattu
[Confluencessa](https://knowledge.solita.fi/x/CYz9Bg). Palveluväylään
integroituville Javalla tehdyille web-sovelluksille on valmis CI-putki olemassa.
Muut palvelut joutuvat rakentamaan sellaisen itse. Työkaluna voi käyttää
esimerkiksi [Travis CI:tä](https://travis-ci.org/).

Rakennettaessa CI-putkea tulee huolehtia seuraavista asioista
 - Pull requesteille on oma CI-ajo.
 - Sovellus julkaistaan CI-järjestelmän kautta.

Pull reqeust -ajon tulee testata koodien toimivuus mahdollisen mergen jälkeen. Pelkkä
haaran testaaminen yksinään ei riitä. Tarkoitus on varmistaa, että koodit
toimivat PR:n hyväksymisen jälkeenkin.

Sovelluksen julkaistava muoto rakennetaan CI-järjestelmässä. Tällä varmistutaan
siitä, että käännösympäristö on vakioitu. Kehittäjät eivät käännä ohjelmasta
julkaisuversioita omilla koneillaan. Julkaisun voi kytkeä tapahtumaan, kun
koodia liitetään projektin master-haaraan.
