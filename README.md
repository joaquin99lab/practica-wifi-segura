# Informe de Auditoría de Red Wi-Fi Insegura

## Introducción

En esta práctica se realizó un análisis básico del tráfico de red generado al acceder a un sitio web mediante una conexión HTTP. El objetivo fue comprender los riesgos de utilizar protocolos no cifrados en redes Wi-Fi públicas y analizar cómo una VPN puede mejorar la seguridad y privacidad de las comunicaciones.

El análisis se realizó utilizando las herramientas de desarrollador del navegador, observando las solicitudes de red realizadas al acceder al sitio **http://neverssl.com**.

---

## 1. Sitio analizado

El sitio utilizado para realizar la práctica fue:

**http://neverssl.com**

Este sitio utiliza deliberadamente el protocolo HTTP, permitiendo observar las características y los riesgos de una comunicación que no utiliza cifrado HTTPS.

### Protocolo utilizado

El protocolo utilizado es:

**HTTP (HyperText Transfer Protocol)**

A diferencia de HTTPS, HTTP no cifra la información transmitida entre el navegador y el servidor.

---

## 2. Evidencia observada

Al abrir las herramientas de desarrollador del navegador mediante `F12` y acceder a la pestaña **Network (Red)**, fue posible observar la solicitud realizada al sitio.

Entre los datos visibles se pueden identificar:

Sitio analizado: http://neverssl.com
Host observado: oldyoungbrightmelody.neverssl.com
URL solicitada: http://oldyoungbrightmelody.neverssl.com/online
Método HTTP: GET
Protocolo: HTTP
Código de respuesta: 307 Temporary Redirecta utilizado.

Estos datos permiten conocer información relacionada con la comunicación entre el navegador y el servidor.


## 3. Riesgos de utilizar HTTP en una red Wi-Fi pública

Utilizar HTTP en una red Wi-Fi pública presenta diferentes riesgos debido a que la comunicación no se encuentra cifrada mediante HTTPS.

Un atacante que consiga observar el tráfico de la red podría obtener información sobre las conexiones realizadas, como los sitios visitados, las solicitudes HTTP y determinados datos incluidos en los headers.

Además, si un usuario introduce información sensible en un sitio que utiliza HTTP, dicha información podría quedar expuesta durante la transmisión.

Entre los principales riesgos se encuentran:

* Interceptación del tráfico de red.
* Exposición de las URL y solicitudes realizadas.
* Obtención de información de los headers.
* Seguimiento de los sitios visitados.
* Posibilidad de modificar determinados datos transmitidos.
* Exposición de información sensible si el sitio no utiliza cifrado.

Por este motivo, no es recomendable utilizar sitios HTTP para ingresar contraseñas, datos bancarios u otra información confidencial.

---

## 4. Diferencia entre HTTP y HTTPS

### HTTP

HTTP transmite la información sin utilizar cifrado de extremo a extremo.

Puede compararse con una postal: la información viaja sin estar protegida mediante cifrado y puede ser más susceptible a la observación o manipulación durante el recorrido.

### HTTPS

HTTPS utiliza mecanismos de cifrado para proteger la comunicación entre el navegador y el servidor.

Puede compararse con una caja fuerte: aunque alguien pueda observar que existe una comunicación, el contenido está protegido mediante cifrado.

Por esta razón, siempre que sea posible se debe utilizar HTTPS, especialmente cuando se manejan datos personales, contraseñas o información financiera.

---

## 5. ¿Cómo ayuda una VPN?

Una VPN (Virtual Private Network) crea un túnel seguro y cifrado entre el dispositivo del usuario y el servidor VPN.

Cuando el usuario se conecta a una VPN, el tráfico de red se encapsula dentro de ese túnel y se transmite de forma cifrada.

### Cifrado

El cifrado transforma la información en datos que no pueden ser interpretados fácilmente por una persona que intercepte el tráfico.

### Encapsulamiento

El tráfico generado por el dispositivo se introduce dentro de una conexión protegida hacia el servidor VPN. Este proceso permite transportar los datos dentro del túnel VPN.

### Túnel seguro

La VPN crea un túnel cifrado a través de la red pública. Un atacante que consiga capturar los paquetes que circulan por la red Wi-Fi debería encontrar información cifrada en lugar del contenido original de las comunicaciones protegidas por la VPN.

### Protección del tráfico

La VPN ayuda a proteger el tráfico frente a personas que puedan estar observando la red Wi-Fi pública.

Sin embargo, una VPN no convierte automáticamente un sitio HTTP en HTTPS. Si el usuario accede a un sitio HTTP, la conexión entre el servidor VPN y el sitio web puede seguir utilizando HTTP.

Por eso, la VPN y HTTPS cumplen funciones complementarias.

---

## 6. 3 Reglas de Oro para utilizar redes Wi-Fi públicas

### Regla 1 – Evitar operaciones sensibles

No realizar operaciones bancarias, ingresar contraseñas importantes ni transmitir información confidencial utilizando redes Wi-Fi públicas que no sean de confianza.

### Regla 2 – Utilizar HTTPS y una VPN

Comprobar que los sitios web utilicen HTTPS y utilizar una VPN cuando sea necesario conectarse desde una red pública.

### Regla 3 – No confiar automáticamente en una Wi-Fi pública

No conectarse automáticamente a redes desconocidas y evitar realizar actividades sensibles mientras se está conectado a ellas.

---

## 7. Conclusión

El análisis permitió comprobar las diferencias entre HTTP y HTTPS y comprender los riesgos asociados con el tráfico no cifrado.

Al utilizar HTTP, determinados datos relacionados con las solicitudes pueden quedar expuestos a personas capaces de observar el tráfico de la red. Este riesgo aumenta cuando el usuario se encuentra conectado a una red Wi-Fi pública y no confiable.

El uso de HTTPS permite proteger la comunicación entre el navegador y el servidor mediante cifrado. Por otro lado, una VPN agrega una capa adicional de protección al crear un túnel cifrado y encapsular el tráfico entre el dispositivo y el servidor VPN.

Por lo tanto, las medidas recomendadas son utilizar HTTPS, evitar introducir información sensible en sitios HTTP, utilizar una VPN en redes públicas cuando corresponda y mantener una actitud preventiva al conectarse a redes Wi-Fi desconocidas.

