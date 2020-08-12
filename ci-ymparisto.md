[Takaisin päätasolle](./README.md)

# CI-ympäristö

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
