[Takaisin päätasolle](./README.md)

# Versiointi

Projektit versioidaan [SemVer](https://semver.org/)-määrityksen mukaisesti
kolmella numerolla, jotka erotetaan toisistaan pisteellä. Erityisen tärkeää tämä
on kirjastojen sekä ulkoisia rajapintoja sisältävien tuotteiden kanssa.

Julkaistu versio merkitään versionhallintaan tägillä, joka sisältää
v-kirjaimen ja versionumeron. Version "1.2.3" merkitään tägillä
"v1.2.3".

Version tulee olla näkyvissä tuotteen paketoinnissa tai vähintään sen
sisällä. Tiedoston nimi voi olla esimerkiksi sovellus-v1.2.3.tgz. Jos
tämä ei ole, jostakin syystä mahdollista paketointi voi sisältää
tiedoston, josta versio käy ilmi. Version on hyvä näkyä myös
käyttöliittymästä helposti. 

Julkaisun versionumeron tulee yksiselitteisesti liittää paketti
johonkin versionhallinnan kohtaan. Tämä on äärimmäisen tärkeää
virhetilanteita selvitettäessä.  Kyseisen versionhallinnan kohdan on
myös aina toimittava samalla tavalla.

> **---Kommentti---**
>
>  - Tämän voisi ehkä siirtää vaatimukseksi (jos niitä halutaan käyttää)...
>  - Nykyinen käytäntö build numeron käyttämisessä julkaisemisessa on ristiriidassa yllä olevan kanssa.
>
> **---Kommentti---**
