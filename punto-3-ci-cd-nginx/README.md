# 🚀 CI/CD para Nginx con GitHub Actions

Este proyecto implementa un pipeline de CI/CD para automatizar el despliegue de un servidor Nginx. Cada vez que se realiza un cambio en el archivo `index.html`, se construye una nueva imagen de Docker, se sube a un registro de contenedores (como Docker Hub) y se despliega en un entorno de producción.

## 📌 Requisitos previos

Antes de iniciar, asegurate de tener lo siguiente:

- **Docker** instalado.
- **Docker Hub** (o cualquier otro registro de contenedores) para almacenar las imágenes.
- **GitHub** para alojar el repositorio y ejecutar el pipeline.

## 🛠 Estructura del proyecto
/punto-3-ci-cd-nginx
│
├── Dockerfile.nginx
├── index.html
├── docker-compose.yml
├── .github/workflows/ci-cd.yml
├── README.md


- **Dockerfile**: Define la imagen de Nginx.
- **index.html**: Archivo HTML que se sirve mediante Nginx.
- **docker-compose.yml**: Archivo para orquestar el servicio de Nginx.
- **ci-cd.yml**: Archivo de configuración del pipeline de GitHub Actions.

## 🐋 Dockerfile

El archivo `Dockerfile` define cómo se construye la imagen de Nginx. Aquí está su contenido:

```dockerfile
# Usar la imagen oficial de Nginx como base
FROM nginx:alpine

# Copiar el archivo index.html al directorio de Nginx
COPY index.html /usr/share/nginx/html/index.html

# Exponer el puerto 80
EXPOSE 80

# Comando para iniciar Nginx
CMD ["nginx", "-g", "daemon off;"]
