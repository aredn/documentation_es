========================
Planificación de canales
========================

La sección anterior identificó los diferentes canales en cada banda de frecuencia que están disponibles para AREDN | trade | redes. Los dispositivos a cada lado de un enlace de radio deben usar la misma banda de frecuencia, canal, ancho de canal y SSID. Sin embargo, más allá de ese requisito, tiene bastante flexibilidad para seleccionar los canales de radio que asegurarán la mayor calidad de señal y rendimiento para su red. En un AREDN | trade | red con varios nodos distribuidos en un área geográfica limitada, todos los nodos pueden usar la misma banda, canal y ancho de canal. Esto les permite establecer la red de malla y enrutar datos a cualquiera de los sitios según sea necesario.

Sin embargo, a medida que más nodos se unen a la red o cuando varios nodos son: abbr: `colocados (mismo sitio físico)` y comparten el mismo canal, es posible que el rendimiento general de la red se degrade. Para un AREDN | trade | red para ampliar en tamaño y complejidad, la coordinación de frecuencias y la planificación de canales se vuelven cada vez más importantes. Para planificar el crecimiento futuro, los grupos de malla pueden necesitar dividir el tráfico de la red mediante la asignación de canales para áreas específicas o tipos de enlaces con el fin de garantizar que la red pueda soportar los servicios esperados.

operación de red inalámbrica
----------------------------

Una red inalámbrica es un medio semidúplex compartido en el que solo debe transmitir una estación a la vez. En ese sentido, las operaciones inalámbricas son análogas a otros tipos de transmisiones de radio. Si dos estaciones conectan sus transmisores al mismo tiempo, interferirán entre sí en la medida en que ninguna de ellas reciba el mensaje de la otra. Es por eso que se implementan procedimientos de control de red para garantizar el acceso controlado a un canal de radio durante la comunicación de emergencia.

AREDN | trade | firmware verifica automáticamente el acceso de la estación al medio inalámbrico mediante la implementación de `IEEE 802.11a / b / g / n <https://en.wikipedia.org/wiki/IEEE_802.11n-2009>` _ standards y `Carrier Sense Multiple Access / Evitación de colisiones (CSMA / CA) <https://en.wikipedia.org/wiki/Carrier-sense_multiple_access> `_. Esta tecnología de escuchar antes de hablar ayuda a los nodos a determinar si un canal está ocupado. Cada nodo realiza una * Clear Channel Assessment (CCA) * además de usar `Request to Send / Clear to Send (RTS / CTS) <https://en.wikipedia.org/wiki/IEEE_802.11_RTS/CTS>` _ mensajes para negociar el acceso a un canal. También se requiere una cantidad insignificante de tráfico de red para `OLSR (protocolo de enrutamiento de estado de enlace optimizado) <https://en.wikipedia.org/wiki/Optimized_Link_State_Routing_Protocol>` _ para mantener rutas para la red de malla en su conjunto, pero ese OLSR tráfico es una fracción muy pequeña del total.

En una red inalámbrica de un solo canal, cualquier nodo que necesite transmitir se coordinará automáticamente con los otros nodos para obtener un canal libre. Esto es así por diseño, pero a medida que más dispositivos intentan obtener acceso al mismo canal, existe un mayor potencial para que cada nodo espere más tiempo para poder transmitir. Esto puede resultar en una mayor latencia y una disminución del rendimiento de la red a medida que aumenta el número de nodos de red.

canal de contención
++++++++++++++++++

El concepto de * Interferencia de canales superpuestos * se ilustra en el lado derecho del siguiente diagrama de exploración de canales. * La interferencia de canales superpuestos * es muy grave, pero se puede eliminar seleccionando canales no superpuestos para todos los dispositivos que acceden a su red de malla. Un segundo problema relacionado con el funcionamiento de las redes inalámbricas se ilustra en el lado izquierdo del diagrama. Se denomina comúnmente * Interferencia cocanal *, pero se describe con mayor precisión como * Contención cocanal * o * Cooperación cocanal *.

.. image:: _images/cci-aci.png
   :alt: Co-Channel Contention
   :align: center

En este ejemplo, varios nodos deben compartir un solo canal, por lo que todos negocian la oportunidad de transmitir. Cualquier nodo que necesite transmitir utilizará la tecnología de escuchar antes de hablar para determinar si el medio está ocupado. Si el canal parece libre, el nodo intentará transmitir datos. Si el canal está ocupado, el nodo diferirá la transmisión hasta que el canal parezca despejado. En una red de alta densidad donde una gran cantidad de nodos comparten un solo canal, los procesos normales de negociación pueden provocar una degradación significativa del rendimiento. Desde la perspectiva del usuario final, un canal sobrecargado puede hacer que la red parezca lenta o incluso inutilizable.

Este ejemplo no pretende mostrar teniendo solo siete nodos se va sobrecargar un canal. No existe una regla general establecida para compartir canales que especifique cuántos nodos son demasiados. La respuesta depende del número de nodos, el ancho de banda en uso para soportar los servicios requeridos, las cualidades de la señal de enlace y otras características de la red. En función de estos parámetros, un canal compartido puede funcionar bien con muchas docenas de nodos, mientras que otra red puede ver una degradación del rendimiento con una cantidad significativamente menos nodos que comparten un mismo canal. Muchos factores interactúan para influir en el rendimiento de la red, pero pronto será obvio para los usuarios si la red se comporta como se esperaba.

Hay varias herramientas disponibles para probar el rendimiento de la red, como * ping * para medir la latencia, * traceroute * para identificar cómo se enruta el tráfico y * iperf3 * para estimar el rendimiento de la red. Las mediciones periódicas junto con las percepciones del usuario pueden ser útiles para determinar si la separación de canales sería beneficiosa. Es un subproducto esperado de cómo funcionan normalmente las redes inalámbricas, pero el rendimiento puede mejorarse al planificar los canales asignados para sus dispositivos de malla como se describe en la sección ** Planes de canales ** a continuación.

Nodos ocultos
++++++++++++

En cualquier red inalámbrica habrá nodos que no estén dentro del alcance de radio entre sí pero que compartan el mismo canal. En el diagrama de ejemplo, ** A ** puede escuchar ** B ** pero no puede escuchar ** C **. Como ** A ** y ** C ** están `ocultos el uno del otro <https://en.wikipedia.org/wiki/Hidden_node_problem>` _, pueden intentar transmitir en el canal compartido al mismo tiempo sin sabiéndolo. Debido a sus ubicaciones relativas y a cualquier retraso de red asociado, puede parecer que cada nodo tiene un canal libre para la transmisión.

.. image:: _images/hidden-node.png
   :alt: Hidden Node Problem
   :align: center

`Solicitud de envío / Borrar para enviar (RTS / CTS) <https://en.wikipedia.org/wiki/IEEE_802.11_RTS/CTS>` _ los mensajes son utilizados por AREDN | trade | nodos para minimizar o eliminar este problema. Por ejemplo, el nodo ** A ** transmite un breve mensaje RTS con un intervalo de tiempo / duración propuesto para transmitir su flujo de datos completo. El nodo ** B ** recibe esa solicitud y transmite un CTS para ese intervalo de tiempo. El nodo ** C ** no pudo escuchar el RTS original, pero escuchará el mensaje CTS y diferirá sus transmisiones durante ese intervalo de tiempo.

Otros dos enfoques también pueden aliviar el problema del nodo oculto. Es posible que pueda hacer que los nodos ocultos sean visibles entre sí, por ejemplo, aumentando la intensidad de la señal. La alternativa es aislar completamente los nodos colocándolos en diferentes bandas o canales. Dado que los nodos que usan antenas direccionales son casi invisibles para otros que no están ubicados en el haz de la antena, las antenas direccionales deben usarse con cuidado al compartir un canal. Puede ser más apropiado crear un enlace separado entre los sitios y colocar las radios en una banda o canal diferente.

Otro caso es cuando hay un enlace de baja calidad sobre el cual se debe enrutar todo el tráfico. El apretón de manos y las retransmisiones de datos pueden hacer que todos los demás nodos esperen. Toda la red puede verse afectada por una ruta de baja calidad que se convierte en un solo cuello de botella. Si es posible, debe aumentar la calidad de la señal de ese enlace vital o instalar un mejor enlace como una ruta alternativa.

Aleteo de ruta
++++++++++++++

Este es otro problema que puede conducir a problemas de rendimiento en una red. Puede tener rutas paralelas entre dos * Nodos remotos *, y estas rutas tienen valores similares: abbr: `ETX (métrica de transmisión esperada)` que indica que el costo de usar cualquiera de las rutas es comparable. Puede parecer que estos dos caminos funcionan bien la mayor parte del tiempo.

Sin embargo, cuando una aplicación de uso intensivo de ancho de banda, como la videoconferencia, comienza a enviar tráfico a través de una de las rutas, puede notar que el enlace se atasca y el: abbr: `ETX (métrica de transmisión esperada)` caerá por debajo de la otra ruta . En este punto: abbr: `OLSR (protocolo de enrutamiento de estado de enlace optimizado)` cambia a la ruta alternativa que ahora tiene un costo más bajo. Luego, la transmisión de video empantana su nueva ruta, lo que reduce: abbr: `ETX (métrica de transmisión esperada)`, y: abbr: `OLSR (protocolo de enrutamiento de estado de enlace optimizado)` vuelve al enlace original cuyo: abbr: ` ETX (métrica de transmisión esperada) `ha mejorado. Esta situación puede continuar indefinidamente, sin que ninguna ruta pueda entregar el tráfico adecuadamente.

Este problema puede ocurrir en enlaces de múltiples saltos con similar: abbr: `ETX (métrica de transmisión esperada)` que parece funcionar bien hasta que se cargan con tráfico. Luego, comienza a ocurrir la pérdida de paquetes, las conexiones caducan y ninguna de las rutas es confiable durante ese ciclo. Una solución podría ser mejorar la carga del enlace de múltiples saltos aumentando la calidad de la señal de los enlaces a lo largo de una de las rutas. Por el contrario, también puede reducir la potencia en la ruta alternativa para aumentar su costo. Si se debe pasar tráfico de ancho de banda intensivo entre dos puntos finales remotos, el mejor enfoque sería diseñar una ruta más sólida entre esos dos puntos finales para satisfacer esa necesidad.

Planes de canales y coordinación de frecuencia
----------------------------------------

Puede experimentar un rendimiento deficiente de la red si hay demasiados nodos que usan la misma banda y canal. Aquí hay un ejemplo simple para ilustrar el problema: una ruta de tres saltos desde QTH1 a Tower1 a Tower2 a QTH2. Si todos los enlaces usan el mismo canal, solo un nodo a la vez puede enviar datos. Esto reduce instantáneamente el rendimiento en un tercio o más y aumenta la latencia con la sobrecarga del protocolo. Para mejorar el rendimiento, puede configurar cada enlace para usar un canal diferente, permitiendo transmisiones simultáneas. Por ejemplo, los nodos de la torre colocada podrían vincularse DtD a través de Ethernet, con QTH1 y Tower1 usando el canal 172 de 5 GHz, mientras que QTH2 y Tower2 usan el canal 176. Antes de implementar este plan de canales, es posible tener un flujo de video HD y una llamada VoIP  con frecuentes abandonos. Después de implementar el plan de canales, debería ser posible tener tres transmisiones de video HD y varias llamadas VoIP simultáneamente con pocos abandonos.

Dependiendo de la banda de frecuencia que esté utilizando, hay diferentes opciones disponibles para asignar canales no compartidos no superpuestos a sus dispositivos de malla. Como se muestra en el cuadro a continuación, en la banda de 2,4 GHz que utiliza un ancho de canal de 5 MHz, solo hay dos canales que no se superponen y que aún no se comparten con otros usuarios sin licencia. En la banda de 3.4 GHz que usa los canales pares de 10 MHz, hay once canales no superpuestos. En la banda de 5.8 GHz que utiliza canales pares de 10 MHz, hay 25 canales no superpuestos, pero solo ocho de ellos no se comparten con otros usuarios potenciales del espectro.

=======  ===============  ======================================
Banda    Ancho de banda   Canales no superpuestos no compartidos
=======  ===============  ======================================
2.4 GHz  5 MHz            2
3.4 GHz  10 MHz           11
5.8 GHz  10 MHz           8
=======  ===============  =================================

Idealmente, las zonas de cobertura de RF (a veces llamadas "celdas") deberían usar canales diferentes. La cobertura de celdas superpuestas puede proporcionar una conectividad más amplia, pero las zonas de cobertura superpuestas no deben usar frecuencias de RF superpuestas.
.. image:: _images/channel-reuse-example.png
   :alt: Example Channel Reuse Plan
   :align: center

El mapa de cobertura de ejemplo muestra que se han asignado cuatro canales diferentes para lograr una cobertura amplia al segmentar áreas específicas en zonas para reducir la contención cocanal. Cabe señalar que incluso un plan de reutilización de canales como este puede no eliminar todas las instancias de contención. Por ejemplo, si un nodo está en los bordes exteriores de una zona de cobertura o se eleva muy por encima del nivel del suelo, sus transmisiones pueden propagarse a una celda distante utilizando el mismo canal. Las radios en la otra celda diferirán si escuchan las transmisiones del nodo original, aunque se originen en una celda diferente. Puede ser necesario cierto grado de experimentación para minimizar la contención y maximizar el rendimiento de la red.

Nodos que comparten ubicación
-----------------------------

.. image:: _images/collocated-nodes.png
   :alt: Collocated Nodes
   :align: right

En algunos sitios puede haber varios dispositivos montados en el mismo edificio o estructura. La foto de la derecha muestra muchos nodos colocados en una sola torre. La degradación del rendimiento de la red puede ocurrir si estos nodos comparten una banda y canal de RF. Por ejemplo, cuando dos antenas sectoriales se colocan y comparten el mismo canal, el rendimiento de la red para ese sitio se reducirá a la mitad o más. Si tiene nodos colocados, entonces tiene sentido permitir que los dispositivos pasen tráfico a través de su interfaz Ethernet (como se describe a continuación) en lugar de obligarlos a usar su canal de radio.

Enlace de dispositivo a dispositivo (DtD)
+++++++++++++++++++++++++++++++++++++++++

En su configuración más básica para dos nodos colocados, se conecta un cable Ethernet entre el puerto PoE * LAN * de cada dispositivo. : abbr: `OLSR (Protocolo de enrutamiento de estado de enlace optimizado)` asignará un "costo de enlace" muy bajo (0.1) a la conexión DtD y enrutará automáticamente el tráfico entre los nodos a través de Ethernet en lugar de hacer que el canal de RF esté ocupado.

Una ventaja adicional de la vinculación DtD es que puede vincular nodos que operan en diferentes bandas y canales. Los nodos que usan * Separación de canales * para segmentar el tráfico aún pueden pasar datos a altas velocidades a través de su enlace DtD y ser miembros de una sola red. En un sitio de torre como el que se muestra aquí, puede vincular nodos de 2,4 GHz, 3,4 GHz y 5,8 GHz a la misma red. De hecho, en un sitio concurrido como este, es una buena práctica utilizar el enlace DtD, porque de lo contrario la contención del canal de RF podría inutilizar la red.

Idealmente, debe configurar sus nodos coubicados para usar diferentes bandas y canales, y luego configurar enlaces DtD entre los nodos para garantizar que el tráfico se enrute de manera eficiente sin generar embotellamientos de RF o retrasos. : abbr: `OLSR (Protocolo de enrutamiento de estado de enlace optimizado)` siempre elegirá primero la ruta DtD al pasar el tráfico entre los nodos vinculados. Cada AREDN | trade | El nodo reconoce los paquetes entrantes etiquetados con: abbr: `VLAN (Red de área local virtual)` 2 como tráfico DtD.
.. image:: _images/dtd-linking.png
   :alt: DtD Linking
   :align: center

En el simple ejemplo anterior, el conmutador compartirá todo el tráfico en todos los puertos y cada nodo lo recibirá en su enlace DtD. Si desea particionar aún más el tráfico, puede configurar VLAN adicionales en el conmutador para aislar el tráfico del puerto para que solo los nodos que deberían recibir tráfico específico lo vean. Por ejemplo, puede tener un sistema de videovigilancia (5) o un: abbr: `VoIP (Voz sobre IP)` Sistema PBX (6), y el tráfico de esos dispositivos solo debe pasarse a un conjunto específico de enlaces como se muestra en El diagrama a continuación. Las VLAN basadas en puertos asegurarán que el tráfico sea controlado y enrutado, en lugar de transmitirse a través de cada enlace.

.. image:: _images/vlan-isolation.png
   :alt: Traffic Isolation with VLANs
   :align: center

Polarización de la antena
+++++++++++++++++++++++++

La mayoría de las últimas AREDN | trade |  dispositivos usan antenas de polaridad dual y: abbr: características `MIMO (entrada múltiple - salida múltiple)` en las radios que explotan la propagación por trayectos múltiples. Sin embargo, si está utilizando antenas de polaridad única con radios de "cadena simple", otra forma de lograr la separación de la señal para dispositivos colocados es orientar las antenas del sitio para que una esté polarizada verticalmente y la otra esté polarizada horizontalmente. Esto puede dar como resultado una separación de señal de hasta 20 dB. Debido al predominio de la polarización vertical en dispositivos WiFi comerciales, AREDN | trade | nodos pueden lograr un rendimiento ligeramente mejor utilizando polarización horizontal con una línea de visión clara. Puede probar ambas polarizaciones para ver cuál produce un mejor rendimiento frente al ruido artificial en su entorno específico. Tenga en cuenta que las antenas en ambos lados de un enlace de radio deben estar orientadas de la misma manera.

Alinear nodos vinculados
++++++++++++++++++++++++

El AREDN | trade |  web interfaz proporciona información útil cuando se alinean dos nodos que se están instalando para formar un enlace. En la página ** Estado de nodo **, haga clic en el botón ** Gráficos ** para ver el gráfico * Señal en tiempo real a ruido *. Lentamente gire e incline su antena, haciendo una pausa para ver las métricas de la señal. Una vez que vea la mejor señal, como se muestra a continuación, puede bloquear la antena en su posición. Si desea enfocarse en la posición de la antena sin tener que mirar el gráfico SNR, también puede habilitar la función * SNR Sound * y alinear la antena con el tono de tono más alto. Dependiendo de la implementación, una relación señal / ruido de 15 dB es adecuada para pasar datos a velocidades en el rango de 5 a 20: abbr: `Mbps (Megabits por segundo)`.

.. image:: _images/align-nodes.png
   :alt: Aligning Nodes
   :align: center

Consejos de planificación de canales
------------------------------------

.. sidebar:: Evitar problemas de escalabilidad de red

Si hay dos torres o áreas de cobertura celular dentro del alcance, configure los nodos con diferentes canales para evitar un bajo rendimiento.

Según el propósito de su red, intente crear rutas confiables a las ubicaciones donde se necesitan datos. Utilice la separación de canales y el enlace DtD de los nodos colocados para evitar la contención del canal de RF. Las bandas de 3,4 GHz y 5,8 GHz proporcionan los canales más compartidos para su uso en AREDN | trade | redes.

* Si necesita una amplia cobertura local para un área muy grande, puede instalar antenas sectoriales en una torre en un sitio alto: por ejemplo, tres paneles con un ancho de haz de 120 grados cada uno. Un enlace DtD vincula los sectores en la torre y se utilizarían diferentes canales para cada sector. De esta manera se evitaria la congestión en los canales.

* Considere poner cada área de cobertura local en su propio canal para minimizar la interacción entre zonas.

* Si está instalando enlaces punto a punto de larga distancia para conectar islas de malla, asegúrese de usar una banda o canal separado para el enlace troncal. Este tipo de enlace tiene un único propósito: transportar la mayor cantidad de datos lo más rápido posible de un extremo al otro. Elimine cualquier tipo de contención de canal para que estos enlaces puedan lograr un alto rendimiento.

* Recuerde que una ruta de múltiples saltos a través de la red debe tener una buena calidad de señal en cada tramo del viaje. No puede esperar un rendimiento adecuado a través de una serie de enlaces de baja calidad. Por ejemplo, si atraviesa tres enlaces que tienen: métricas abbr: `LQ (calidad de enlace)` 65%, 45% y 58%, su agregado: abbr: `LQ (calidad de enlace)` será 17%, lo que no se puede usar . Idealmente, el agregado: abbr: `LQ (calidad de enlace)` debe tener al menos un 80% para tener un enlace que admita las aplicaciones y servicios que necesita.


.. |trade|  unicode:: U+00AE .. Registered Trademark SIGN
   :ltrim:
