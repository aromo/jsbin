# Introducción

El proyecto docker-jsbin contiene un contenedor desplegable que descargará la última versión de JSBIN (Tiene un referencia al master oficial)

El proyecto de pennyworth es un Servidor Node-js que es el recomendado para añadir componentes como Sass (Sass necesita ruby así que la compilación en JSBIN se hace en remoto)

La arquitectura es una instalación de docker-jsbin en una máquina y en la misma u otra levantar el servidor de pennyworth que creará websockets usando AXON apuntando a la URL y puerto de JSBIN.

# Comandos

## Docker-JSBIN

(Ver Archivo Makefile)

Se pueden ejecutar tareas por separado, por ejemplo solo para lanzar JSBIN una vez instalado sería "make run-container"

El orden para una instalación desde 0 sería, 

``
make install
``

``
make build
``

``
make run
``

## Pennyworth

Arrancar el servidor node

`HOST=XXXXXX PORT=XXXX node lib/server.js`

# Referencias

- [Docker-jsbin] (https://github.com/qband/docker-jsbin)
- [Pennyworth] (https://github.com/jsbin/pennyworth)
