Instituto Tecnologico de Costa Rica

Escuela de Ingeniería en Computación

Campus Tecnológico Central Cartago

IC-7602 Redes

Prof. Ing. Gerardo Nereo

II Semestre,

2026 Trabajo hecho por: Alexandra Milagros De Gracia Calderón

c. 2026801601

29/08/26

L3 - Network Media Types

Preguntas
1. ¿En qué consiste la comunicación Wireless?

La comunicación inalámbrica es básicamente la forma de transmitir datos entre dispositivos sin necesitar un cable físico que los conecte. En su lugar, se usan ondas electromagnéticas, ya sea en forma de radiofrecuencia (RF) o infrarrojo (IR), que viajan por el aire (o incluso por el vacío, como en el caso de las señales satelitales).

Para que esto funcione en una red, hace falta un punto de acceso, que es el que se encarga de distribuir la señal a todos los equipos conectados, y del lado del usuario, el PC o laptop necesita una tarjeta de red inalámbrica (NIC wireless) para poder captar esa señal.

Estas señales trabajan en un rango de frecuencias bastante amplio, que va desde los 3 kHz hasta los 300 GHz, y pueden alcanzar velocidades de transmisión de hasta 54 Mbps (dependiendo del estándar que se use). Las redes WLAN, que son las más comunes hoy en día, siguen los estándares IEEE 802.11 y suelen trabajar con ondas de radio, microondas (como el conocido 2.4 GHz) o infrarrojo.

En la práctica, esta tecnología la usamos todos los días sin darnos cuenta: cuando nos conectamos a internet desde el celular, cuando usamos un teclado o mouse inalámbrico, o cuando dos dispositivos intercambian información por Bluetooth o algo similar.

2. ¿Cuál es la diferencia entre los dos modos de fibra óptica?

Existen dos tipos de fibra óptica y la diferencia entre ellas tiene que ver con cómo viaja la luz dentro del cable.

La fibra monomodo deja pasar un solo haz de luz (un solo "modo") a través del núcleo, y para generar esa luz se usa un láser. Esto le permite alcanzar distancias mucho mayores —más de 10 km sin necesidad de repetidores— y velocidades más altas, por lo que normalmente se usa para conectar backbones entre edificios o campus completos. Eso sí, es la opción más cara de las dos.

La fibra multimodo, en cambio, permite que viajen varios haces de luz al mismo tiempo dentro del núcleo, usando LEDs como fuente de luz en lugar de láser. Su alcance es más limitado (hasta unos 2 km) y se usa más que todo dentro de un mismo edificio, por ejemplo para conectar pisos entre sí.

Buscando un poco más de información en internet, encontré que la razón detrás de esta diferencia está en el grosor del núcleo de la fibra: en la monomodo el núcleo es muchísimo más delgado, lo que obliga a la luz a viajar prácticamente en línea recta. En la multimodo el núcleo es más ancho, entonces la luz rebota en distintos ángulos mientras avanza, lo que provoca lo que se conoce como dispersión modal. Esa dispersión es justamente lo que hace que la señal se degrade más rápido y por eso la multimodo no puede cubrir distancias tan largas como la monomodo.

3. ¿Qué importancia tiene el par trenzado en la comunicación en una LAN desde el punto de vista electromagnético?

El hecho de que los cables vengan trenzados no es un detalle de fabricación al azar, tiene una razón física bien concreta. Cuando circula corriente eléctrica por un cable, se genera a su alrededor un pequeño campo magnético. Si se ponen dos cables juntos formando un circuito, sus campos magnéticos terminan quedando en direcciones opuestas, entonces se cancelan entre sí, y de paso también ayudan a cancelar cualquier interferencia magnética que venga de afuera.

Ahora bien, al trenzar los cables ese efecto de cancelación se vuelve todavía más fuerte. Es como si el propio diseño del cable —sin necesidad de agregarle una malla metálica extra— ya le diera cierta protección natural contra el ruido. Por eso el UTP, que no tiene blindaje como tal, logra funcionar bien a pesar de no estar "protegido" físicamente: su protección viene precisamente del trenzado.

Otro detalle importante es que dentro de un mismo cable, cada par tiene una cantidad distinta de vueltas por metro. Esto se hace a propósito para reducir el crosstalk, es decir, para que un par no le meta ruido al par de al lado.

En pocas palabras: gracias al trenzado, el par trenzado logra limitar bastante bien la interferencia electromagnética (EMI) y la interferencia de radiofrecuencia (RFI), sin necesitar un blindaje adicional.

4. ¿Cuál es la importancia del "shield" (blindaje) en los medios de transmisión cableados?

El blindaje es esa capa metálica —puede ser una malla trenzada de cobre o una lámina— que envuelve los conductores internos de un cable, y su trabajo es proteger la señal del ruido eléctrico, tanto el que se genera dentro del mismo cable (crosstalk entre pares) como el que viene de fuentes externas (EMI y RFI).

En el capítulo aparece en dos medios distintos:

En el STP, cada par de cables va envuelto en su propia lámina metálica, y además los cuatro pares juntos quedan cubiertos por un blindaje general. Esto hace que el STP resista mejor las interferencias que el UTP, aunque tiene su costo: es más caro y más complicado de instalar.

En el cable coaxial, la malla o lámina metálica cumple una doble función: además de servir como blindaje, actúa como el segundo conductor del circuito eléctrico, junto con el conductor de cobre en el centro.