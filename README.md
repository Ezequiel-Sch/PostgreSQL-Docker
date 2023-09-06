# Creación de Base de Datos (PostgreSQL) en Docker


## Conexión
En el presente archivo se detallara la forma de crear una base de datos SQL dentro de un contenedor Docker en un servidor `onPremise`.
El siguiente procedimiento se puede realizar conectándose directamente al servidor (con un monitor y teclado) o remotamente.

Para conectarse remotamente al servidor podemos utilizar un cliente SSH como `Putty` el cual se puede obtener desde el siguiente link: https://www.putty.org/

En este instructivo se utilizara la consola de Windows en vez de utilizar un cliente SSH, para esto es necesario abrir una ventana de comandos (cmd) e ingresar el siguiente comando:

`ssh <nombre_de_usuario>@<direccion_IP> `

>Ejemplo:  `ssh user1@XXXX.XXXX.XXXX.XXXX`

## Docker

Se da por hecho que el usuario ya cuenta con Docker en su servidor,por lo que se detallará solo la creacion del docker de PostgreSQL.

### Obtener la imagen del Docker

Una vez conectado al servidor debemos ejecutar el siguiente comando para descargar la imagen de Docker de PostgreSQL. 

`docker pull postgres` 

Link de la documentación oficial de la imagen: https://hub.docker.com/_/postgres

### Creación del contenedor

Si se ejecuta en la terminal:

`docker run postgres`

Se creará un contenedor genérico, y debera el usuario entrar en el contenedor para crear la Base de Datos.


### Creación del contenedor y la BD en el mismo comando

Si deseamos una Base de Datos (DB) debemos agregarle los `flags` necesarios al comando `docker run postgres`.

Agregando los flgas el comando anterior quedaria:

`docker run  --name  <container-name> -e POSTGRES_USER=<db-user> -e POSTGRES_PASSWORD=<db-password>  -e POSTGRES_DB=<db-name> -p 5432:5432 -d postgres`




