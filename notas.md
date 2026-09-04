********COMANDOS DE COMPILACIÓN********

    1. xelatex memoria_tfg
    2. makeglossaries-lite memoria_tfg
    3. bibtex memoria_tfg
    4. xelatex memoria_tfg
    5. xelatex memoria_tfg

Cosas que faltan:
-> Numerito final de los glosarios no está ok
-> creacion de los esquemas de flyway
-> diagrama 7.2 actualizar Visualmente es demasiado pequeño.

Además, por lo que se ve, la rama principal es duplicado sí/no, pero tu sistema tiene también:

NO_DATA,
FAILED,
validaciones,
descarga/historial.

Yo haría un diagrama algo más completo y más grande, posiblemente ocupando casi todo el ancho de página. explicar q esta echo con mermaid

-> añadir las 4 imágenes de sonar al apéndice y la de arquitectura detallada


Posibles preguntas:
- que son los servicios esos especializados? ElTasklet realiza conjuntamente la obtención de datos mediante ElasticsearchService y los servicios especializados, -> como hacemos exactamente las peticiones para estos datos de los informes???