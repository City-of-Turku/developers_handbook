[Takaisin päätasolle](./README.md)

# Ohjelmointikielet

## Java

Javan käyttöä pyritään vähentämään Javan lisenssointiin liittyvien riskien
takia. Javalla tehtävien toteutusten on toimittava OpenJDK-jakelulla tai muulla
laajasti tuetulla ilmaisella toteutuksella.

## Python

Python on Turun kaupungin pääkieli taustatoteutuksiin. Pythonista
käytetään versiota 3.6.x.

## JavaScript

Palvelin toteutuksissa käytetään node.js versiota 12.x. Selaimessa
käytetään EcmaScript-tasoa 6, koodi ajetaan ns. strict-tilassa ("use
strict"). Totetusten on tuettava seuraavien selainten alle vuoden
vanhoja versioita

 - Microsoft Edge
 - Google Chrome
 - Firefox
 - Safari
 - Opera

# Lähdekoodin muotoilu

Lähdekoodin muotoilun tarkoituksena on, että riippumatta koodin kirjoittajasta
koodi näyttää samalta.  Koodi kirjoitetaan UTF-8 koodausta käyttäen.  Riivit
päättyvät rivinvaihtoon (0x10). Koodin tuottamiseen käytetään pääasiassa Visual
Studio Codea. Saman editorin käyttäminen helpottaa yhtenäisen mutoilun
tuottamista.

## Java

Koodi muotoillaan [Googlen
käytänteiden](https://google.github.io/styleguide/javaguide.html)
mukaan (katso myös
[google-java-format](https://github.com/google/google-java-format)).
Muotoilun pakottamiseen käytetään Maven lisäosaa
[fmt-maven-plugin](https://github.com/coveooss/fmt-maven-plugin).
Visual Studio Coden käyttön löytyy myös
[ohjeet](https://www.sethvargo.com/using-google-java-format-with-vs-code/).


## Python

Toteutuksissa käytetään vähintään 3.6 versiota. Koodaustyyli on
[PEP8](https://www.python.org/dev/peps/pep-0008/) mukainen. Tyylin tarkastukseen
käytetään [pylint](https://pylint.org/)-ohjelmaa.

## JavaScript

Käytössä on [airbnb:n käyttämä tyyli](https://github.com/airbnb/javascript). Sen
tarkastamiseen käytetään `eslint`:n lisäosaa
[eslint-plugin-airbnb](https://www.npmjs.com/package/eslint-config-airbnb).
Lisäksi reactin kanssa käytetään
[eslint-plugin-react](https://www.npmjs.com/package/eslint-plugin-react)-lisäosaa.

## SQL

SQL-koodi kirjoitetaan [SQL Style Guide](https://www.sqlstyle.guide/) mukaisesti.
