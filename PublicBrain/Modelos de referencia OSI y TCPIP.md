# Modelos de referencia OSI y TCPIP

[[Aprender sobre Redes e Internet]]

Los modelos de referencia OSI (Open Systems Interconnection) y TCP/IP (Transmission Control Protocol/Internet Protocol) son dos enfoques fundamentales para comprender y describir la arquitectura de redes y la comunicación de datos. Aquí tienes información sobre ambos:

### Modelo OSI:

El Modelo de Interconexión de Sistemas Abiertos (OSI) es un modelo conceptual que divide las funciones de una red de computadoras en siete capas. Cada capa realiza funciones específicas y se comunica con las capas adyacentes para proporcionar una estructura organizada para el diseño y la comprensión de las redes. Las capas del modelo OSI son:

1. **Capa 1 - Física:** Trata con la transmisión física de datos sobre un medio de comunicación, como cables o fibras ópticas.

2. **Capa 2 - Enlace de Datos:** Se encarga de la detección y corrección de errores en los datos, así como del control de acceso al medio (MAC).

3. **Capa 3 - Red:** Es responsable de la dirección lógica y el enrutamiento de datos entre redes.

4. **Capa 4 - Transporte:** Maneja la segmentación y reensamblaje de datos, y proporciona servicios de control de flujo y corrección de errores.

5. **Capa 5 - Sesión:** Establece, mantiene y termina sesiones entre aplicaciones.

6. **Capa 6 - Presentación:** Se encarga de la traducción, cifrado y compresión de datos para garantizar la compatibilidad entre sistemas.

7. **Capa 7 - Aplicación:** Proporciona servicios de red a las aplicaciones y permite la interacción del usuario con la red.

### Modelo TCP/IP:

El Modelo de Protocolo de Interconexión de Red de Transmisión (TCP/IP) es otro modelo de referencia ampliamente utilizado en el diseño de redes, y consta de cuatro capas:

1. **Capa de Acceso a la Red (Link o Enlace):** Equivalente a las capas física y de enlace de datos del modelo OSI. Se encarga de la transmisión física de datos y del acceso al medio.

2. **Capa de Internet:** Correspondiente a la capa de red del modelo OSI. Gestiona la dirección lógica (IP) y el enrutamiento de datos entre redes.

3. **Capa de Transporte:** Similar a la capa de transporte del modelo OSI. Proporciona servicios de transporte confiable de extremo a extremo, con TCP (Control de Transmisión) y UDP (Protocolo de Datagramas de Usuario) como protocolos principales.

4. **Capa de Aplicación:** Combina las funciones de las capas de sesión, presentación y aplicación del modelo OSI. Incluye protocolos como HTTP, FTP, SMTP, entre otros.

### Diferencias clave:

- El modelo OSI tiene siete capas, mientras que el modelo TCP/IP tiene cuatro.
- La capa de sesión y presentación del modelo OSI está incorporada en la capa de aplicación del modelo TCP/IP.
- El modelo OSI es más descriptivo y teórico, mientras que el modelo TCP/IP es más práctico y se ha adaptado a la implementación de Internet.

Ambos modelos son útiles para entender la arquitectura de redes, y a menudo se utilizan en conjunto para describir la comunicación de datos en sistemas de red.
