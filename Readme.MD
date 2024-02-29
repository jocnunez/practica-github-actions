# Práctica de Despliegue de Aplicaciones Web

## 📚 Proyecto base con Docker Compose

El proyecto base es una aplicación típica de lista de tareas divida en tres partes:

- una base de datos MongoDB
- una API REST hecha en Node con la librería Fastify (basada en Express)
- un front hecho con Solid.js (versión simplificada de React (sin VirtualDOM))

Puedes encontrar información sobre Docker Compose en la web oficial <https://docs.docker.com/compose/gettingstarted/>

---

### :green_book: Base de Datos MongoDB

Características de la MongoDB:

- Incluye las variables de entorno **MONGO_INITDB_ROOT_USERNAME** y **MONGO_INITDB_ROOT_PASSWORD** por lo que estará securizada de inicio
- También se incluye la VE **MONGO_INITDB_DATABASE** así que esa DB estará creada de inicio y será la que usemos para nuestra app
- Por último para nuestro caso de uso se creará un usuario con permisos para escribir en esa DB, pasando sus datos también por VEs
- Para crear el usuario usaremos un script **./db/init-mongo.sh** que pasaremos por el Docker Entrypoint del contenedor de la DB

[:pencil:] En este servicio no hay que hacer ningún cambio. Lo único que necesitaremos será añadir las Variables de Entorno a github como **secretos** para que funcione nuestro workflow.

---

### :orange_book:   Aplicación server en Node usando Fastify

- Usaremos Fastify para crear una API RESTful que de servicio al cliente.
- Conectaremos con la DB para persistir los datos
- Tendrá test unitarios con Jest

---

### :blue_book: Aplicación client hecha en Solid.js

- Generaremos un nuevo proyecto con Vite
- Usaremos Typescript y Lit como librería
- Usaremos el código de TodoMVC

---

### :closed_book: GitHub Workflows

- Usar secretos para cargar las variables de entorno
- Modificar el changelog con los nuevos cambios
- Release??

---

### :pencil: Ejercicios

- :pencil: Modifica el workflow para que se lancen los tests de la app de servidor y que solo deje mergear cuando dichos tests pasen. (<span style="color:yellow;">1,5 puntos</span>)
- :pencil: Crea los tests E2E necesarios para cubrir todas las operaciones del CRUD sobre las tareas (<span style="color:yellow;">1,5 puntos</span>)
- :pencil: Modifica la aplicación tanto en el lado del cliente como del servidor para completar la funcionalidad (update y delete) (<span style="color:yellow;">2 puntos</span>)
- :pencil: Haz los test unitarios necesarios para cubrir las modificaciones del punto anterior (<span style="color:yellow;">2 puntos</span>)

Para los dos siguiente ejercicios si no pueden hacerlos únicamente siguiendo la documentación de github, el miércoles lo veremos en clase:

- :pencil: Crea un workflow para que al sacar release se actualice el changelog.md con los cambios que incluya la versión. Los cambios serán los nombres de los commits. (<span style="color:yellow;">1,5 puntos</span>)
- :pencil: Crea un workflow que publique las imagenes de Docker del cliente y del servidor en tu espacio de docker hub al hacer una release. (<span style="color:yellow;">1,5 puntos</span>)

Además de los ejercicios se tendrá en cuenta otros factores, como la limpieza de código, la calidad de la presentación (en cuanto a fluidez, concreción y coherencia con el código) o cualquier extra que se quiera añadir a la práctica (nuevo workflow, ...) (<span style="color:yellow;">1,5 puntos</span>)
