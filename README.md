### Info de la Materia: Topicos Especiales en Telematica-st0263

### Estudiante: Miguel Angel Martinez Florez, mamartinef@eafit.edu.co

### Profesor:  Edwin Nelson Montoya Munera, emontoya@eafit.edu.co  

# Reto No 1 y 2 - P2P - Comunicación entre procesos mediante API REST, RPC.

## 1. Breve descripción de la actividad:

1.1 La implementación cumple con los requisitos funcionales y no funcionales propuestos, destacando la creación de un sistema P2P para compartir archivos con microservicios que utilizan gRPC para la comunicación RPC y REST para APIs. Se implementan funcionalidades de localización y compartición de archivos, concurrencia en el servidor, y configuración dinámica de nodos.

- **Microservicios para Servidor y Cliente:** Desarrollo de módulos específicos para funcionalidades de servidor y cliente, incluyendo búsqueda y transferencia de archivos.
- **Concurrencia:** Manejo de múltiples conexiones y solicitudes simultáneas mediante hilos.
- **Configuración Dinámica:** Uso de archivos de configuración para parámetros iniciales y adaptabilidad del sistema.

1.2 Un desafío pendiente es la efectividad en la respuesta del servidor inicial (pear de arranque), que si bien logra recibir las solicitudes y establecer las conexiones necesarias, aún no alcanza el nivel de respuesta esperado. Este aspecto crucial para la funcionalidad completa del sistema requiere una revisión detallada para asegurar una interacción fluida entre los nodos."


## 2. Información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas:

La arquitectura de diseño de alto nivel para el proyecto se basa en un sistema P2P no estructurado con microservicios para soportar la compartición de archivos. Se utilizan patrones de diseño como Cliente-Servidor para las interacciones entre nodos y el modelo Publicador-Suscriptor para la actualización y sincronización de archivos. Las mejores prácticas incluyen el uso de archivos de configuración para flexibilidad, el manejo de concurrencia mediante hilos, y el empleo de gRPC para llamadas a procedimientos remotos eficientes. La arquitectura modular facilita la escalabilidad y mantenimiento del sistema.


## 3. Descripción del ambiente de desarrollo y técnico: lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones:
![p2p2 drawio](https://github.com/migueflorez10/mamartinef-st0263/assets/68928440/06a13edc-e502-4737-8162-ab21714bf7ad)

**Lenguaje de programación:** Python, JavaScript.

- **Librerías/paquetes:** grpcio, grpcio-tools, requests, entre otros definidos en requirements.txt.

- **Cómo se compila y ejecuta:** La aplicación se ejecuta directamente con Python. La compilación de archivos .proto para gRPC se realiza mediante grpcio-tools.

- **Configuración del proyecto:** Los parámetros como IP, puerto, y directorio de archivos se configuran mediante archivos de configuración, permitiendo flexibilidad y adaptabilidad en diferentes entornos de ejecución.

### Cliente
- **Compilación del Protocolo gRPC:** Utilice el comando específico para compilar el archivo .proto y generar los stubs necesarios para la comunicación gRPC.
- **Instalación de Dependencias:** Ejecute pip install -r requirements.txt para instalar todas las dependencias especificadas.
- **Ejecución del Cliente:** Inicie el script main.py. Durante la ejecución, se le solicitará ingresar la IP pública para conectarse al servidor de arranque.

### Servidor de Arranque
- **Instalación de Node.js:** Siga los pasos para instalar Node.js utilizando el comando apropiado.
- **Arranque del Servidor:** Ejecute sudo node main.js para iniciar el servidor, el cual escuchará en el puerto 8000.
- **Configuración en AWS:** Tanto la IP como los puertos se deben configurar a través de AWS, tratando cada instancia como un peer diferente en la red.

El ambiente de desarrollo técnico se basa en Node.js para el backend, con el uso de librerías como net para TCP, @grpc/grpc-js y @grpc/proto-loader para gRPC, y fs para manejo de archivos. Las versiones específicas incluyen grpcio@1.62.0 y requests@2.31.0 entre otras. El proyecto se ejecuta mediante comandos de Node.js, por ejemplo, node main.js para iniciar el sistema. Los parámetros del proyecto como IP y puertos se configuran en archivos .js y .json, facilitando la adaptación a diferentes entornos.


## 4. Descripción del ambiente de Ejecucion
- Similar al ambiente de desarrollo, con énfasis en la ejecución en entornos de producción potencialmente distribuidos como AWS, donde se configuran IPs y puertos específicos.

- **IP o Nombres de Dominio:** Utiliza direcciones IP públicas o nombres de dominio configurados en tu proveedor de nube o en la máquina servidor.
- **Configuración de Parámetros:** Los parámetros como IP, puertos, y directorios se configuran en archivos config.json o similares. Esto permite ajustes dinámicos sin modificar el código. 
- **Ejemplo:** node main.js para arrancar el servidor.
- **Lanzamiento del Servidor:** Ejecuta node server.js desde la línea de comando en el directorio del proyecto para iniciar el servidor gRPC y el servidor TCP.
  
- **Guía de usuario:** La interacción con el sistema se realiza a través de la interfaz de línea de comandos, donde los usuarios pueden buscar y compartir archivos.

## 5. Información relevante adicional:
- La implementación demuestra un uso efectivo de patrones de diseño modernos y tecnologías para sistemas distribuidos. La modularidad y la capacidad de adaptación del sistema a diferentes entornos de red y configuraciones lo hacen robusto y versátil para su uso en diversos escenarios de compartición de archivos.

- La solución hace uso intensivo de concurrencia para manejar múltiples conexiones y solicitudes simultáneas, destacando la escalabilidad y la eficiencia en la gestión de recursos.
