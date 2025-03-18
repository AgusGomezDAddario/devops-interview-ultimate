# Despliegue de aplicación Django + React.js

Este proyecto consiste en el despliegue de una aplicación web dockerizada, que cuenta con backend en Django y frontend en React.js. El despliegue de la misma puede realizarse tanto de manera local como en entornos cloud (como puede ser AWS).

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
