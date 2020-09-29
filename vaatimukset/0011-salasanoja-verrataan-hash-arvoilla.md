[Takaisin päätasolle](./../README.md)

# Salasanojen vertaileminen on tehtävä hash-arvojen avulla

Käyttäjien salasanoja ei tallenneta selväkielisinä.  Salasanan vertaileminen
esimerkiksi sisäänkirjautumistilanteessa on tehtävä
[hash-arvojen](https://en.wikipedia.org/wiki/Hash_function) avulla.  Salasanan
hash-arvoa laskettaessa on käytettävä
ns. [suolaa](https://en.wikipedia.org/wiki/Salt_(cryptography)). Yleisesti
algoritmi näyttää seuraavalta.

    hash = hashAlgoritmi(suola+salasana)
    
Suolana voi käyttää mitä tahansa merkkijonoa, joka on jokaiselle salasanalle
yksilöllinen. Toisin sanoen suolan tulee vaihtua, jos käyttäjä vaihtaa
salasanansa. 

Hashien tuottamiseen käytetään turvalliseksi tunnettua kryptografista
funktiota. Koska hash-algoritmeista löytyy aika ajoin turvallisuusongelmia,
algoritmia joutuu tulevaisuudessa todennäköisesti vaihtamaan. Tämän takia
käytetty algoritmi on hyvä merkitä ylös. Tallennettava merkkijono voi näyttä
esimerkiksi seuraavalta.

    *sha3-256*satunnainesuola*ded5910fafe7e22b374e139b911a9fba66c5854413e78e8d6d9b273068e34bef960a9e907ce3117bbc7907673107b03d8648ca3b3bbb6c319877f71dba31dedb

Vertailu tapahtuu seuraavasti

    onkoSalasanaOikein(käyttäjä, salasana):
        algoritmi, suola, odotettuHash = lataaKannastaKäyttäjänAlgoritmiHashJaSuola(käyttäjä)
        laskettuHash = algoritmi(suola+salasana)
        return odotettuHash == laskettuHash

Suolan lisäksi voidaan käyttää
[pippuria](https://en.wikipedia.org/wiki/Pepper_(cryptography)),
asennuskohtaista salaista arvoa.

    hash = hashAlgoritmi(suola+pippuri+salasana)
    
Kannan sijaan arvo on tallennettu esimerkiksi asetustiedostoon.  Tämä
hankaloittaa (tai jopa estää) yksinkertaisien salasanojen murtamista
tilanteessa, jossa hyökkääjä on saanut hash-arvot haltuunsa varastamalla
tietokannan sisällön.


