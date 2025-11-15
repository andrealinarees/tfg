********COMANDOS EJECUCION********:
    1. xelatex memoria_tfg
    2. makeglossaries memoria_tfg
    3. bibtex memoria_tfg
    4. xelatex memoria_tfg
    5. xelatex memoria_tfg

Cosas que faltan:
-> Diagrama resumen de la BIC Platform (alto nivel) -> arquitectura de la plataforma
-> Diagrama de los módulos de BIC
-> Modelo de proceso Simple dentro de design de un BPMN
-> Diagrama de componentes detallado -> cliente, API, batch,  BD, elasticsearch...
-> Gráfica de tiempos de ejecución de jobs (?) crear un histograma p.e
-> Gráfico de sonarCloud -> coverage + duplicidad antes /después.
-> Para la última parte fase de rc de alsea
-> Añadir las citas de los gloasarios y acronimos que faltan que están comentados
-> Ver que la captura de la tabla de report esté bonita
-> Resolver comentarios del pdf suyo.

*Idea principal para el apartado 5:*

**Análisis** | Qué debe hacer el sistema -> Requisitos, actores, historias de usuario, descripción general de la arquitectura (cliente/servidor), interfaz original, modelo conceptual preliminar 
**Diseño**   | Cómo se implementará -> Decisiones técnicas, estructuras de datos, diseño de componentes, diagramas, interacciones, patrones y justificación de la arquitectura elegida       


5.1 Arquitectura tecnológica del sistema

Describe la estructura final elegida, más detallada que la del análisis:

Diagrama general de arquitectura (cliente, servidor, base de datos, integración con BIC y Elasticsearch).

Explica cómo se comunican los componentes (REST API, endpoints principales, JSON, etc.).

Justifica por qué se usa esa arquitectura (modularidad, separación de responsabilidades, mantenibilidad…).

Ejemplo:

Cliente → Angular 15

Servidor → Spring Boot 3 + Spring Batch

Almacenamiento → PostgreSQL

Infraestructura → Docker Compose

Migraciones → Flyway

Logs y monitorización → Spring Actuator

5.2 Diseño de la aplicación

Desglosa el diseño a nivel de componentes internos:

5.2.1 Cliente (Angular)

Estructura de módulos y componentes (ReportGenerator, ReportHistory, SharedModule).

Servicios Angular (report.service.ts, notification.service.ts, etc.).

Flujo de datos entre componentes.

Validaciones y feedback al usuario (mensajes, loaders, etc.).

Frameworks o librerías de interfaz (Angular Material, Bootstrap…).

5.2.2 Servidor (Spring Boot + Spring Batch)

Estructura de paquetes (controllers, services, repositories, batch, config...).

Patrón de diseño usado (por capas, inyección de dependencias, DTOs…).

Descripción del flujo de generación de informes:
Controller → Service → ProbeService → Spring Batch Job → Excel Generator → PostgreSQL

Diseño del Job y Step de Spring Batch (inputs, outputs, parámetros, etc.).

Diagrama de secuencia o flujo del batch.

5.2.3 Capa de datos

(Aquí moverías el modelo conceptual que ahora está en el cap. 4)

Explica la entidad ReportEntity y su relación con otras (si las hay).

Incluye el diagrama E-R o UML de la entidad.

Explica decisiones de diseño: por qué se usa bytea, cómo se gestiona la firma de duplicidad, índices, etc.

Justificación del esquema alsea_reports y uso de Flyway.

5.3 Interacción cliente–servidor

Diagrama de secuencia (por ejemplo: generación → consulta → descarga).

Descripción de los endpoints REST (/api/reports/generate, /api/reports/history, etc.).

Formato de las peticiones/respuestas JSON.

Manejo de errores y mensajes.

(Opcional si tienes espacio o lo ves útil)
5.4 Diseño de la interfaz

Mockups o capturas de las pantallas finales.

Justificación de la disposición de los elementos (usabilidad, accesibilidad, claridad visual).