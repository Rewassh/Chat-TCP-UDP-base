# Chat TCP/UDP - Proyecto Final

## Descripción

Aplicación de chat desarrollada en Unity que permite la comunicación bidireccional entre dos usuarios utilizando los protocolos TCP y UDP.

El sistema permite enviar y recibir:

- Mensajes de texto  
- Imágenes (con visualización en la interfaz)  
- Archivos PDF (guardados localmente)

La aplicación fue desarrollada desde cero utilizando sockets en C# y cumpliendo los requisitos funcionales establecidos en la rúbrica del proyecto.

---

## Características Principales

- Selección explícita del protocolo de comunicación (TCP o UDP) antes de iniciar la conexión.
- Selección de rol (Server o Client).
- Comunicación bidireccional entre dos instancias.
- Envío y recepción de:
  - Texto
  - Imágenes
  - Archivos PDF
- Visualización de imágenes recibidas en la interfaz.
- Almacenamiento automático de archivos recibidos.
- Funcionamiento completo y validado en ambos protocolos.

---

## Funcionamiento del Setup Panel

El Setup Panel es la sección inicial donde se configura la conexión antes de comenzar el chat.

Para utilizar la aplicación correctamente:

1. Seleccionar el protocolo de comunicación (TCP o UDP).
2. Elegir el rol:
   - Server: inicia el servidor y espera la conexión.
   - Client: se conecta al servidor.
3. Si se selecciona Client, ingresar la dirección IP del equipo que actúa como servidor.
4. Definir el puerto de comunicación (ambas instancias deben utilizar el mismo puerto).
5. Presionar el botón Conectar.

Una vez establecida la conexión, se habilita el panel de chat y se permite el intercambio de mensajes y archivos.

---

## Funcionamiento del Chat

En el Chat Panel el usuario puede:

- Enviar mensajes de texto.
- Enviar imágenes en formato PNG o JPG.
- Enviar archivos PDF.
- Limpiar el historial del chat.
- Desconectarse de la sesión activa.

Las imágenes recibidas se muestran directamente en la interfaz.  
Los archivos PDF recibidos se almacenan automáticamente en la carpeta local de la aplicación.

---

## Ubicación de Archivos Recibidos

Los archivos PDF recibidos se almacenan en la siguiente ruta del sistema:
C:\Users\USUARIO\AppData\LocalLow\CompanyName\ProductName\ReceivedFiles


Esta ruta corresponde al directorio `Application.persistentDataPath` de Unity.

---

## Diferencias entre TCP y UDP

### TCP
- Protocolo orientado a conexión.
- Garantiza la entrega y el orden de los mensajes.
- Maneja automáticamente la retransmisión de paquetes perdidos.
- Adecuado para transferencia confiable de datos y archivos.

### UDP
- Protocolo no orientado a conexión.
- No garantiza entrega ni orden de los paquetes.
- Presenta menor sobrecarga y mayor rapidez.
- Para la transferencia de archivos se implementó un sistema de fragmentación (START / CHUNK / END) y reconstrucción en el receptor.

---

## Justificación Técnica

Para cumplir con los requisitos del proyecto se implementó:

- Uso de sockets TCP y UDP en C#.
- Estructuración de mensajes mediante JSON.
- Fragmentación y reconstrucción manual de archivos en UDP.
- Manejo de tareas asíncronas para evitar bloqueo de la interfaz.
- Integración de StandaloneFileBrowser para selección de archivos en el ejecutable de Windows.

---

## Requisitos

- Sistema operativo Windows de 64 bits.
- Ejecución de dos instancias del archivo ejecutable.
- Uso del mismo protocolo y puerto en ambas instancias.

---

## Instrucciones de Ejecución

1. Ejecutar el archivo `.exe` en dos instancias.
2. En la primera instancia:
   - Seleccionar protocolo.
   - Elegir Server.
   - Definir puerto.
   - Presionar Conectar.
3. En la segunda instancia:
   - Seleccionar el mismo protocolo.
   - Elegir Client.
   - Ingresar la dirección IP del servidor.
   - Utilizar el mismo puerto.
   - Presionar Conectar.
4. Iniciar el intercambio de mensajes o archivos.

---

## Video Demostración

(https://youtu.be/svZ22q1DZes)

---

## Autor(es)

- Diva Catalina Rodriguez Acosta
- Juan Sebastian Muñoz Molina
