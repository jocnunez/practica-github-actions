# Práctica CI/CD

## Ejercicios de clase

#### 1. Proyecto con Docker Compose

El proyecto tendrá los siguientes servicios:

-   database:
    -   basado en la imagen de mongo
-   server:
    -   basado en la imagen de node
-   client:
    -   basado en la imagen de nginx

#### 2. Base de Datos Mongo persistida en un volumen

-   Configurar la DB para cargar por variables de entorno los datos sensibles

#### 3. Modificar Workflow

-   Usar secretos para cargar las variables de entorno
-   Modificar el changelog con los nuevos cambios
-   Release??

#### 4. Aplicación server en Node usando Fastify

-   Usaremos Fastify para crear una API RESTful que de servicio al cliente.
-   Conectaremos con la DB para persistir los datos

#### 5. Aplicación client

-   Generaremos un nuevo proyecto con Vite
-   Usaremos Typescript y Lit como librería
-   Usaremos el código de TodoMVC
