# Desplegar ExpressJS y PSQL en Heroku

## Secciones
- Requerimientos del trabajo.
- Ambiente de Desarrollo📋
  - DBeaver
  - Heroku Account
- Reproducir Proyecto
 
 ## Requerimientos del trabajo.
 
En nuestra empresa de desarrollo tenemos un cliente que desea un sistema que le permita
gestionar las tareas de su personal, parte de la necesidad de que el proceso de asignación y
creación de asignaciones es muy manual. Nosotros como desarrolladores le ofrecemos la
opción de desarrollar una API Rest con Express, en la cual el cliente pueda crear, listar y
eliminar tareas y además que el servicio pueda ser desplegado a producción con Heroku, lo
cual le permitirá a todos sus trabajadores acceder al servicio.

- Rutas para las vistas con Handlebars

![imagen](https://user-images.githubusercontent.com/68036938/162593922-f8083d86-3347-4663-b8b2-909ef0c1a866.png)

- API REST

![imagen](https://user-images.githubusercontent.com/68036938/162593945-9f83e131-8939-4e58-a11a-f8d65e0ff5c3.png)

## Ambiente de Desarrollo.
- DBeaver para crear las tablas y usuarios de prueba en el servidor de Heroku.
  - https://dbeaver.io/

- Cuenta en Heroku
  - https://id.heroku.com/login

## Reproducir Proyecto.

* Clonar el repositorio -
### HEROKU

- Crear una app en Heroku desde el dashboard:

![imagen](https://user-images.githubusercontent.com/68036938/162594103-7f38bd73-78c3-4466-8505-25454e375cbe.png)

![imagen](https://user-images.githubusercontent.com/68036938/162594108-d30d871c-0969-4ca4-8927-b624d1c1abd6.png)

- Instalar el plugin* de Heroku Postgres y seguir los pasos para su creación.

![imagen](https://user-images.githubusercontent.com/68036938/162594276-84c1cf0f-3527-40ae-826a-4436be7a8653.png)

![imagen](https://user-images.githubusercontent.com/68036938/162594294-18c0780d-02fa-480d-81a7-7b87d595e666.png)

- Una vez listo haremos click enÑ

![imagen](https://user-images.githubusercontent.com/68036938/162594310-f9f5ef7d-171e-45cf-8a4b-c8e12277f561.png)

- Iremos a Setting:

![imagen](https://user-images.githubusercontent.com/68036938/162594329-cfdcee27-5488-4760-8d02-c6bf325204ca.png)

- Vamos a "View Credentials", aquí tendremos toda la información necesaria para que nuestra app se conecte a la base de datos que creamos en Heroku:

![imagen](https://user-images.githubusercontent.com/68036938/162594359-d3225668-660b-4560-a266-824f976961aa.png)

![imagen](https://user-images.githubusercontent.com/68036938/162594403-6cb0fd8f-e3ea-4d73-8f92-c7218db80859.png)

### DBeaver

- Una vez abierto DBeaver, deberemos crear una nueva conexión, eligiendo PostgreSQL como DB:

![imagen](https://user-images.githubusercontent.com/68036938/162594438-791e6319-4316-4c98-b43f-388f237e63c8.png)

![imagen](https://user-images.githubusercontent.com/68036938/162594453-8c8d53d9-23ce-4b94-9cab-a996e06e1f64.png)

- Haremos uso de todas las credenciales entregadas por Heroku salvo URI y HerokuCLI.
- Probamos que los datos estén bien ingresados haciendo click en "Test Connection ..."

![imagen](https://user-images.githubusercontent.com/68036938/162594497-1360ecc4-7255-4de6-804d-0711cf62c461.png)

- Una vez listos, hacemos click derecho en la nueva conexión y creamos un nuevo script SQLÑ

![imagen](https://user-images.githubusercontent.com/68036938/162594511-0e4082c5-a517-4bbb-9939-62b17862562c.png)

- Y pegamos el contenido de "data.sql" del repositorio que descargaste y hacemos click en el botón señalado:

![imagen](https://user-images.githubusercontent.com/68036938/162594548-9a0d3f52-946e-47db-bf82-bd1ad38dd782.png)

### Proyecto

- Creamos la el archivo ".env" con las credenciales entregadas por PosgreSQL de Heroku.
  - PRIVATE_KEY puede tener el valor que vos quieras, es para JasonWebToken.

![imagen](https://user-images.githubusercontent.com/68036938/162594609-6ba0e2e3-680e-4717-9184-94c0205f84de.png)

- Debemos instalar Heroku CLI para por línea de comandos, desplegar nuestra aplicación. En el siguiente link encontrarás Heroku CLI para todos los SO https://devcenter.heroku.com/articles/heroku-cli
  - En la terminal escribimos:
    - heroku login
    - heroku git:remote -a {nombre del proyecto}
    - git checkout -b master
    - git push heroku master

### Ver App

- Puedes ver tu aplicación yendo a su DASHBOARD y haciendo click en "Open App":

![imagen](https://user-images.githubusercontent.com/68036938/162594726-eea13971-0223-490e-9ddc-a4f38285df31.png)

------------- FIN ---------------
