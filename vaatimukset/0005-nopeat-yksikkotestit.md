[Takaisin päätasolle](./../README.md)

# Yksikkötestien on oltava nopeita (ajoaika alle 2 minuuttia).

Järjestelmän yksikkötestien ajamiseen tulisi kestää vain muutamia sekunteja
kauempaa. Ison järjestelmän ollessa kyseessä testien ajamiseen käytetty aika
luonnollisesti kasvaa. Aika ei kuitenkaan saa ylittää 2 minuuttia.

Liian pitkä testien ajoaika johtaa helposti testien jakamisen ryhmiin, joista
vain osaa ajetaan jatkuvasti. Uudet testit lisätään aina jaettavien testien
ryhmään.  Lopulta tämä ryhmä on taas liian hidas ja sitä lähdetään
jakamaan. Samaan aikaan harvemmin ajettavat testit hankaloittavat järjestelmän
ylläpitoa, koska niiden mennessä rikki on ne kuitenkin korjattava. Järjestelmän
automaattinen testaus rapautuu pikkuhiljaa.

Testiajat pysyvät lyhyenä, kun testien ei tarvitse toimiakseen jatkuvasti
käyttää oikeaa tietokantaa, tiedostojärjestelmää yms. ulkoisia
resursseja. Ulkoiset resurssit tulee piilottaa rajapintojen taakse, jotta testit
voivat todellisen toteutuksen sijasta käyttää testaamiseen paremmin soveltuvaa
toteutusta. Sen sijaan, että jokainen testi testaisi sivutuotteenaan esimerkiksi
tietokannan yleistä toimintaa, kannattaa tietokannan toimintaan liittyvät testit
jakaa omaksi kokonaisuudekseen.
