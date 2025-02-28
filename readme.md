# TaskManager - Proyecto Full Stack de Gestión de Tareas

Este es un proyecto full stack para la gestión de tareas, permitiendo realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar). Se ha implementado Keycloak para la gestión de usuarios junto con Spring Boot.

## Tecnologías Utilizadas

- **Backend**: Java con Spring Boot y MySQL
- **Frontend**: Vite.js + ReactJS
- **Estilos**: Tailwind CSS
- **Internacionalización**: i18n
- **Configuración centralizada**: Spring Cloud
- **Mensajería**: RabbitMQ
- **Autenticación y autorización**: Keycloak
- **Pruebas automatizadas**: Selenium con JUnit
- **Contenedorización**: Aplicación completamente dockerizada

## Repositorios

- **Archivos de configuración**: [ConfigServerFiles](https://github.com/BrahianPuschiasis/ConfigServerFiles)
- **Backend**: [TaskManager](https://github.com/BrahianPuschiasis/TaskManager)
- **Frontend**: [TaskManagerFront](https://github.com/BrahianPuschiasis/TaskManagerFront)
- **Config Server**: [ConfigServerTaskManager](https://github.com/BrahianPuschiasis/ConfigServerTaskManager)

## Instrucciones de Uso

### Levantar los Servicios con Docker

Cada repositorio tiene su respectivo `Dockerfile` para generar su imagen.
Para levantar cada servicio individualmente, usa:

```sh
# Levantar el backend desde el directorio raíz del proyecto
docker build -t task-service -f Dockerfile .
```

```sh
# Levantar el frontend desde el directorio raíz del proyecto
docker build -t task-front -f Dockerfile .
```

```sh
# Levantar la base de datos
docker-compose -f mySQL.yml up -d
```

```sh
# Levantar RabbitMQ
docker-compose -f rabbit.yml up -d
```

### Levantar todo con `docker-compose`

Se encuentra un `docker-compose.yml` en este mismo repositorio, que levanta todos los servicios simultáneamente con sus configuraciones respectivas.
Para ejecutarlo, usa:

```sh
docker-compose up -d
```

## Configuración de Keycloak

Una vez que Keycloak esté levantado, sigue estos pasos:

1. Accede a [http://localhost:8080](http://localhost:8080)
2. Inicia sesión con las credenciales de administrador. (admin;admin)
3. Crea un nuevo **Reino** (Realm).
4. Importa el archivo `realm-export.json` que se encuentra en este repositorio.

## Variables de Entorno

### Backend

```sh
PORT=
DB_HOST=
DB_PORT=
DB_USERNAME=
DB_PASSWORD=
RABBITMQ_USERNAME=
RABBITMQ_PASSWORD=
RABBITMQ_HOST=
RABBITMQ_PORT=
CONFIG_SERVER_URL=

# Keycloak Configuration
KEYCLOAK_REALM=
KEYCLOAK_AUTH_SERVER_URL=
KEYCLOAK_CLIENT_ID=
KEYCLOAK_CLIENT_SECRET=
KEYCLOAK_REDIRECT_URI=
KEYCLOAK_ISSUER_URI=
```

### Frontend

```sh
VITE_KEYCLOAK_HOST=
VITE_BACKEND_HOST=
VITE_CLIENT_ID=
VITE_CLIENT_SECRET=
VITE_SCOPE=
VITE_GRANT_TYPE=
VITE_ADMIN_USER=
VITE_ADMIN_PASS=
```

---

