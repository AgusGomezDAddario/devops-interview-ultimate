 Despliegue de aplicación Django + React.js con Docker  

Este proyecto proporciona el despliegue dockerizado de una aplicación web que incluye:  

- **Backend**: Django (API RESTful).  
- **Frontend**: React.js (interfaz de usuario).  
- **Base de datos**: PostgreSQL.  
- **Orquestación**: Docker y Docker Compose.  

El despliegue puede realizarse tanto en un entorno local como en la nube (AWS).  

## 📌 Requisitos previos  

Antes de iniciar el despliegue, tenés que contar con los siguientes elementos:  

- **Docker** instalado.  
- **Docker Compose** instalado.  
- **Git** instalado.  
- **Claves SSH** (solo para despliegue en AWS).  

## 🖥️ Despliegue local  

### 1️⃣ Clonar el repositorio  

```sh
git clone https://github.com/AgusGomezDAddario/devops-interview-ultimate.git
cd devops-interview-ultimate/punto-2-despliegue-django-react
```

### 2️⃣ Levantar los contenedores  

```sh
docker-compose up --build
```

### 3️⃣ Acceder a la aplicación  

- **Frontend**: [http://localhost:3000/](http://localhost:3000/)  
- **Backend**: [http://localhost:8000/](http://localhost:8000/)  

### 4️⃣ Detener los contenedores (cuando ya no quieras usar la aplicación) 

Para detener los contenedores presioná `Ctrl + C` en la terminal o ejecuta:  

```sh
docker-compose down
```

---

## ☁️ Despliegue en AWS  

### 1️⃣ Crear y configurar una instancia EC2  

1. Acceder a la consola de AWS y crear una nueva instancia EC2 (se recomienda el uso de Ubuntu).  
2. Configurar el grupo de seguridad permitiendo el tráfico en los siguientes puertos:  
   - **22 (SSH)**: Para la conexión remota.  
   - **3000 (HTTP)**: Para el frontend.  
   - **8000 (HTTP)**: Para el backend.  
3. Descargar la clave privada (`.pem`) para la conexión SSH.  

#### Notas sobre la IP pública y la clave SSH:
- **IP pública**: Podes encontrar la IP pública de tu instancia EC2 en la consola de AWS, en la sección de "Instancias".
- **Clave SSH**: Al crear la instancia EC2, AWS te proporcionará un archivo `.pem`. Asegúrate de tenerlo en tu máquina local y de que los permisos sean correctos (por ejemplo, `chmod 400 /ruta/a/tu-clave.pem`).

### 2️⃣ Conectarse a la instancia vía SSH  

```sh
ssh -i /ruta/a/tu-clave.pem ubuntu@<IP-PÚBLICA>
```

### 3️⃣ Instalar Docker y Docker Compose  

```sh
sudo apt update && sudo apt install -y docker.io docker-compose
```

Agregar al usuario al grupo de Docker:

```sh
sudo usermod -aG docker $USER
```

Luego, reconectarse:  

```sh
exit
ssh -i /ruta/a/tu-clave.pem ubuntu@<IP-PÚBLICA>
```

### 4️⃣ Clonar el repositorio  

```sh
git clone https://github.com/AgusGomezDAddario/devops-interview-ultimate.git
```

Navegar a la siguiente ubicación del repositorio:

```sh
cd devops-interview-ultimate/punto-2-despliegue-django-react
```

### 5️⃣ Levantar los contenedores  

```sh
docker-compose up --build -d
```

### 6️⃣ Acceder a la aplicación  

- **Frontend**: [http://<IP-PÚBLICA>:3000/](http://<IP-PÚBLICA>:3000/)  
- **Backend**: [http://<IP-PÚBLICA>:8000/](http://<IP-PÚBLICA>:8000/)  

### 7️⃣ Detener los contenedores (cuando ya no quieras usar la aplicación)

```sh
docker-compose down
```

---

## 📜 Notas adicionales  

- Para ejecutar los contenedores en segundo plano, usar la opción `-d`:  

  ```sh
  docker-compose up --build -d
  ```
