===========================================
Características del espectro radioeléctrico
===========================================

AREDN | trade |  redes operan en el espectro de radio de microondas y los  radioaficionados con autorización especial tienen acceso exclusivo a muchas de estas frecuencias. Para las bandas en las que los radioaficionados comparten el espectro, existe una mayor probabilidad de interferencia de RF que puede hacer que algunas frecuencias sean inutilizables para AREDN | trade | redes de datos. Para obtener los mejores resultados, seleccione frecuencias que no se comparten con otros usuarios sin licencia.

Cada banda se divide en canales, cada uno de los cuales consiste en un desplazamiento de frecuencia de 5 MHz identificado por la frecuencia central del canal y se le asigna una etiqueta numérica. En el siguiente ejemplo, puede ver que un canal seleccionado puede usar más o menos el rango de frecuencia en función del ancho del canal elegido. Cuanto más ancho sea el canal, más superposición habrá con los canales adyacentes. Los canales anchos tienen el efecto de reducir la cantidad de canales que no se superponen o que no interfieren y que estarán disponibles para su uso. Al seleccionar canales y anchos de banda, asegúrese de usar canales que no se superpongan. Los dispositivos que no usan el mismo canal y ancho de canal que se superponen interferirán entre sí y no pueden comunicarse para coordinar el uso compartido del ancho de banda.

.. image:: _images/channel-width-example.png
   :alt: Channel Width Example
   :align: center

Toda la banda de 33 cm se comparte con otros usuarios autorizados de la FCC. Todos los canales superiores en la banda de 13 cm se comparten con los usuarios estándar de la FCC Parte 15: abbr: `WiFi (IEEE 802.11x)`, al igual que todos los canales inferiores en la banda de 5 cm. El único rango de frecuencia que los radioaficionados no comparten actualmente con usuarios sin licencia es la banda de 9 cm, en la cual el ejército de los EE. UU. puede operar ocasionalmente con radiobalizas. La siguiente tabla enumera cada banda de radioaficionados, rango de frecuencia, ancho de banda total de asignación y la cantidad de canales disponibles para AREDN | trade | redes.

=======  =================  ===============  ========
Banda    Frecuencia         Ancho de banda   Canales 
=======  =================  ===============  ========
33 cm    902-928   MHz      25 MHz           5
13 cm    2390-2450 MHz      45 MHz           9
9  cm    3300-3500 MHz      120 MHz          24
5  cm    5650-5925 MHz      260 MHz          52
=======  =================  ===============  ========

La tabla anterior muestra que la banda de 9 cm tiene el mayor ancho de banda disponible en sus canales no compartidos, mientras que la banda de 5 cm tiene la siguiente mayor cantidad de ancho de banda disponible en canales no compartidos. La elección de una banda de frecuencia para conexiones AREDN | trade | red depende de varios factores diferentes, pero puede "mezclar y combinar" bandas en el diseño de su red siempre que ambos lados de un enlace de radio usen la misma banda, canal y ancho de canal.

Tiene la opción de seleccionar el ancho del canal para cada enlace. Cuando utilice canales en la parte superior o inferior de una banda, asegúrese de que el ancho elegido no se transmitirá fuera de la asignación de la Parte 97 de la FCC para esa banda. Diferentes anchos de canal pueden producir un mejor rendimiento que otros. En algunas áreas, los operadores usan diferentes canales para aislar enlaces, por lo que pueden necesitar usar canales de 10 MHz en lugar de 20 MHz para asegurarse de tener suficientes canales disponibles. Además, los enlaces de larga distancia simplemente tienen un mejor rendimiento con anchos de canal de 10 MHz frente a 20 MHz o 5 MHz. Pruebe el rendimiento de sus enlaces utilizando varios anchos de canal para asegurarse de que estén optimizados.

Algunas de las ventajas y desventajas de cada rango de frecuencia se explican en las siguientes secciones.

Características de la banda de 900 MHz
--------------------------------------

** Desventajas **
Toda la banda de 33 cm se comparte entre varios servicios de radio autorizados por la FCC. La desventaja de usar esta banda para conexiones de red  AREDN | trade |  es que en todas las áreas remotas, excepto en las más remotas, el nivel de ruido de RF puede ser muy alto, lo que reduce el: abbr: `SNR (relación señal / ruido)` y da como resultado la pérdida de paquetes, retrasos en la retransmisión y una menor calidad de enlace utilizable.

Otra desventaja es que el equipo puede ser más costoso que los dispositivos que operan en las bandas de 2.4 y 5.8 GHz. Además, toda la banda es bastante estrecha (25 MHz), lo que significa que solo pueden existir uno, dos o cinco canales de radio en este rango de frecuencia compartida, dependiendo del ancho del canal seleccionado.

**Ventajas**
La ventaja de esta banda de frecuencia es que su longitud de onda más larga la hace más adecuada para penetrar algunos tipos de obstrucciones que normalmente bloquearían las señales a frecuencias más altas. Sus características de propagación: abbr: `NLOS (Non Line of Sight)` pueden ser exactamente lo que se necesita para establecer un enlace de RF entre dos ubicaciones difíciles.

Características de la banda de 2.4 GHz 
--------------------------------------

**Desventajas**
Los canales superiores de la banda de 13 cm se comparten con varios otros servicios autorizados por la FCC. Dependiendo de las condiciones locales de RF, puede que no sea posible utilizar estos canales compartidos debido al alto nivel de ruido que reduce: abbr: `SNR (relación señal / ruido)` y disminuye la calidad de la señal. Esto deja a los radioaficionados  solo con dos canales no compartidos con un posible ancho de banda de 10 MHz cada uno.

Una preocupación con todas las bandas de frecuencias más altas es que debe haber una línea de visión clara entre los nodos a cada lado del enlace. Esto significa que no solo los nodos necesitan tener una ruta directa sin obstrucciones, sino que la Zona Fresnel entre los nodos también debe estar despejada. El diámetro de la zona de Fresnel depende de la frecuencia y la distancia entre los nodos. Por ejemplo, en un enlace en la banda de 13 cm con 10 millas entre nodos, el primer radio de la Zona Fresnel será de 72 pies. Si menos del 20% de la zona de Fresnel está obstruida, hay poca pérdida de señal, pero cualquier bloqueo más allá del 40% causará una pérdida de señal significativa y podría inutilizar el camino. En la banda de 13 cm, el radio del 60% sin bloqueo es de aproximadamente 43 pies, que a menudo es más alto que la mayoría de los nodos * Intermedio * o * Última milla * que se han instalado. Se debe considerar cuidadosamente la altura del nodo y el terreno entre los nodos para minimizar las obstrucciones.

.. image:: _images/2.4ghz.png
   :alt: 2.4 GHz Band
   :align: center

**Ventajas**
Dentro del rango de frecuencia disponible, tiene la opción de seleccionar anchos de canal de 5, 10 o 20 MHz. Un ancho de canal mayor proporcionará velocidades de datos más altas. Sin embargo, un efecto de reducir el ancho del canal es aumentar: abbr: `SNR (relación señal / ruido)` para mejorar la calidad de la señal. Por ejemplo, cambiar de un ancho de canal de 20 MHz a 10 MHz dará como resultado una ganancia de señal de 3 dB y podría marcar la diferencia entre un enlace marginal y uno utilizable. Solo recuerde que cuando corta el ancho del canal a la mitad, también reduce su rendimiento máximo a la mitad. Pruebe cuidadosamente sus enlaces para garantizar un rendimiento óptimo.

Una ventaja para la banda de 13 cm es que los equipos de radio y los sistemas de antena están más disponibles y son menos costosos debido a la mayor demanda del consumidor. Existe una gran variedad de equipos de varios fabricantes que respaldan AREDN |trade | y operan en esta banda. Con una línea de visión clara y antenas bien sintonizadas, las señales de 2.4 GHz pueden propagarse a través de distancias muy largas.

 Características de la banda de 3.4 GHz 
----------------------Características----------------

**Desventajas**
Como se mencionó anteriormente, debe haber una línea de visión clara y la zona de Fresnel entre los nodos también debe estar despejada. Para un enlace en la banda de 9 cm con 10 millas entre nodos, el primer radio de la zona de Fresnel será de 62 pies, que es menor que la banda de 13 cm discutida anteriormente. Sin embargo, el radio del 60% sin bloqueo sigue siendo de unos 37 pies. Considere el nodo: abbr: `AGL (altura sobre el nivel del suelo)` y el terreno para minimizar las obstrucciones.

El equipo para la banda de 9 cm está menos disponible y generalmente es más costoso debido a la menor demanda del consumidor. Se debe tener cuidado al seleccionar radios para no confundirlos con los dispositivos más comunes: abbr: `WiMAX (IEEE 802.16)` que están diseñados para el rango de 3,65 GHz y no son compatibles con AREDN | trade | firmware.

.. image:: _images/3.4ghz.png
   :alt: 3.4 GHz Band
   :align: center

**Ventajas**
La principal ventaja de usar la banda de 9 cm es que tiene más ancho de banda disponible para usar en canales no compartidos que cualquier otra banda. Puede seleccionar anchos de canal de 5, 10 o 20 MHz, con anchos de canal más grandes que proporcionan velocidades de datos más altas. Recuerde que reducir el ancho del canal aumentará: abbr: `SNR (relación señal / ruido)` para mejorar la calidad de la señal si eso es un problema para un enlace en particular. El equipo en la banda de 9 cm es adecuado para * Backbone Links * ya que hay pocas posibilidades de interferencia de otros dispositivos que comparten estas frecuencias en los sitios de la torre. Con una línea de visión clara y antenas bien sintonizadas, las señales de 3,4 GHz pueden propagarse a través de distancias muy largas.

Características de la banda de 5.8 GHz 
--------------------------------------

**Desventajas**
Como se mencionó anteriormente, debe haber una línea de visión clara y la zona de Fresnel entre los nodos también debe estar despejada. Para un enlace en la banda de 5 cm con 10 millas entre nodos, el primer radio de la Zona Fresnel será de 46 pies, que es mucho menor que las bandas de frecuencia discutidas anteriormente. Sin embargo, el radio del 60% sin bloqueo en la banda de 5 cm todavía es de aproximadamente 28 pies. Asegúrese de tener en cuenta el nodo: abbr: `AGL (altura sobre el nivel del suelo)` y el terreno para lograr una línea de visión clara entre los nodos.

.. image:: _images/5.8ghz.png
   :alt: 5.8 GHz Band
   :align: center

**Ventajas**
Una ventaja de usar la banda de 5 cm es que contiene 52 canales, y muchos de ellos en el extremo superior de la banda se subutilizan con menos posibilidades de interferencia. Puede elegir anchos de canal de 5, 10 o 20 MHz, canales con mas ancho proporcionan velocidades de datos más altas. Recuerde que la reducción del ancho del canal aumentará: abbr: `SNR (Relación señal / ruido)` para mejorar la calidad de la señal si eso es un problema para un enlace problemático.

El equipo de radio y los sistemas de antena para esta banda están fácilmente disponibles y son menos costosos debido a la mayor demanda del consumidor. Existe una gran variedad de equipos de varios fabricantes que respaldan el  AREDN |trade | firmware y operan a través de los 52 canales disponibles. Los sistemas de radio y antena para esta banda que son similares en tamaño a los de otras bandas y a menudo tendrán mayor ganancia. Los dispositivos en la banda de 5 cm también son adecuados para * Backbone Links * ya que hay pocas posibilidades de interferencia de RF de otras radios que comparten estas frecuencias en sitios de alto perfil. Con una línea de visión clara y antenas bien sintonizadas, las señales de 5.8 GHz pueden propagarse a través de distancias muy largas.


Hay diferentes rangos de frecuencia disponibles para conectar los nodos de malla necesarios para cumplir con los propósitos de su red. Al planificar las frecuencias que se desplegarán en ubicaciones específicas, puede ser útil usar un * analizador de espectro * para identificar los rangos que ya están en uso. El objetivo final es tener una red de datos confiable que cumpla su propósito de proporcionar servicios a los destinos y usuarios previstos.


.. |trade|  unicode:: U+00AE .. Registered Trademark SIGN
   :ltrim:
