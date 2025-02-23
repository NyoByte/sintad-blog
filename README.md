# Sintad Blog - Fullstack App

Este proyecto usa **Docker Compose** para levantar el frontend (Angular), backend (Spring Boot) y la base de datos (PostgreSQL) en contenedores separados.

## 📁 Estructura del Proyecto

```
sintad-blog/
├── sintad-blog-frontend/   # Proyecto Angular 19
├── sintad-blog-backend/    # Proyecto Java 21 con Spring Boot 3
├── compose.yaml            # Orquestador Docker Compose
└── README.md               # Guía de uso
```

## 🚀 Clonar el proyecto

Clona el repositorio principal junto con sus submódulos:

```bash
git clone --recurse-submodules git@github.com:NyoByte/sintad-blog.git
```

Si ya clonaste el repositorio y olvidaste los submódulos, ejecuta:

```bash
git submodule update --init --recursive
```

## 🐳 Levantar el Proyecto

En la raíz del proyecto (**sintad-blog/**), ejecuta:

```bash
docker-compose -f compose.yaml up --build
```

Esto levantará:
- **Frontend Angular** en: [http://localhost:4300](http://localhost:4300)
- **Backend Spring Boot** en: [http://localhost:8080](http://localhost:8080)
- **PostgreSQL** en el puerto **5432**

## ⚡ Comandos útiles

- **Parar contenedores:**

  ```bash
  docker compose down
  ```

- **Ver logs de un contenedor específico:**

  ```bash
  docker compose logs -f
  ```

- **Reconstruir sin usar caché:**

  ```bash
  docker compose up --build --no-cache
  ```

## 🐘 Base de Datos (PostgreSQL)

- **Host:** `sintad-db`
- **Puerto:** `5432`
- **Usuario:** `sintad`
- **Contraseña:** `sintad`
- **Base de datos:** `dbSintadBlog`

Accede a PostgreSQL desde tu máquina con:

```bash
psql -h localhost -U sintad -d dbSintadBlog
```

## 🛠️ Requisitos
- Docker & Docker Compose
- Node.js v22.13.1 y npm v10.9.2 (para desarrollo en frontend)
- Java 21 y Maven 3.9.6 (para desarrollo en backend)

📌 Nota: Para asegurar el correcto funcionamiento de las rutas en Angular con Nginx, el servidor está configurado para redirigir todas las rutas al index.html.
