### Info de la Materia: Topicos Especiales en Telematica-st0263

### Estudiante: Miguel Angel Martinez Florez, mamartinef@eafit.edu.co

### Profesor:  Edwin Nelson Montoya Munera, emontoya@eafit.edu.co  

# Reto No 1 y 2 - P2P - Comunicación entre procesos mediante API REST, RPC.

## 1. Breve descripción de la actividad:

1.1 La implementación cumple con los requisitos funcionales y no funcionales propuestos, destacando la creación de un sistema P2P para compartir archivos con microservicios que utilizan gRPC para la comunicación RPC y REST para APIs. Se implementan funcionalidades de localización y compartición de archivos, concurrencia en el servidor, y configuración dinámica de nodos.

1.2 Todos los aspectos de desarrollo fueron completados. 


## 2. Información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas:

Se adopta una arquitectura basada en microservicios dentro de una red P2P. Se utilizan gRPC y REST para la comunicación entre servicios, enfatizando la modularidad, la escalabilidad y la eficiencia en la gestión de conexiones concurrentes.


## 3. Descripción del ambiente de desarrollo y técnico: lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones:
**Lenguaje de programación:** Python, JavaScript.

- **Librerías/paquetes:** grpcio, grpcio-tools, requests, entre otros definidos en requirements.txt.

- **Cómo se compila y ejecuta:** La aplicación se ejecuta directamente con Python. La compilación de archivos .proto para gRPC se realiza mediante grpcio-tools.

- **Configuración del proyecto:** Los parámetros como IP, puerto, y directorio de archivos se configuran mediante archivos de configuración, permitiendo flexibilidad y adaptabilidad en diferentes entornos de ejecución.


## 4. Descripción del ambiente de Ejecucion
- Similar al ambiente de desarrollo, con énfasis en la ejecución en entornos de producción potencialmente distribuidos como AWS, donde se configuran IPs y puertos específicos.
  
- **Guía de usuario:** La interacción con el sistema se realiza a través de la interfaz de línea de comandos, donde los usuarios pueden buscar y compartir archivos.

## 4. Información relevante adicional:
- La implementación demuestra un uso efectivo de patrones de diseño modernos y tecnologías para sistemas distribuidos. La modularidad y la capacidad de adaptación del sistema a diferentes entornos de red y configuraciones lo hacen robusto y versátil para su uso en diversos escenarios de compartición de archivos.

- La solución hace uso intensivo de concurrencia para manejar múltiples conexiones y solicitudes simultáneas, destacando la escalabilidad y la eficiencia en la gestión de recursos.
