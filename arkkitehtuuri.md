[Takaisin päätasolle](./README.md)

# Arkkitehtuuri

Turun kaupungin tietojärjestelmät koostuvat pääasiassa monoliittisella
arkkitehtuurilla toteutetuista tietyn sovellusalueen järjestelmistä, joiden
välillä on löyhä integraatio. Karkeasti järjestelmä on kahtiajakoinen. Se
koostuu kaupunkien välisen yhteiskehittämisen tuottamista avoimen lähdekoodin
palveluista sekä [palveluväylän](https://knowledge.solita.fi/x/CROlBw)
palveluista. Avoimen lähdekoodin palvelut löytyvät
[githubista](https://github.com/City-of-Turku).

Tyypillinen tapa järjestelmien väliseen kommunikaatioon on HTTP-protokollan yli
välitetty JSON-muotoinen data. Järjestelmä käyttää [Backend for
Frontend](https://akfpartners.com/growth-blog/backend-for-frontend)-lähestymistapaa. SOA-arkkitehtuurista
poiketen taustapalveluita ei kuitenkaan ole useassa kerroksessa.

## Tunnistautuminen

Järjestelmät käyttävät kirjautumiseen
[Tunnistamo-palvelua](https://github.com/City-of-Turku/tunnistamo).



