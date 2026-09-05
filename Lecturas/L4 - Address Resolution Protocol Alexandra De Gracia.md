Instituto Tecnológico de Costa Rica

Escuela de Ingeniería en Computación

Campus Tecnológico Central Cartago

Redes IC-7602

Prof. Ing. Gerardo Nereo

II Semestre,

2026 Trabajo hecho por: Alexandra Milagros De Gracia Calderón

c. 2026801601

05/09/26

L4 - Address Resolution Protocol

Desarrollo
1. ¿En qué consiste ARP?
   
El Address Resolution Protocol (ARP) es uno de los principales protocolos que forman parte de la suite TCP/IP. Su principal propósito consiste en realizar la correspondencia o mapeo entre una dirección lógica y una dirección física. Específicamente, ARP permite convertir una dirección IPv4 de 32 bits, considerada una dirección lógica, en una dirección física MAC de 48 bits.
Este protocolo es necesario debido a que las aplicaciones de red utilizan direcciones IPv4 para establecer comunicación con otros dispositivos. Sin embargo, en la capa de enlace de datos, el direccionamiento se realiza mediante direcciones MAC, las cuales corresponden a la dirección física de la tarjeta de red.
Por lo tanto, cuando una aplicación necesita comunicarse con otro dispositivo dentro de una Red de Área Local (LAN) y conoce su dirección IPv4, ARP se utiliza para encontrar la dirección MAC que corresponde a esa dirección IP. Una vez obtenida la dirección física, es posible realizar la comunicación a través de la red local.
En otras palabras, ARP funciona como un mecanismo que permite relacionar la dirección lógica utilizada por los protocolos de red con la dirección física necesaria para la transmisión de datos en la capa de enlace. 

3. ¿Cómo funciona ARP?
El funcionamiento de ARP se realiza mediante un proceso compuesto por siete pasos. Este proceso permite que un dispositivo encuentre la dirección física de otro dispositivo cuando solamente conoce su dirección IP.

Paso 1: El emisor conoce la dirección IP del destino
El proceso comienza cuando el dispositivo emisor conoce la dirección IP del dispositivo al que desea enviar información. Sin embargo, todavía no conoce la dirección MAC correspondiente a ese dispositivo.

Paso 2: Creación de la solicitud ARP
El protocolo IP solicita a ARP que cree un mensaje de solicitud denominado ARP Request. En este mensaje se incluyen:
•	La dirección física del dispositivo emisor. 
•	La dirección IP del dispositivo emisor. 
•	La dirección IP del dispositivo destino. 
Como la dirección MAC del destino todavía es desconocida, el campo correspondiente a la dirección física del destino se llena con ceros.

Paso 3: Encapsulación y envío de la solicitud
El mensaje ARP pasa a la capa de enlace de datos. Allí, el mensaje se encapsula dentro de una trama.
La dirección MAC del dispositivo emisor se utiliza como dirección de origen, mientras que como dirección de destino se utiliza una dirección física de broadcast. Esto permite que la solicitud sea recibida por todos los dispositivos de la red local.

Paso 4: Recepción de la solicitud por los dispositivos
Todos los hosts y routers de la red reciben la trama debido a que fue enviada mediante broadcast. Cada dispositivo examina la solicitud ARP.
Los dispositivos que no son el destino descartan el paquete. El dispositivo cuya dirección IP coincide con la dirección IP buscada reconoce que la solicitud está dirigida a él.

Paso 5: Envío de la respuesta ARP
El dispositivo destino crea un mensaje denominado ARP Reply. En esta respuesta proporciona su dirección física o dirección MAC.
A diferencia de la solicitud ARP, que se transmite mediante broadcast, la respuesta ARP se transmite mediante unicast, es decir, directamente hacia el dispositivo que realizó la solicitud.

Paso 6: El emisor recibe la dirección MAC
El dispositivo emisor recibe el mensaje ARP Reply y obtiene la dirección física del dispositivo destino.
A partir de este momento, el emisor ya conoce la relación entre la dirección IP del destino y su dirección MAC.

Paso 7: Envío de los datos
Después de conocer la dirección física del destino, el datagrama IP que contiene la información puede encapsularse dentro de una trama y enviarse directamente al dispositivo destino mediante unicast.
De esta manera, ARP permite obtener la dirección MAC necesaria para que la comunicación pueda realizarse correctamente dentro de la red. 

5. ¿Cuáles considera son las ventajas y desventajas de Static y Dynamic Mapping?
Se muestra dos métodos para establecer la relación entre una dirección lógica y una dirección física: Static Mapping y Dynamic Mapping.
Static Mapping
El mapeo estático consiste en crear una tabla que relaciona una dirección lógica con una dirección física. Esta tabla se almacena en cada máquina de la red.
Por ejemplo, si una máquina conoce la dirección IP de otra máquina, pero no conoce su dirección física, puede buscar la dirección MAC correspondiente dentro de la tabla.

Ventajas del Static Mapping
Una ventaja del mapeo estático es que permite mantener previamente establecida una relación entre las direcciones IP y las direcciones físicas. La información necesaria se encuentra almacenada en una tabla, por lo que una máquina puede consultar la correspondencia entre una dirección lógica y una dirección física.
Además, cada dispositivo de la red puede disponer de una tabla con la información de las direcciones que necesita conocer.
Desventajas del Static Mapping
La principal desventaja del mapeo estático es que las direcciones físicas pueden cambiar. Se presenta varias situaciones en las que esto puede suceder:
1.	Una máquina puede cambiar su NIC o tarjeta de red, lo cual provoca que tenga una nueva dirección física. 
2.	En algunas redes LAN, como LocalTalk, la dirección física puede cambiar cada vez que se enciende el computador. 
3.	Un computador móvil puede trasladarse de una red física a otra, lo que puede provocar un cambio en su dirección física. 
Debido a estos cambios, las tablas de mapeo estático deben actualizarse periódicamente. Se indica que esta actualización genera una sobrecarga (overhead) que puede afectar el rendimiento de la red.
Por lo tanto, aunque el mapeo estático permite almacenar previamente las asociaciones entre direcciones, requiere mantenimiento constante cuando se producen cambios en las direcciones físicas. 

Dynamic Mapping
El mapeo dinámico funciona de manera diferente al mapeo estático. En este caso, cada vez que una máquina conoce la dirección lógica de otra máquina, puede utilizar un protocolo para encontrar su dirección física.
Existen dos protocolos diseñados para realizar el mapeo dinámico:
•	ARP (Address Resolution Protocol). 
•	RARP (Reverse Address Resolution Protocol). 
ARP realiza el mapeo de una dirección lógica hacia una dirección física. Es decir, permite obtener una dirección MAC cuando se conoce una dirección IP.
Por otro lado, RARP realiza el proceso contrario, es decir, mapea una dirección física hacia una dirección lógica. Sin embargo, se señala que RARP fue reemplazado por otro protocolo y, por esta razón, el contenido se enfoca principalmente en ARP.

Ventajas del Dynamic Mapping
La principal ventaja del mapeo dinámico es que permite encontrar la dirección física cuando se conoce la dirección lógica utilizando un protocolo.
Además, no requiere depender únicamente de una tabla creada y actualizada manualmente, ya que el protocolo puede realizar la búsqueda de la dirección física cuando es necesaria.
Este método permite realizar el proceso de correspondencia entre direcciones de forma dinámica.

Desventajas del Dynamic Mapping
De acuerdo con el funcionamiento para obtener una dirección física es necesario realizar un proceso de resolución utilizando un protocolo.
Por ejemplo, en el caso de ARP, se debe crear una solicitud, transmitirla a través de la red y esperar una respuesta del dispositivo correspondiente antes de conocer su dirección física.
Por ello, a diferencia del mapeo estático, donde la información se encuentra previamente almacenada en una tabla, el mapeo dinámico necesita realizar un proceso de comunicación para encontrar la dirección física correspondiente.
En conclusión, el Static Mapping utiliza tablas previamente creadas, pero requiere actualizaciones periódicas cuando cambian las direcciones físicas. El Dynamic Mapping, en cambio, utiliza protocolos como ARP para obtener la dirección física cuando esta es necesaria. 

4. ¿Cuáles son las aplicaciones de un Proxy ARP?
Se describe Proxy ARP como una técnica utilizada para crear un efecto de subnetting, es decir, para permitir que una red funcione como si estuviera subdividida.
Un Proxy ARP funciona mediante un router que actúa en nombre de un conjunto de hosts o dispositivos.
Cuando un router que utiliza Proxy ARP recibe una solicitud ARP que busca la dirección IP de uno de los hosts que representa, el router responde a la solicitud proporcionando su propia dirección física o dirección MAC.
Después de que el router recibe el paquete IP real, se encarga de enviar dicho paquete al host o router apropiado.
Una de las principales aplicaciones tiene la posibilidad de crear una subred sin necesidad de realizar modificaciones en todo el sistema para que este reconozca las direcciones correspondientes a la nueva subred.
Se presenta el caso en el que un administrador necesita crear una subred, pero no desea modificar todo el sistema para que reconozca las direcciones de subred. Como solución, se puede agregar un router que ejecute Proxy ARP.
En este caso, el router actúa en nombre de todos los hosts que se encuentran dentro de la subred. Cuando recibe una solicitud ARP cuya dirección IP de destino coincide con la dirección de uno de los hosts protegidos, el router responde anunciando su propia dirección de hardware como la dirección física del destino.
Posteriormente, cuando el router recibe el paquete IP, este se encarga de enviarlo al host apropiado.
Por lo tanto, las aplicaciones principales del Proxy ARP son:
•	Actuar en nombre de un conjunto de hosts. 
•	Crear un efecto de subnetting. 
•	Permitir la creación de una subred sin modificar todo el sistema. 
•	Responder solicitudes ARP utilizando la dirección MAC del router. 
•	Recibir posteriormente los paquetes IP y reenviarlos hacia el host o router correspondiente. 

5. ¿Cómo funciona el ARP spoofing?
Según lo que entendí después de estudiar el funcionamiento de ARP en el ARP spoofing ocurre cuando se aprovecha el proceso mediante el cual ARP relaciona una dirección IP con una dirección MAC. En este caso, se proporciona información falsa para que un dispositivo asocie una dirección IP con una dirección MAC que no corresponde realmente.
Yo lo entiendo como una especie de engaño dentro de la red, porque ARP normalmente busca la dirección MAC correcta de un dispositivo para poder enviarle la información. Sin embargo, con ARP spoofing se puede hacer que un dispositivo crea que una dirección MAC falsa pertenece a otro equipo.
Esto puede provocar que la información sea enviada hacia un lugar incorrecto o que pase primero por otro dispositivo antes de llegar a su destino. Por esta razón, ARP spoofing representa un problema de seguridad en las redes loca

Conclusión
En conclusión, ARP es un protocolo importante porque permite relacionar las direcciones IP con las direcciones MAC para que los dispositivos puedan comunicarse dentro de una red local. Además, comprender su funcionamiento, el mapeo estático y dinámico, y Proxy ARP ayuda a entender mejor cómo se realiza la comunicación entre dispositivos en una red.

Referencia en formato IEEE
[1] A. K. Idrees, “Address Resolution Protocol (ARP),” Communication and Computer Networks, Department of Computer Science, University of Babylon, pp. 1–7.



