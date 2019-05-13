![odoo](https://user-images.githubusercontent.com/31807256/57650844-606d6300-7591-11e9-880d-f982be50c2ed.png)
# OdooDockerCompose
_El siguiente repositorio contiene un entorno de Odoo haciendo uso de Docker Compose._

## Docker-Compose
_Compose es una herramienta para definir y ejecutar aplicaciones Docker de múltiples contenedores. Docker-Compose, utiliza un archivo YAML para configurar los servicios de su aplicación. Luego, con un solo comando, puede crear e iniciar todos los servicios desde su configuración._

## Odoo 

_Odoo es un software de ERP (sistemas de planificación de recursos empresariales) integrado. Nosotros haremos uso de su version de gestión de proyectos._

_Nos permite programar un equipo con trabajadores en distintos proyectos teniendo en cuenta las vacaciones de cada empleado. Planificar con antelación tareas para el futuro con previsiones basadas en datos comparables de proyectos pasados y estimar fechas límite con más precisión. Ademas compara previsiones con hojas de horas reales para aumentar la rentabilidad. Esto nos permite optimizar el rendimiento de nuestro proyecto._

## Procedimiento 
_Primero hemos de crear una configuración de Docker-Compose, la cual llamaremos docker-compose.yml como se muestra a continuación._
      
```
version: '2'
services:
  web:
    image: odoo:12.0
    depends_on:
      - mydb
    ports:
      - "8069:8069"
    environment:
    - HOST=$nombre
    - USER=$usuario
    - PASSWORD=$contrasena
  mydb:
    image: postgres:10
    environment:
      - POSTGRES_DB=$postgresdb
      - POSTGRES_PASSWORD=$postgrespw
      - POSTGRES_USER=$postgresuser
      
```
_La forma más fácil de ejecutar este contenedor es en modo privilegiado, ya que tendrá todos los permisos y el acceso necesarios para construir contenedores de ventana acoplable._

_Para montar la aplicacion simplemente ejecutamos: docker-compose up Una vez que el servicio esté listo, puede acceder a él desde el navegador con localhost:8080._

## Autores 

**Cristian Camilo Cuervo Castillo - 20142020010
**Edvard Frederick Bareño Castellanos - 20142020014
**Neider Alejandro Fajardo Cardona - 20142020025

## Referencias
* https://www.odoo.com/es_ES/page/project-management
* https://docs.docker.com/compose/
