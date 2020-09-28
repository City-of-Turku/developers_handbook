[Takaisin päätasolle](./../README.md)

# Järjestelmän turvallisuus ei saa perustua toimintalogiikan salassapitämiseen

Järjestelmän tietoturvaa mietittäessä tulee lähteä siitä, että järjestelmän
toiminta on kaikkien tiedossa. Järjestelmän tulee suunnitella siten, että
mahdolliselle murtautujalle voidaan huoletta antaa kaikki tieto järjestelmän
toiminnasta. Lähdekoodien, rajapintojen ja salausalgoritmien tunteminen ei saa
helpottaa hyökkääjän toimintaa.

Esimerkiksi tieto rajapinnan olemassaolosta ei saa mahdollistaa sen luvatonta
kutsumista.  Tämän sijaan kutsujat on tunnistettava ja valtuutettava
oikein. Tietojen salaus pitää olla rakennettu niin, että salatussa muodossa
olevat tiedot voidaan antaa hyökkääjälle (ilman mahdollisia salausavaimia) ja
kertoa miten ne on salattu, vaarantamatta tietoturvaa.
