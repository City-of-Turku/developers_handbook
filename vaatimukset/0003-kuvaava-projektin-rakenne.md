[Takaisin päätasolle](./../README.md)

# Projektin rakenteen ja nimeämisen pitää kuvastaa sovelluksen toimintaa

Tyypillinen tapa rakentaa projekti on jakaa projekti käytetyn
frameworkin mukaisiin osiin. Nämä nimet ovat hyvin geneerisiä ja
johtavat esimerkiksi seuraavankaltaiseen hakemistolistaukseen
projektin päätasoilla.

    public_transportation/
       views/
       controllers/
       repositories/

Listaus sopisi mihinkä tahansa järjestelmään. Se ei kerro lukijalle
järjestelmästä yhtään mitään. Toinen yhtä informatiivinen tapa on
luetella projektissa käytettävät työkalut ja jakaa koodi niiden alle.

    public_transportation/
        packer/
        cloudformation/
        ansible/
        python/
        java/
        react/

Kumpaakin tapaa tulisi välttää ja käyttää korkeintaan syvällä
projektin hakemistorakenteessa. Projektin rakenteen tulisi pyrkiä
kommunikoimaan, mistä sovelluksessa on kysymys. Esimerkiksi
seuraavasti:

    public_transportation
        timetables/
            editor/
            viewer/
   
Luonnollisesti käytetyt työkalut ja tekniikat luovat nimeämiseen omat
rajoitteensa. Järkevän rakenteen luomiseen kannattaa kuitenkin käyttää
vaivaa, koska koodia kirjoitetaan viime kädessä ihmiselle. Tietokone
ymmärtää koodin rakenteesta riippumatta.
