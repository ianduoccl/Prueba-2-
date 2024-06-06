# Prueba-2-
Prueba 2 del ramo Tecnologias de virtualizacion
# Nagios Core Docker Image

Este repositorio contiene los archivos necesarios para construir una imagen Docker con Nagios Core en Amazon Linux.

## Instrucciones para construir la imagen

1. Clonar el repositorio:
    ```sh
    git clone <URL_DEL_REPOSITORIO>
    cd <NOMBRE_DEL_REPOSITORIO>
    ```

2. Construir la imagen Docker:
    ```sh
    docker build -t nagios-core .
    ```

3. Ejecutar el contenedor:
    ```sh
    docker run -d -p 80:80 --name nagios-container nagios-core
    ```

## Acceso a la interfaz web de Nagios

Después de ejecutar el contenedor, puedes acceder a la interfaz web de Nagios en `http://localhost`.

## Archivos incluidos

- `Dockerfile`
- `nagios-init.sh`
- `entrypoint.sh`
- `README.md`
