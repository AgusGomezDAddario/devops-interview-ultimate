# 🚀 Prueba Técnica - DevOps

Este repositorio contiene la resolución de la prueba técnica para el puesto de DevOps en Craftech. La prueba consta de tres puntos principales:

1. **Diagrama de Red**: Diseño de una arquitectura en AWS para una aplicación web.
2. **Despliegue de una aplicación Django + React.js**: Implementación de un despliegue dockerizado.
3. **CI/CD para Nginx**: Automatización del despliegue de un servidor Nginx.

## 📌 Estructura del repositorio
/repositorio
├── .github/workflows/ci-cd.yml
|
├── /punto-1-diagrama-red
│ ├── diagrama-red.png (o .pdf)
│ ├── descripcion-arquitectura.md
│
├── /punto-2-despliegue-django-react
│ ├── /backend
│ │ ├── Dockerfile
│ │ ├── requirements.txt
│ │ ├── manage.py
│ │ └── ... (resto del código Django)
│ ├── /frontend
│ │ ├── Dockerfile
│ │ ├── package.json
│ │ └── ... (resto del código React)
│ ├── docker-compose.yml
│ ├── README.md
│
├── /punto-3-ci-cd-nginx
│ ├── /nginx
│ │ ├── Dockerfile
│ │ ├── index.html
│ ├── docker-compose.yml
│ ├── README.md
│
└── README.md (este archivo)


## 🛠 Cómo ejecutar cada punto

### 1. Diagrama de Red

- **Archivos**:
  - `diagrama-red.png`: Diagrama de la arquitectura propuesta.
  - `descripcion-arquitectura.md`: Explicación detallada de las decisiones técnicas.
- **Instrucciones**: Revisá los archivos en la carpeta `/punto-1-diagrama-red`.

### 2. Despliegue de Django + React.js

- **Archivos**:
  - `Dockerfile` para backend y frontend.
  - `docker-compose.yml` para orquestar los contenedores.
  - `README.md` con instrucciones detalladas.
- **Instrucciones**: Seguí las instrucciones en `/punto-2-despliegue-django-react/README.md`.

### 3. CI/CD para Nginx

- **Archivos**:
  - `Dockerfile` para Nginx.
  - `index.html` que se sirve mediante Nginx.
  - `docker-compose.yml` para gestionar el servicio de Nginx.
  - `.github/workflows/ci-cd.yml` para el pipeline de CI/CD.
  - `README.md` con instrucciones detalladas.
- **Instrucciones**: Seguí las instrucciones en `/punto-3-ci-cd-nginx/README.md`.

## 🛠 Herramientas utilizadas

- **Docker**: Para contenerizar las aplicaciones.
- **Docker Compose**: Para orquestar los contenedores.
- **GitHub Actions**: Para implementar el pipeline de CI/CD.
- **AWS**: Para el diseño de la arquitectura en el punto 1.
- **Nginx**: Como servidor web en el punto 3.
- **Django y React.js**: Para la aplicación full-stack en el punto 2.

## 📜 Notas adicionales

- **Documentación**: Cada punto tiene su propio README con instrucciones detalladas.

---

