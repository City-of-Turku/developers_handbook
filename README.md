# Turun kaupungin ohjelmistokehittäjän käsikirja

Tästä versionhallinasta löytyvät Turun kaupungin
ohjelmistokehityksessä käytettävät käytännöt kehittäjän
näkökulmasta. Korjauksia virheisiin ja yleisiä parannuksia voi
toimittaa tekemällä pull requestin.

## Käytänteet ja työkalut

 * [Ohjelmistokehityksen vaiheet](./vaiheet.md)
 * [Projektinhallintamalli (Scrum)](./projektinhallintamalli.md)
 * [Viestintä](./viestinta.md) 
 * [Koodin lisensointi](./koodin-lisensointi.md)
 * [Dokumentaatio](./dokumentaatio.md)
 * [Versiointi](./versiointi.md)
 * [Tehtävienhallinta](./tehtavienhallinta.md)
 * [Versionhallinta](./versionhallinta.md)
 * [Definition of Done](./definition-of-done.md) 
 * [Ohjelmointikielet](./ohjelmointikielet.md)
 * [Käyttöliittymä](./kayttoliittyma.md)
 * [Arkkitehtuuri](./arkkitehtuuri.md)
 * [Yhteiskehittäminen](./yhteiskehittaminen.md)
 * [CI-Ympäristö](./ci-ymparisto.md)
  
## Vaatimukset

###  Koodin laatu

 * [Projektilla on oltava readme tiedosto](./vaatimukset/0001-readme-vaaditaan.md)
 * [Projektin kääntämisen on oltava toistettavaa](./vaatimukset/0002-toistettavat-buildit.md)
 * [Projektin tiedosto- ja hakemistorakenteen on oltava kuvaava](./vaatimukset/0003-kuvaava-projektin-rakenne.md)
 * [Väärin muotoiltujen lähdekooditiedostojen pitää estää projektin kääntyminen](./vaatimukset/0004-virheellinen-muotoilu-estaa-buildin.md)
 * [Yksikkötestien on oltava nopeita](./vaatimukset/0005-nopeat-yksikkotestit.md)
 * [Kaikki koodi tuotetaan kirjoittamalla testi ensin](./vaatimukset/0006-koodi-kirjoitetaan-tddlla.md)
 * [Testien on katettava kaikki koodi](./vaatimukset/0007-yksikkotestien-kattavuus.md) 
   
### Suorituskyky

 * [Järjestelmän on vastattava käyttäjälle alle 500 ms](./vaatimukset/0008-vastaa-riittavan-nopeasti.md) 
   
### Tietoturva

 * [Järjestelmän turvallisuus ei saa perustua toimintalogiikan salassapitämiseen](./vaatimukset/0009-sekavuus-ei-tuo-tietoturvaa.md)
 * [Salasanoja ei saa laittaa versionhallintaan suojaamattomana](./vaatimukset/0010-salasanat-on-salattava-versionhallinassa.md)
 * [Salasanojen vertaileminen on tehtävä hash-arvojen avulla](./vaatimukset/0011-salasanoja-verrataan-hash-arvoilla.md)
 * [Sisään tuleva data on validoitavat](./vaatimukset/0012-input-on-validoitava.md)
 * [Virheilmoitukset eivät saa paljastaa järjestelmän sisäistä toimintaa](./vaatimukset/0012-ei-stack-traceja-ulos.md)
 * [Virheilmoituksen pitää sisältää tunniste virhetilanteeseen](./vaatimukset/0013-tunniste-virheeseen.md)
 * [Varmuuskopiot eivät saa pitää sisällään salasanoja selväkielisenä tai salattuna. Suolatut hashit ovat ok](./vaatimukset/0014-ei-salasanoja-varmuuskopioihin.md)
 * [Järjestelmä on voitava palauttaa toimintaan versionhallinnasta](./vaatimukset/0015-ei-varmuuskopioita-tuotantopalvelimista.md)
 * [Liikenne on salattava vähintään TLS 1.2](./vaatimukset/0016-vahintaan-tls-1-2.md)
 * [Ulos menevä data on siistittävä](./vaatimukset/0017-tuloste-on-siistittava.md)
 * [Varmuuskopioista on voitava palauttaa päivän tarkkuudella alla 2 kk takainen tilanne](./vaatimukset/0018-palautus-mahdollinen-2kk-taaksepain.md)
 * [Juoksevia (ja muita ennustettavia) tunnisteita tulee välttää](./vaatimukset/0019-ei-juoksevia-tunnisteita.md)
 * [CSRF-hyökkäykset pitää estää](./vaatimukset/0020-ei-csrf-hyokkayksia.md)
   
### Tietosuoja

 * [Käyttäjän (henkilö)tietoja ei saa logittaa tarpeettomasti](./vaatimukset/0021-valta-henkilotietojen-logitusta.md)
 * [Käyttäjän tietojen katsomisesta on pidettävä kirjaa](./vaatimukset/0022-tietojen-katsomiset-on-kirjattava.md)
 * [Mahdollisista tietoturvaloukkauksista on ilmoitettava viipymättä](./vaatimukset/0023-tietoturvaloukkauksista-on-ilmoitettava.md)
 * [Käyttäjän tietoja ei saa tallenta ilman lupaa](./vaatimukset/0024-ilman-lupaa-ei-saa-tallentaa.md)
 * [Käyttäjän tiedot on saatava ulos järjestelmästä](./vaatimukset/0025-tiedot-on-saatava-ulos.md)
 * [Järjestelmän on mahdollistettava käyttäjien tietojen tuhoaminen](./vaatimukset/0026-tiedot-on-voitava-poistaa.md)
 * [Projektien tulee tarjota metriikka statsd-muodossa](./vaatimukset/0027-statsd-metriikat.md)
 * [Logi tuotetaan JSON-muodossa stdout-virtaan](./vaatimukset/0028-json-logging-stdouttiin.md)
 
### Saavutettavuus

 * [Järjestelmien saavutettavuuden taso on vähintään WCAG 2.1 AA](./vaatimukset/0029-saavutettavuustaso-on-wcag-2-1-aa.md)
 
# Muuta ajattelemisen aihetta

 * [The twelve-factor methodology](https://12factor.net/)
 * [The Principles of Clean Architecture by Uncle Bob Martin](https://www.youtube.com/watch?v=o_TH-Y78tt4)
 * [Näin keräät ja käytät lokitietoja](https://www.kyberturvallisuuskeskus.fi/fi/ajankohtaista/ohjeet-ja-oppaat/nain-keraat-ja-kaytat-lokitietoja)




























