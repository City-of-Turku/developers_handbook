
[Takaisin päätasolle](./../README.md)

# Logi tuotetaan JSON-muodossa stdout-virtaan

Järjestelmän tulee tuottaa logi suorana tulosteena normaaliin stdout:iin JSON-muodossa.

Viestin pitää sisältää vähintään seuraavat kentät:

  * msg - viesti
  * level - viestin taso (critical, error, warning, info, debug, trace)
  * time - tapahtumaaika (UTC) muodossa "2020-09-16T10:08:00.123Z".
  * corrId - Correlation id, UUID, joka pysyy samana saman kontekstin (esim. palvelimelle tehty pyyntö) lokiriveille.
   
Esimerkiksi:
   
    {"time":"2020-09-15T15:11:12.113Z","level":"info","corrId":"9a63fcb6-3867-48d9-a5d1-edb4fd04042b","msg":"Application v1.2.3 started."}
