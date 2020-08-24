[Takaisin päätasolle](./README.md)

# Arkkitehtuuri

> **---Kommentti---**
>
>  - Tässä olisi hyvä viitata järjestelmäkuvaukseen tjms.
>  -  Tämän kirjoittamiseen tarvitaan enemmän tietoa asiakaan ympäristöistä.
>  - Tunnistamo repon pitäisi sisältää tieto siitä, miten tunnistamo otetaan sovellukseen käyttöön
>  - EU GDPR vaatimukset (käyttäjätietojen poisto ja kyseleminen?
> - Jos tunnistamolla mennään järjestelmiin sisään miten uloskirjautuminen on hoidettu?
> - Miten autorisaatio ja ryhmien hallinta on toteutettu?
> **---Kommentti---**

Turun kaupungin tietojärjestelmät koostuvat monoliittisella
arkitehtuurilla toteutetuista tietyn sovellusalueen järjestelmistä,
joiden välillä on löyhä integraatio. Järjestelmät keskustelevat
toistensa kanssa suoraan JSON-muotoisella datalla HTTP-protokollaa
käyttäen.

Järjestelmä käyttää [Backend for
Frontend](https://akfpartners.com/growth-blog/backend-for-frontend)-lähestymistapaa. SOA
arkkitehtuurista poiketen taustapalveluita ei kuitenkaan ole useassa
kerroksessa.


## Tunnistautuminen

Järjestelmät käyttävät kirjautumiseen [Tunnistamo-palvelua](https://github.com/City-of-Turku/tunnistamo) (*Onko oikea repo?*).

