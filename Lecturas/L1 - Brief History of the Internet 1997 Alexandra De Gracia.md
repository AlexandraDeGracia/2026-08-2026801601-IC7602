 

Instituto Tecnológico de Costa Rica


 Escuela de Ingeniería en Computación 


Campus Tecnológico Central Cartago


 IC-7602 Redes


 Prof. Ing. Gerardo Nereo


II Semestre, 


2026  Trabajo hecho por: Alexandra Milagros De Gracia Calderon

 c. 2026801601 
11/08/26
L1 - Brief History of the Internet 1997
Preguntas:
1.       Explique cómo se originó el Internet.
Internet se fue desarrollando poco a poco gracias al trabajo de varios investigadores. En 1962, J.C.R. Licklider propuso la idea de una “Galactic Network”, donde diferentes computadoras pudieran estar conectadas y compartir información. Después, Leonard Kleinrock trabajó con la idea de la conmutación de paquetes y, en 1965, Lawrence Roberts logró conectar dos computadoras a larga distancia. Estos trabajos ayudaron a demostrar que se necesitaba una mejor forma de conectar computadoras. Más adelante, Roberts trabajó en ARPANET, una red que comenzó a funcionar en 1969 y que fue uno de los principales antecedentes de Internet.
2.       De acuerdo con la lectura, ¿Qué es circuit switching y packet switching?
El circuit switching, o conmutación de circuitos, era la forma de comunicación utilizada principalmente por las redes telefónicas. Para comunicarse, se establecía un circuito entre los dos puntos y la información viajaba por ese camino durante la llamada.
El packet switching, o conmutación de paquetes, funciona de otra manera. La información se divide en pequeños paquetes que pueden viajar por la red hasta llegar a su destino. Este método resultó más conveniente para conectar computadoras y fue muy importante para el desarrollo de ARPANET y posteriormente de Internet.
3.       ¿Qué tanto impacto causó las “Four ground rules” en el Desarrollo de las comunicaciones actuales? Base su respuesta en su conocimiento actual de cómo funcionan las redes, comunicaciones y el Internet.
Las “Four Ground Rules” tuvieron un impacto muy importante porque ayudaron a establecer la forma en que diferentes redes podían conectarse entre sí. Entre sus ideas estaba que cada red pudiera funcionar de manera independiente, que los paquetes se enviaran bajo el principio de “best effort” y que existieran dispositivos encargados de conectar las diferentes redes.
Estas ideas todavía se pueden ver en Internet actualmente. Por ejemplo, diferentes tecnologías como Wi-Fi, fibra óptica y redes móviles pueden conectarse y comunicarse dentro de Internet sin tener que funcionar exactamente de la misma manera. Por eso, estas reglas ayudaron a que Internet pudiera crecer y adaptarse con el paso del tiempo.

4.       Explique el rol de la documentación en las redes.
La documentación tuvo un papel muy importante en el desarrollo de Internet porque permitía compartir ideas y conocimientos entre las personas que trabajaban en las redes. En 1969 aparecieron los RFC (Request for Comments), que al principio eran documentos utilizados por los investigadores para compartir ideas y recibir comentarios de otros.
Con el tiempo, este sistema ayudó a mejorar las propuestas y a crear especificaciones que podían ser utilizadas por otras personas. Además, el hecho de que estos documentos fueran accesibles facilitó que estudiantes, investigadores y desarrolladores pudieran aprender y trabajar con estas tecnologías.
5.       En la lectura se mencionan múltiples dispositivos de red, así como protocolos, por ejemplo satélites, ethernet y routers (pero no se limita solo a estos), extraiga todos estos nombres de dispositivos y mediante alguna herramienta de Inteligencia artificial generativa (que se debe especificar), proporcione una definición de cada dispositivos en el ámbito de redes además pregunte ¿A que capa del modelo de referencia OSI pertenece el dispositivo o protocolo?

Dispositivos de Red y Tecnologías Físicas:
Satélites (Satellites): Dispositivos de comunicación ubicados en la órbita espacial que reciben y retransmiten señales electromagnéticas para proveer conectividad de red a enormes distancias o zonas de difícil acceso.
Capa OSI: Capa 1 (Física), ya que gestionan la transmisión a través del medio físico (el espacio libre mediante radiofrecuencia).
Ethernet: Estándar y tecnología de redes de área local (LAN) que define las características del cableado, los voltajes y el formato de las tramas de datos para la comunicación física.
Capa OSI: Capa 1 (Física) y Capa 2 (Enlace de datos).
Routers (Enrutadores): Dispositivos de hardware que interconectan múltiples redes IP. Analizan las direcciones de destino de los paquetes de datos y deciden la mejor ruta para enviarlos a través de la red.
Capa OSI: Capa 3 (Red).
Gateways (Puertas de enlace): Nodos de red que actúan como punto de entrada de una red a otra red externa. Suelen realizar tareas complejas como traducción de protocolos diferentes entre sistemas incompatibles.
Capa OSI: Típicamente operan en la Capa 3 (Red), aunque los Gateways de aplicación pueden llegar hasta la Capa 7 (Aplicación).
Interface Message Processors (IMPs): Fueron las primeras minicomputadoras utilizadas como conmutadores de paquetes en la red ARPANET. Son los ancestros directos de los routers modernos.
Capa OSI: Capa 3 (Red) y Capa 2 (Enlace de datos).
Hosts (Computadoras Personales, Workstations, Mainframes): Cualquier dispositivo o equipo informático de usuario final que esté conectado a la red y disponga de una dirección IP para enviar y recibir información.
Capa OSI: Al ser dispositivos finales, implementan la pila de red completa, desde la Capa 1 hasta la Capa 7.
Protocolos de Red:
NCP (Network Control Protocol): Protocolo utilizado en ARPANET para permitir la comunicación entre los hosts. La lectura indica que el Network Working Group terminó el protocolo inicial de comunicación host-to-host en 1970.
Capa OSI: principalmente relacionado con las funciones de Transporte, aunque no encaja perfectamente en el modelo OSI porque fue creado antes de este modelo.

TCP (Transmission Control Protocol): Protocolo que establece conexiones lógicas y garantiza que los datos se entreguen de forma íntegra, confiable, en orden y sin errores entre el origen y el destino.
Capa OSI: Capa 4 (Transporte).
IP (Internet Protocol): Protocolo principal responsable del direccionamiento de los equipos y del enrutamiento de los paquetes individuales a través del laberinto de redes que conforman el Internet.
Capa OSI: Capa 3 (Red).
UDP (User Datagram Protocol): Un protocolo alternativo a TCP que envía paquetes (datagramas) rápidamente sin verificar si llegaron o si están en orden. Es ideal para comunicaciones en tiempo real como voz o video.
Capa OSI: Capa 4 (Transporte).
FTP (File Transfer Protocol): Protocolo estándar utilizado para la transferencia bidireccional y administración de archivos entre un cliente y un servidor en una red.
Capa OSI: Capa 7 (Aplicación).
Telnet: Uno de los primeros protocolos diseñados para conectarse a otra computadora y administrarla de forma remota mediante una consola o terminal de texto.
Capa OSI: Capa 7 (Aplicación).
DNS (Domain Name System): El "directorio telefónico" de Internet, encargado de traducir nombres de dominio legibles por humanos (ej. google.com) en direcciones IP numéricas.
Capa OSI: Capa 7 (Aplicación).
SNMP (Simple Network Management Protocol): Protocolo que se utiliza para monitorizar, configurar y recolectar información sobre el estado de diversos dispositivos de red (routers, switches, servidores).
Capa OSI: Capa 7 (Aplicación).

