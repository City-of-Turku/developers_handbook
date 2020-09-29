[Takaisin päätasolle](./../README.md)

# Projektien tulee tarjota metriikka statsd-muodossa
Sovelluksen tulee lähettää sovelluksen metriikat
[statsd](https://github.com/statsd/statsd) muodossa localhostin UDP porttiin
8125, josta ne voidaan tarvittaessa toimittaa eteenpäin.

Metriikka on toimitettava:

   * Rersurssipoolien koosta ja käytetyistä resursseista.
   * Käsiteltyjen pyyntöjen määrästä ja kestosta operaatiokohtaisesti.
 
