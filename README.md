# Despliegue de aplicación Django + React.js

Este proyecto consiste en el despliegue de una aplicación web dockerizada, que cuenta con backend en Django y frontend en React.js. El despliegue de la misma puede realizarse tanto de manera local como en entornos cloud (como puede ser AWS).

## 🌟 Características

- **Backend**: Django (API RESTful).
- **Frontend**: React.js (interfaz de usuario).
- **Base de datos**: PostgreSQL.
- **Despliegue**: Docker y Docker Compose.

## 🚀 Despliegue Local

### Requisitos previos 

- Contar con Docker instalado.
- Contar con Docker Compose instalado.
- Contar con Git instalado (una alternativa podria ser contar con el repositorio clonado en el almacenamiento local).

### Instrucciones

#### 1. Clonación de repositorio:
git clone {direccion-repo}
cd {nombre-repo}

#### 2. Levantamiento de contenedores:
docker-compose up --build

#### 3. Acceso a la aplicación mediante navegador:
🌐 Frontend: http://localhost:3000/
🌐 Backend: http://localhost:8000/

#### 4. Detención de los contenedores
Ctrl + C (en consola de comandos)
docker-compose down


## ☁️ Despliegue en AWS

### Requisitos previos

- Poseer una cuenta en AWS para crear una instancia EC2.
- Contar con Docker instalado.
- Contar con Docker Compose instalado.
- Contar con un par de claves SSH para conectarse a la instancia EC2.

### Instrucciones

#### 1. Crear una instancia EC2

1.1. **Creación de una instancia EC2 en AWS**: La configuración del grupo de seguridad debe permitir el tráfico en los siguientes puertos:
     - **22 (SSH)**: Para la conexión a la instancia.
     - **3000 (HTTP)**: Para el frontend (React.js).
     - **8000 (HTTP)**: Para el backend (Django).

1.2. **Conexión a la instancia**: Mediante SSH, se genera la conexión a la instancia:
ssh -i /ruta/a/tu-clave.pem ubuntu@<IP-PÚBLICA>

#### 2. Instalación de Docker y Docker Compose

2.1. **Actualizar el sistema**:
sudo apt update

2.2. **Instalación de Docker**
sudo apt install docker.io -y

2.3. **Instalación de Docker Compose**
sudo apt install docker-compose -y

2.4. **Agregar al usuario al grupo de Docker**
sudo usermod -aG docker $USER

2.5. **Reinicio de la sesión**
exit
ssh -i /ruta/a/tu-clave.pem ubuntu@<IP-PÚBLICA>

#### 3. Clonación del repositorio

git clone https://github.com/tu-usuario/tu-repositorio.git
cd tu-repositorio

#### 4. Levantamiento de contenedores
docker-compose up --build

#### 5. Acceso a la aplicación mediante navegador:
🌐 Frontend: http://<IP-PÚBLICA>:3000/
🌐 Backend: http://<IP-PÚBLICA>:8000/

#### 6. Detención de los contenedores
Ctrl + C (en consola de comandos)
docker-compose down
