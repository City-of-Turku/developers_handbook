[Takaisin päätasolle](./README.md)

# Kehityksen vaiheet

Turun ohjelmistokehitys tapahtuu inkrementaalisella ja iteratiivisella kehitysmallilla
seuraavissa toisistaan erillisissä vaiheissa.

 * Kehitys
 * Laadunvalvonta
 * Tuotanto

Kehitysvaiheen, jota tämä dokumentti pääasiassa käsittelee, tarkoituksena on
selvittää toteutukselle asetettavat vaatimukset ja laatia niiden mukainen
ratkaisu. Kehitys tapahtuu 2 viikon sprinteissä
(kts. [kehitysmalli](./projektinhallintamalli.md)), jonka jälkeen julkaisu
siirtyy laadunvalvonnan kautta tuotantoon. Laadunvarmistuksen ja
tuotantopäivityksen rinnalla käynnistyy uusi kehitysprintti.

Kehitys kannattaa lomittaa siten, että laadunvarmistuksesta ja tuotannosta saatu
palaute pystytään hyödyntämään tehokkaasti. Uusi sprintti on voitava aloittaa
ilman tätä palautetta. Toisaalta palaute on voitava hyödyntää seuraavassa
sprintissä. Iteratiivisen kehitysmallin voima on juuri tässä palautesilmukassa
ja se kannattaa hyödyntää täysimääräisesti. Mitä aikaisemmassa vaiheessa
palautetta aletaan saamaan sitä helpompi projektia on ohjata. Koodit on syytä
viedä tuotantoon heti ensimmäisestä sprintistä lähtien. Tällä tavalla saadaan
selville, että tuotantoon meneminen on ylipäätään mahdollista. Tuoteomistajan on
varmistettava, että laadunvarmistuksen ja tuotannon resurssit ovat riittäviltä
osin käytettävissä heti alusta alkaen.

On tärkeää huomata, että tuotantoon viemisen ei tarvitse automaattisesti
tarkoittaa julkaisemista. Ne kannattaa erottaa toisistaan. Järjestelmä
kannattaa suunnitella siten, että uusia ominaisuuksia voidaan viedä tuotantoon
piilossa käyttäjiltä. Tarvittaessa ominaisuus voidaan julkaista aluksi
esimerkiksi rajoitetulle käyttäjäjoukolle ja ongelmien ilmetessä kytkeä nopeasti
taas pois käytöstä.


