### Clasificar por alcance
Una forma comun de clasifica redes es por el tamaño del area que cubren: de un dispositivo personal a una red que conecta ciudades enteras

### Red Area Local (LAN)
Que es una LAN? Conecta dispositivos dentro de un espacio fisico unico: una casa, una oficina, un salon de clases o un solo edificio.

Caracteristicas: Es la red que una sola organizacion controla y administra por completo, suele tener alta velocidad u bajo costo por su alcance limitado

### Red inalambrica de Area Local(WLAN)
Que es una WLAN: Es una LAN que usa el espectro radio electrico en lugar de cables para conectar los dispisitivos dentro del mismo espacio
Caracteristicas: El acceso se hace a traves de uno o mas puntos de acceso(AP); a cambio de movilidad, el medio es compartido y mas sensible interferencia

### Red de area amplia (WAN)
Que es una WAN? Conecta redes que estan geograficamnte distantes, a veces en distintas ciudades, paises o continentes.

Caracteristicas: Ya no la administra una sola organizacion: suele depender de proveedores de telecomunicaciones, y su costo y latencia son mayores de una LAN.

Comparación por alcance De menor a mayor cobertura: PAN (una persona) → LAN / WLAN (un edificio) → Campus Area
Network(varios edificios de una organización) → WAN (distintas
ciudades o países).
La pregunta que las distingue No es la tecnología que usan, es quién la administra y qué tan lejos llega: eso es lo que determina si una red es LAN, CAN o WAN.

![[Pasted image 20260922203003.png]]

### ACTIVIDAD 2.2

Wifi 2-802.11.a
Wifi 4-802.11.n
Wifi 5-802.11.ac
Wifi 1-802.11.b
Wifi 3-802.11.g
Wifi 6-802.11.ax

| Wi-Fi       | Estándar IEEE | Frecuencia          |      Año | Velocidad máxima teórica |
| ----------- | ------------- | ------------------- | -------: | -----------------------: |
| **Wi-Fi 1** | 802.11b       | **2.4 GHz**         | **1999** |              **11 Mbps** |
| **Wi-Fi 2** | 802.11a       | **5 GHz**           | **1999** |              **54 Mbps** |
| **Wi-Fi 3** | 802.11g       | **2.4 GHz**         | **2003** |              **54 Mbps** |
| **Wi-Fi 4** | 802.11n       | **2.4 GHz y 5 GHz** | **2009** |             **600 Mbps** |
| **Wi-Fi 5** | 802.11ac      | **5 GHz**           | **2013** |             **6.9 Gbps** |
| Wi-Fi 6     | 802.11ax      | **2.4 GHz y 5 GHz** | **2019** |             **9.6 Gbps** |

### QUE ES EL INTERNET?
Es  la red de redes: millones de WAN, LAN 



### QUE LA HACE FUNCIONAR?
 Modelo tcp/ip y modelo osi:
![[Pasted image 20261013184726.png]]


### Capa de Aplicación
Es donde viven los programas y servicios que el usuario reconoce: navegación web, correo, mensajería. Agrupa lo que en OSI son tres capas separadas: aplicación, presentación y sesión.

### Capa de Transporte
Divide el mensaje en segmentos, agrega número de puerto de origen y destino, y decide si la entrega necesita confirmación (TCP) o no (UDP).

### Capa de Internet
Agrega las direcciones IP de origen y destino y es responsable de que el paquete encuentre su ruta entre redes distintas; aquí vive el protocolo IP.

### Capa de Acceso a la red
Agrega la dirección MAC del siguiente salto y convierte los datos en señal para el medio físico; agrupa lo que en OSI son las capas de enlace y física.