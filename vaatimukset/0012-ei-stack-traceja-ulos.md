[Takaisin päätasolle](./../README.md)

# Virheilmoitukset eivät saa paljastaa järjestelmän sisäistä toimintaa

Järjestelmä ei saa tuottaa käyttäjän näkyville tietoa ohjelman sisäisestä
tilasta esimerkiksi tulostamalla ns. stack trace ruudulle virheen sattuessa.
Sisäisen tilan tutkiminen helpottaa mahdollisten haavoittuvuuksien löytämistä.
Lisäksi vaikka tiedoista ei olisikaan varsinaista hyötyä, oletusvirheilmoitusten
käyttäminen antaa hyökkääjälle kuvan, että järjestelmän virheen käsittelyä ei
ole mietitty kunnolla. Tämä voi houkuttaa hyökkääjiä järjestelmän kimppuun.
