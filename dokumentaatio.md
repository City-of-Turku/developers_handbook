[Takaisin päätasolle](./README.md)

# Dokumentaatio

Versionhallinnan tulee sisältää `readme.md`-tiedosto, joka kuvaa: mistä
projektissa on kyse ja miten projektin kehitysympäristö pystytetään.  Tämän
lisäksi on hyvä kertoa mahdollisesti käytetyt tekniikat, projektin rakenne ja
arkkitehtuuri. Erityisesti on syytä kertoa, jos toteutuksessa on poikettu
yleisistä tavoista tai käytänteistä.

On hyvä pyrkiä siihen, että projekti on ymmärrettävä sellaisenaan. Tämä
tarkoittaa sitä, että lukijan tulisi yllättyä kohtaamistaan asioista
mahdollisimman vähän (["the principle of least
astonishment"](https://en.wikipedia.org/wiki/Principle_of_least_astonishment)).
Projektin dokumentaation tulisi saada lukija heti oikeille raiteille. 

Koodin seassa olevaa dokumentaatiota ("kommentteja") tulee käyttää vain
tarvittaessa. Kommenteissa tulisi keskittyä kertomaan, miksi jokin asia tehdään,
ei miten se tehdään. Koodi itsessään on kertomus siitä, miten asia tehdään.
Jotta tämä onnistuu, on koodin oltava selvästi virheetöntä ja ymmärrettävää.

Dokumentaatiota kirjoittaessa tulee miettiä lukijan tarpeita. Minkälainen
kohdeyleisö tekstiä pääasiassa lukee ja mitkä asiat heitä
kiinnostavat. Tyypillisiä asioita, jotka usein jätetään dokumentoimatta ovat
 - missä tilanteessa, miten ja miksi ratkaisua on tarkoitettu käytettäväksi,
 - parametrien ja paluuarvojen merkitys ja arvoalueet, 
 - käyttäytyminen poikkeustilanteissa,
 - ratkaisussa käytetyt yleisesti tunnetut algoritmit,
 - miksi juuri tämä algoritmi on valittu,
 - säieturvallisuus tai sen puute.
 
Kaikki dokumentaatio kannattaa sijoittaa mahdollisimman lähelle koodia eli
samaan versiohallintaan itse ohjelman kanssa. Muutettaessa ohjelman toimintaa
tulisi dokumentaatio muuttaa samalla kertaa. Tätä on vaikea valvoa, jos muutosta
ei voida tehdä samassa pull requestissa. Ohjekirjat yms. kannattaa pyrkiä
julkaisemaan projektin versionhallinnasta sen sijaan, että niitä pidettäisiin
yllä erillisinä dokumentteina jossakin muualla.




