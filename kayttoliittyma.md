[Takaisin päätasolle](./README.md)

# Käyttöliittymä

Sovellusten käyttöliittymän suunnittelussa sovelletaan
ns. mobile-first-lähestymistapaa. Sovellus suunnitellaan sulavasti käytettäväksi
pienehköllä kosketusnäytöllä. Kuitenkin, jos tilaa on tarjolla enemmän,
sovelluksen tulee osata sitä myös hyödyntää. Lähtökohtana ruudun koolle
käytetään iPhone 5:n ruutua (1136×640).

[Saavutettavuusvaatimukset](./vaatimukset/0029-saavutettavuustaso-on-wcag-1-2-aa.md) tulee
huomioida heti kehityksen alusta lähtien. Käyttöliittymät tulee testata
esteellisyysnäkökulmat huomioiden normaalin kehityksen ohessa. Hyviä työkaluja tähän ovat
muun muassa

 - Selainliitännäiset Wave ja aXe.
 - Ruudunlukuohjelmat
   - Orca (Linux)
   - NVDA (Windows)
   - Voiceover (iOS)
   - Talkback (Android)

Selaimelle tehtävien toteutusten on tuettava seuraavien selainten alle vuoden
vanhoja versioita.

 - Microsoft Edge
 - Google Chrome
 - Firefox
 - Safari
 - Opera

 

