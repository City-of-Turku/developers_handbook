[Takaisin päätasolle](./README.md)

# Projektinhallintamalli

Riippumatta toteutustekniikasta projektilla tulee olla seuraavat resurssit käytössään.

 * Versionhallinta
 * Tehtävienhallinta
 * CI-ympäristö
 * Testiympäristö
 * Tuotantoympäristö

Kehitystiimin vastuulla on huolehtia, että nämä ovat kunnossa.

Kehitystyössä käytetään
[Scrum-viitekehystä](https://fi.wikipedia.org/wiki/Scrum). Jos
menetelmä itsesään on tuntematon voi siihen tutustua esimerkiksi
[scrum.org](https://www.scrum.org/resources/what-is-scrum)-sivustolla. Menetelmästä
on olemassa myös paljon kirjallisuutta. Seuraavassa käydään lävitse
menetelmän soveltaminen Turun kaupungin toimintaympäristössä.

Sprintin pituudeksi on sovittu 2 viikkoa. Sprintti aloitetaan
maanantaina aloituspalaverilla ja lopetetaan seuraavan viikon
perjantaina tulosten katselmoinnilla, jota seuraa retrospektiivi.

Tuoteomistajan (product owner) vastuulla on, että työlista (backlog)
on kunnossa ja ajan tasalla. Viimeistään sprintin alkaessa tehtävillä
on oltava kuvaus ja kokoarvio. Yleensä tämä vaatii vaihtelevan määrän
suunnittelupalavereita sprintin aikana. Viime kädessä tuoteomistajan on
pidettävä huoli, että hän saa tehtäviin riittävästi palautetta
tiimiltä.

Jokaisen tiimin ja tuoteomistajan toimintaa tukemassa on scrum master,
jonka vastuulla on huolehtia Scrumin soveltamisessa päivittäisessä
työskentelyssä. Tarvittaessa hän järjestää menetelmän mukaisia
tilaisuuksia (esim. aloitus-, suunnittelu-, lopetuspalavereita ja
retrospektiivejä). Palaverit ovat kuitenkin tiimin vastuulla.

Tiimi vastaa siitä, että se saa sprintin aikana lupaamansa asiat
valmiiksi. Tavoite on, että kaikki on valmista sprintin
päätöspalaveriin mennessä. Toteutukset ovat käytössä
testiympäristössä, jossa tuoteomistaja voi ne hyväksyä. Tiimin
suorituskyvyn laskennan kannalta kannalta tarina on joko täysin
toteutettu tai täysin toteuttamatta. Projektitiimi tuottaa ns. [burn
down -kaavion](https://en.wikipedia.org/wiki/Burn_down_chart) sprintin
etenemisestä. 

Vaikka toteutukset eivät lähtökohtaisesti saa venyä sprintin ylitse,
väistämättä näin joskus käy. Tilanteesta tulee oppia ja tehdä
korjaavat toimenpiteet, jotta tilanteelta vältyttäisiin jatkossa.
Tehtävän jäädessä kesken tulee ennen seuraavaan sprinttiin siirtoa
miettiä onko asian tekeminen vielä oikeasti tarpeellista. Jos on, tulee
miettiä, miten tämän tehtävän venyminen myös seuraavan sprintin yli voidaan
välttää. Tarvittaessa tehtävä voidaan jakaa hallittavampiin osakokonaisuuksiin.


