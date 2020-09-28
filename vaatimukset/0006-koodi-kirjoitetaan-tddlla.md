[Takaisin päätasolle](./../README.md)

# Kaikki koodi tuotetaan kirjoittamalla testi ensin

Koodia tuotetaan _aina_ seuraavalla syklillä:

 1. Tehdään testi halutulle toteutukselle
 2. Ajetaan testi. Testiajon tulee epäonnistua (toteutus puuttuu).
 3. Toteutus
 4. Ajeteaan testit. Testiajo onnistuu. (Jos ei palataan edelliseen kohtaan)
 6. Siistitään toteutus ja testi.
 7. Onnistunut ajo.
 5. Aloitetaan aluista.


Testin tulee olla selkeästi kirjoitettu ja sen tulee dokumentoida toteutettu
toiminnallisuus. Testikoodi on esimerkki kuinka toteutusta on tarkoitus
käyttää. Testit muodostetaan kolmesta osasta: arrange, act ja assert. Testien
nimissä pyritään seuraavaan muotoon.

    [Testattavan_metodin_nimi]_should_[haluttu_lopputulos]_when_[tilanne]
    
Jos jollakin osalla ei ole merkitystä, se voidaan jättää välistä. Samoin metodin
nimi voidaan joutua korvaamaan yleisemmällä testattavalla asialla, jotta nimi
olisi kuvaavampi.

Esimerkki testi:
    
    def display_should_return_result_when_equal_sign_has_been_entered(self):
        # Arrange
        c = Calculator()
        # Act
        c.enter("1")
        c.enter("+")
        c.enter("1")
        c.enter("=")
        result = c.display()
        # Assert
        self.assertEqual(result, "2")
        
Yksinkertaisimmissa tapauksissa arrange-osuudesta voidaan luopua.

    def upper_should_capitalize_every_letter(self):
        # Act
        result = 'foo'.upper()
        # Arrange
        self.assertEqual(result, 'FOO')
 
 
Yleensä osa kehitysvaiheessa tarpeellisista testeistä muuttuu tarpeettomiksi
toiminnallisuuden valmistuessa. Tämän takia myös testit on muokattava helposti
ymmärrettävään ja muokattavaan muotoon. Usein tämä tarkoittaa testien
yhdistämistä ja poistamista. Testit ovat dokumentaatio siitä, miten järjestelmän
on ajateltu toimivan.
