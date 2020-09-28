[Takaisin päätasolle](./../README.md)

# Juoksevia (ja muita ennustettavia) tunnisteita tulee välttää

Järjestelmän paljastamat tiedot on hyvä pyrkiä pitämään sellaisina, että niistä
ei voi tehdä ylimääräisiä päätelmiä. Tietokannoissa tyypillisesti käytetyt
nousevat tunnisteet paljastavat yleensä ylimääräistä tietoa.

Esimerkiksi jos uuden käyttäjätunnuksen numero on 12304 tästä voidaan päätellä
käyttäjien määrää. Jos seuraavalla viikolla uuden käyttäjän tunniste on 12406
voidaan jo alkaa päättelemään kaikkien tunnusten summittaista luontiaikaa. Jos
murtautuja tietää suunnilleen ajankohdan jolloin kohde on rekisteröitynyt
järjestelmään, hän voi päätellä millä välillä kohteen käyttäjän tunniste on. Tai
kääntäen hyökkääjä voi päätellä tunnuksen luontiajankohdan
tunnisteesta. Yksinään tällaiset tiedot harvoin ovat ongelmia, mutta useista
lähteistä koostettu tieto saattaa johtaa järjestelmän suojausten ohittamiseen.

Tyypillinen tapa kiertää ongelmaa on käyttää
[UUID-tunnisteita](https://en.wikipedia.org/wiki/Universally_unique_identifier).
Merkkijonosta "08657ea1-0b6a-4338-9e59-6080c1bb1082" voi päätellä huomattavasti
vähemmän kuin esimerkiksi käyttäjänumerosta.

Tämän lisäksi arvattavat tunnisteet mahdollistavat yksinkertaisesti eri
tunnisteiden kokeilemisen. Jos on olemassa mahdollisuus, että jokin resurssi ei
ole suojattu oikein ja tunnisteen tiedetään olevan järjestysluku, hyökkääjä voi
yksinkertaisesti vain käydä tunnisteita läpi kunnes tärppää. Tämä ei käytännössä
onnistu UUIDtä käytettäessä.

