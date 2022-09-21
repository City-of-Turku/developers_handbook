[Takaisin päätasolle](./../README.md)

# CSRF-hyökkäykset pitää estää

Järjestelmän on varmistuttava, että kutsua ei ole generoitu 3. osapuolen
toimesta luvatta. Esimerkiksi jos tietoja voidaan tuhota GET-pyynnöllä
osoitteeseen `/resurssi/123/delete`, voi ulkopuolinen hyökkäyssivusto saada
käyttäjän selaimen tekemään kyseisen kutsun ilman käyttäjän lupaa. Kyseisiä
hyökkäyksiä kutsutaan
[CSRF-hyökkäyksiksi](https://owasp.org/www-community/attacks/csrf).

Järjestelmän toiminta on suunniteltava siten, että selaimen
huijaaminen 3. osapuolen toimesta ei ole mahdollista. Käytännössä tätä voidaan
välttää siten, että GET-kutsut eivät koskaan muuta järjestelmän tilaa. Tämän
lisäksi voidaan joutua käyttämään erillistä kertakäyttöistä tunnistetta kutsujen
valtuuttamiseen. Tunnistetta generoitaessa on varmistuttava, että sitä ei voida
arvata ulkoapäin.

