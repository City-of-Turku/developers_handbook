[Takaisin päätasolle](./../README.md)

# Salasanoja ei saa laittaa versionhallintaan suojaamattomana

Versionhallintaan ei lähtökohtaisesti tallenneta salasanoja ollenkaan. Tietyissä
tilanteissa provisiointi (ympäristön automaattinen pystyttäminen) voi vaatia
salasanojen tallentamista koodien yhteyteen. Tällaisessa tilanteessa salasanat
tulee salata algoritmilla, jonka salausavaimen vahvuus on vähintään 128
bittiä. Tällaisessa tilanteessa on myös mietittävä kuinka salausavaimen jakelu
ja kierrättäminen hoidetaan turvallisesti. Salausavainta ei saa tallentaa
versionhallintaan.

