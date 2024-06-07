# Nagios Core Docker Deployment #

## Prerrequisitos ##

- AWS EC2 instance con Ubuntu.
- Docker instalado.
- Git instalado.

## Pasos para desplegar Nagios Core en Docker ##

1. Crear y configurar el directorio de trabajo

```bash
mkdir /opt/nagios-core-docker-v1
cd /opt/nagios-core-docker-v1

2. Descargar y extraer Nagios Core, Nagios Plugins y NRPE
wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.4.9.tar.gz
sudo tar xzf nagios-4.4.9.tar.gz

wget https://github.com/nagios-plugins/nagios-plugins/releases/download/release-2.4.2/nagios-plugins-2.4.2.tar.gz
sudo tar xzf nagios-plugins-2.4.2.tar.gz

wget https://github.com/NagiosEnterprises/nrpe/releases/download/nrpe-4.1.0/nrpe-4.1.0.tar.gz
sudo tar xzf nrpe-4.1.0.tar.gz

3. Verificar los archivos descargados
ls
ls -l

4. Crear los archivos necesarios para Docker
vim Dockerfile
vim .env
vim start.sh

5. Instalar Docker
sudo apt update
sudo apt install -y docker.io

6. Construir la imagen Docker
docker build -t nagios-core:4.4.9 .

7. Verificar la imagen Docker
docker images

8. Ejecutar el contenedor Docker
docker run --name nagios-core-4.4.9 -dp 80:80 nagios-core:4.4.9
docker run --name nagios-core-2 -dp 80:80 nagios-core:4.4.9 (FUNCIONAL)

9. Acceder a Nagios
http://ip publica de nagios:80 (NAGIOS)

Pasos para subir el proyecto a GitHub
1. Instalar Git
sudo apt install git

2. Configurar Git
git --version
git config --global user.name "usuario git"
git config --global user.email "mail git"

3. Inicializar el repositorio Git
cd /opt/nagios-core-docker-v1
git init

4. Añadir y commitear los archivos
git add .
git commit -m "prueba2"

5. Añadir el repositorio remoto y subir los cambios
git remote add origin https://github.com/ianduoccl/Prueba-2-.git
git remote remove origin
git remote add origin https://correogit:TOKEN@github.com/usuariogit/Prueba-2-.git
git push -u origin master

