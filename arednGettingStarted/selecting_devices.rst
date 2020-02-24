========================
Seleccionando el Hardware de Radio
========================

La comunidad de radioaficionados ha reconocido los beneficios de utilizar radios comerciales de bajo costo: abbr: `WISP (Wireless Internet Service Provider)` para crear la red AREDN | trade |. Cada uno de estos dispositivos viene con su firmware del fabricante preinstalado, pero siguiendo unos sencillos pasos, este firmware se puede reemplazar con una imagen de firmware hecha por el equipo de AREDN | trade |. Se han adaptado y mejorado varias funciones de software de código abierto para crear esta versión de firmware, basándose en `OpenWRT (enrutador inalámbrico abierto) <https://en.wikipedia.org/wiki/OpenWRT>` _ y `OLSR (protocolo de enrutamiento de estado de enlace optimizado) <https://en.wikipedia.org/wiki/ Optimized_Link_State_Routing_Protocol> `_. El equipo de AREDN | trade | crea imágenes de firmware específicas adaptadas a cada modelo radio, y mantienen una lista de los dispositivos compatibles en: `Matriz de plataformas soportadas <https://www.arednmesh.org/content/supported-platform-matrix/>` _.

Para seleccionar tu dispositivo para AREDN |trade| deberías de tener en consideración lo siguiente:r decision.

* Las radios deben de comprarse teniendo en cuenta la banda de frecuencias en la que van a operar * Actualmente AREDN |trade| soporta dispositivos en las bandas de: 900 MHz, 2.4 GHz, 3.4 GHz y 5.8 GHz.

* Varios dispositivos vienen con un sistema incorporado de :abbr:`MIMO (Multiple Input-Multiple Output)`, esto ayuda a reducir los problemas de multipath que son típicos en ciudad.

* La mayoria de radios pueden comprarse de forma separada a la antena, así que es posible tener más de una opción de antena para cada radio. De esta manera podremos adaptar el comportamiento de nuestros dispositivos AREDN |trade| a cada ocación.

* El coste de los dispositivos puede ser desde menos de 50€ a varios cientos de euros por un nodo completo. Hay una opción para cada bolsillo. El mercado de segunda mano para este tipo de radios es muy activo. 

* Algunos dispositivos antiguos tienen una cantidad limitada de recursos (ya sea en forma de memoria de programa o ram) que podrían traducirse en el abandono del soporte por parte del equipo de AREDN |trade|. Ten esto en cuenta a la hora de elegir un dispositivo en la matriz de plataformas soportadas. 

* Comprueba que la potencia de radio del dispositivo sea suficiente para el enlace que quieres hacer, teniendo en cuenta la normativa local.

Uno de las mejores fuentes de información detallando las caracteristicas técnicas de cada dispositivo es su fabricante. Actualmente AREDN |trade| soporta más de cincuenta modelos, incluyendo fabricantes como: GL-iNET, Mikrotik, TP-LINK, o Ubiquiti Networks.

Si estás empezando a interesarte por AREDN |trade| puedes empezar fácilmente con uno de los dispositivos de menor coste, habitualmente con la antena integrada y :abbr:`PoE (Power over Ethernet)`. Ya llegará eel momento de expandir tu red con equipo más sofisticado.


.. note:: See the **Network Design Guide** for more information about constructing robust mesh networks.


.. |trade|  unicode:: U+00AE .. Registered Trademark SIGN
   :ltrim:
