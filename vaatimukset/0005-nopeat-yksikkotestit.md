[Takaisin päätasolle](./../README.md)

# Yksikkötestien on oltava nopeita (ajoaika alle 2 minuuttia).

Järjestelmän yksikkötestien ajamiseen tulisi kestää vain muutamia
sekunteja. Ison järjestelmän ollessa kyseessä testien ajamiseen käytetty aika
luonnollisesti kasvaa. Aika ei kuitenkaan saa ylittää 2 minuuttia.

Testiajat pysyvät lyhyenä, kun testien ei tarvitse toimiakseen jatkuvasti
käyttää oikeaa tietokantaa, tiedostojärjestelmää yms. ulkoisia
resursseja. Ulkoiset resurssit tulee piilottaa rajapintojen taakse, jotta testit
voivat todellisen toteutuksen sijasta käyttää testaamiseen paremmin soveltuvaa
toteutusta. Sen sijaan, että jokainen testi testaisi sivutuotteenaan esimerkiksi
tietokannan yleistä toimintaa, kannattaa tietokannan toimintaan liittyvät testit
jakaa omaksi kokonaisuudekseen.

Testiajan kasvaminen aiheuttaa aluksi kehittäjän keskittymisen herpaantumisen
testiajon valmistumista odotellessa. Työtehon säilyttämisen vuoksi testejä
ajetaan harvemmin ja muutosten koko kasvaa. Testien epäonnistuessa suuremmasta
muutoksesta on vaikeampi löytää virheen aiheuttanutta kohtaa. Kohta jokaisen
muutoksen jälkeen ei enää edes voida ajaa kaikkia testejä. Koska kaikkia testejä
ei enää ajeta jatkuvasti, testejä lisätään huomioimatta kokonaistestiajan
jatkuvaa kasvua. Lopulta osa testeistä siirretään ajettavaksi vain
CI-ympäristössä. Palautteen saamiseen tulee pidempi ja pidempi viive, mikä näkyy
jatkuvana kehittämisen vaikeutumisena.
