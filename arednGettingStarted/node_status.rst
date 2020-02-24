===================
Estado del Nodo
===================

Una vez se ha completado la configuración inicial de tu nodo de AREDN |trade|, puedes conectar tu ordenador al puerto de LAN del inyector :abbr:`PoE (Power over Ethernet)` y navegar a ``http://localnode``. Serás redirigido a la página de **Estado de Nodo** tal y como se muestra en la web inferior.

----------

.. image:: _images/03-node-status.png
   :alt: Node Status
   :align: center

----------

Debajo de la barra con el nombre del nodo, hay varias secciones: 

**Ayuda**
   Abre una nueva ventana para mostrar la ayuda.
   
**Refresh**
   Actualiza la información mostrada con datos actuales.

**Mesh Status**
   Abre la página de **Estado de la Red**, mostrando los nodos cercanos y remotos. Además, muestra los servicios expuestos en esos nodos. 

**Escaneo WiFi**
   Muestra la lista de otras señales 802.11 (WiFi) que se reciben desde tu nodo. Estas señales incuyen Puntos de Acceso, el WiFi del vecino, y otras redes. Esta función solo muestra dispositivos con la misma configuración de canal (frecuencia y ancho de canal) que la de nuestro nodo. Si estamos instalando en una nueva hubicación, es buena práctca escanear con  ancho de canal de 5, 10, and 20MHz en busca de posibles interferencias. Cuando hay más de una red accesible (con diferente SSID o canal), los ID de cada nodo de dicha ned se mostrarán de forma resumida. Además, hay un modo automático de escaneo, pero hacerlo de forma continuada no está recomendado; especialmente si nuestro nodo tiene tráfico.
  El escaneo de AREDN es pasivo, solo busca los paquetes que anuncian redes cercanas en los canales. Esto implica que puede perderse alguno. WiFiScan no hace escaneos activos, por lo que no se corre el riesgo de interferir con estaciones de Radar ni DFS cercanos. Varios intentos de escaneo pueden ser necesarios para encontrar todos los dispositivos al alcance.

**Configuración**
  Abre la página de configuración de tu nodo. Necesitarás usuario y contraseña para acceder a esta página. El usuario siempre es ``root``, y la contraseña se configuró la primera vez que se utilizó el nodo. Si el nodo no ha sido configurado nunca, ca contraseña por defecto es ``hsmm``.

**Selección de Tema**
   El firmware AREDN |trade|tiene múltiples temas incluídos por defecto. El standard es ``aredn``, pero puedes probar otros que se ajusten mejor a tus preferencias. 
   
   
Resumen de los ajustes del Nodo
---------------------

El área bajo los controles muestra dos cosas: En el lado izquierdo contiene los detalles de configuración de este nodo. Concretamente, las direcciones ip de cada interfaz, SSID, frecuencia y ancho de canal.

La columna derecha contiene la intensidad de la sieñal recibida y otros valores de este nodo. La **Relación Señál a Ruido** muestra la señal del nodo vecino más fuerte en :abbr:`dBm (decibels relative to one milliwatt)`, y estará disponible solo cuando el nodo esté interconectado por :abbr:`RF (Radio Frequency)` a la red AREDN | trade |.

Bajo la lectura de señal, están los datos del sistema tales como: La versión del Firmware, el tipo de red, la hora del nodo, y el tiempo que lleva sin ser reiniciado. Los nodos no tienen ni batería ni un reloj interno. Esto provoca que la hora se pierda cada vez que se reinicia. Si hay salida a internet, tomará la hora usando el protocolo :abbr:`NTP (Network Time Protocol)`

La **Carga Media** es la media del número de procesos que tienen lugar en el nodo en los últimos 1, 5 y 15 minutos. 
El **Espacio Libre** muestra cuanta memoria nos queda en el dispositivo.  Esta es la memoria flash del dispositivo, que tiene permanencia entre reinicios. Aquí quedan guardadas las configuraciones y los paquetes de software. 
La **Memoria** nos indica la cantidad de memoria :abbr:`RAM (Random Access Memory)` disponible en el nodo.

Las **Entradas :abbr:`OLSR (Optimized Link State Routing protocol)`** Muestran el total de nodos en la tabla de rutas actual. Estos son los nodos de la red AREDN con los que tenemos conectividad. 

Signal Charts
-------------

There is a **Charts** button next to the node's **Signal Stength** display, and clicking this button takes you to **Signal Charts**. This page shows :abbr:`RF (Radio Frequency)` signal information in both a realtime and an archived view. The default view shows the average signal of all connected stations in realtime.

.. image:: _images/04-node-charts.png
   :alt: Node Charts
   :align: center

At the top of the charts display there are several control buttons.

**Archive**
  This button shows the charts for any archived signal data on this node.

**Realtime**
  This button shows the charts for current signal data as seen from this node.

**Quit**
  This button exits the charts view and takes you back to the *Node Status* page.

Below these controls you can choose to view the signal strength statistics for individual nodes that are directly connected to your node. Choose the neighbor node from the **Selected Device** dropdown list. Changing the selected device will automatically reload the chart to show that node's information.

Hovering over data points within a chart will show additional information for each data point, including Time, Signal, Noise, :abbr:`SNR (Signal to Noise Ratio)`, TX Rate, TX :abbr:`MCS (Modulation Coding Scheme)`, RX Rate, and RX :abbr:`MCS (Modulation Coding Scheme)`. If no traffic is being routed to the neighbor, the Rate and MCS values may be zero until data is available. An MCS value of zero may indicate non-802.11n encoding schemes (ie. 802.11a/b/g).

The small icon with three vertical dots in the upper right corner of the chart allows you to download a snapshot of the chart to a graphic file on your local computer (jpeg or png).

Data shown in the **Archive** charts is not stored in permanent memory on the node. The node will store approximately two days of archived data, and all data is cleared when a node is rebooted.

If you click and drag your mouse across a region of the chart, the display will zoom into that selected area. This allows you to view data points for a specific time range of your choice. While zoomed, two additional icons will appear in the upper right of the chart. The **Pan** icon allows you to scroll and pan the zoomed portion of the chart. The **Reset** icon returns the chart to its normal display mode.

.. image:: _images/snr-sound.png
   :alt: SNR Sound Control
   :align: left

On the left of the Realtime Graph there is an **SNR Sound** control. Clicking the *On* button will cause your computer to emit a tone that corresponds to the relative SNR level, with higher pitch tones indicating better SNR. This feature was added in order to provide an audio queue to operators in the process of aligning directional antennas. When your antenna reaches a position at which the highest pitch tone is heard you can lock it down without having to look at the signal graph display, knowing that you are receiving the best signal available. You can also adjust the tone pitch and volume with the sliders on the sound control.

.. |trade|  unicode:: U+00AE .. Registered Trademark SIGN
   :ltrim:
