=================
Resumen de redes
=================

Esta ** Guía de diseño de red ** analizará algunos de los principios útiles para crear redes de datos robustas como un servicio tanto para los radioaficionados  como para la comunidad en general. Un AREDN | trade |  red puede servir como mecanismo de transporte para las aplicaciones en las que las personas confían para comunicarse entre sí en el curso normal de sus interacciones comerciales y sociales, incluido el correo electrónico, el chat, el servicio telefónico, el intercambio de documentos, la videoconferencia y muchos otros programas útiles. . Dependiendo de las características de la implementación, esta red de datos digitales puede operar a velocidades cercanas a Internet con muchas millas entre los nodos de la red.

Hay una variedad de formas de interconectar AREDN | trade | nodos, pero la pregunta más importante que debe responderse es * "¿Cuál es el propósito de esta red en particular?" * Los requisitos específicos de su situación impulsarán el diseño de su red de datos. Por ejemplo, considere los siguientes problemas:

**Temporal o Permanente**
¿Se está desplegando su red como un mecanismo de comunicación a corto plazo, posiblemente para satisfacer las necesidades de un evento de un día o un ejercicio ? Si es así, varios radioaficionados con nodos portátiles pueden establecer rápidamente una red * ad hoc * con un conjunto específico de servicios para satisfacer las necesidades de comunicación para esa situación. Esos nodos y ordenadores probablemente pueden funcionar con baterías portátiles, sin ninguna dependencia de energía externa para un despliegue temporal.

¿Su red está pensada como una infraestructura a largo plazo o permanente para atender las necesidades de comunicación en curso de un área o región local? Si es así, entonces se debe diseñar y construir una topología de red más sofisticada para cumplir con esos requisitos a largo plazo. Puede ser necesario un equipo de radio más robusto o resistente, y se requerirá una alimentación  más confiable o recursos de energía renovable fuera de la red para garantizar operaciones consistentes.

**Geografia y terreno**
¿Dónde se necesita la comunicación de datos? ¿Hay ubicaciones específicas donde se requieren nodos de red? ¿Qué nivel de: abbr: cobertura de 'RF (Radio Frequency)' será necesaria para llegar a esos lugares? Los lugares a los que debe llegar la red determinarán el número y la posición de AREDN | trade | nodos

¿Cuáles son las características geográficas del área a través de la cual operará su red de datos? Los diferentes tipos de terreno pueden requerir tipos específicos de conexiones de red para cubrir adecuadamente la región sobre la cual se necesitan comunicaciones de datos. Un terreno más exigente puede requerir una mayor cantidad de nodos intermedios o posiblemente sistemas de antena y estructuras de montaje de mayor ganancia.

**Expanción y crecimiento de la red **
¿Su red necesitará expandirse o adaptarse a las condiciones cambiantes con el tiempo? Las redes de malla son ideales para el crecimiento * ad hoc * y el enrutamiento de menor costo basado en la disponibilidad de nodos. Sin embargo, a medida que se agregan más dispositivos a la red, la topología se vuelve más complicada y el tráfico de datos se puede enrutar a través de múltiples "saltos" para llegar a su destino previsto. Esto podría resultar en una mayor latencia en la red, con algunos segmentos de red que se vuelven casi inutilizables si no se pueden alcanzar los umbrales de tiempo de respuesta de la aplicación.

**Aplicaciones y rendimiento**
¿Qué programas, aplicaciones o servicios de red se deben proporcionar para cumplir el propósito de la red? Cada aplicación generará una cierta cantidad de tráfico de datos, y algunos programas o servicios requieren más datos que otros. La red necesita ser diseñada para pasar adecuadamente el tráfico para las aplicaciones requeridas.

¿Cuántos usuarios simultáneos generarán tráfico en la red y en diferentes momentos? A medida que aumenta el número de usuarios, también aumentará la cantidad de datos que atraviesan la red. Además, con un número creciente de nodos en la red, habrá un aumento correspondiente en la cantidad de `OLSR (protocolo de enrutamiento de estado de enlace optimizado) <https://en.wikipedia.org/wiki/Optimized_Link_State_Routing_Protocol>` _ tráfico que es necesario para mantener la red de malla. Un AREDN | trade | red debe estar diseñada para manejar la carga de trabajo esperada.

Con estos factores en mente, siempre es mejor mantener la red lo más simple posible e incluir solo aquellos servicios que se requieren. Asegúrese de diseñar su red para que cumpla su misión y se adapte a su propósito.


.. |trade|  unicode:: U+00AE .. Registered Trademark SIGN
   :ltrim:
