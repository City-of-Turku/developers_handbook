[Takaisin päätasolle](./../README.md)

# Ulos menevä data on siistittävä

Järjestelmän tuottamat tulosteet ovat siistittävä siten, että ulostulomuodon
syntaksia ei voida rikkoa. Hyvin yksinkertaisena esimerkkinä tuotettaessa
"-merkeillä ympäröityjä merkkijonoja on mietittävä, miten ratkaistaan tilanne,
jossa data itsessään pitää sisällään "-merkin. Yleinen tapa on sopia syntaksi,
jolla voidaan osoittaa varatun merkin olevan osa dataa (esim. \-merkki).

     "Esimerkissä "-merkki on ongelmallinen"   # Virheellinen muoto. Ei ole selvää missä jono loppuu
     "Esimerkissä \"-merkki on ongelmallinen"  # Esimerkiksi näin

Se, miten tuotettua dataa joudutaan käytännössä siistimään, riippuu paljon itse
järjestelmästä. Tyypillisiä tilanteita on SQL-kutsujen tuottaminen kantaa varten
tai HTML-sivujen rakentaminen selaimelle vietäväksi. Yleensä siistiminen
hoidetaan kirjastojen avulla. Virheet näissä tilanteissa johtavat muun muassa
[SQL-injektion](https://owasp.org/www-community/attacks/SQL_Injection) ja
[XSS-hyökkäyksen](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A7-Cross-Site_Scripting_(XSS))
mahdollisuuteen.

Logi on yksi ulostulon muoto, joka helposti sivuutetaan. Vaikka kirjasto
huolehtisi ulostulon siistimisen sinänsä voi olla, että se ei rajaa tulosteen
pituutta. Jos virhetilanteissa logitetaan käyttäjän lähettämä kutsu
sellaisenaan,voi tämä mahdollistaa hyökkäyksen, jossa logiin tuotetaan
gigatolkulla roskaa.

Viittauksissa ulkoisiin järjestelmiin tai komentorivien käskyjen tuottamisessa
on oltava myös tarkkana. Jos järjestelmä käyttää käyttäjän syötettä
huolimattomasti tiedostonimen tai linkin generoimiseen voi hyökkääjä saada ".."-
tai "/"-merkinnällä aikaan yllättäviä sivuvaikutuksia.
