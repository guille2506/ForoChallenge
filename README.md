# 📚 ForoHub - API de Foro Técnico

**ForoHub** es una API REST que simula el funcionamiento de un foro profesional de discusión.  
Permite crear y administrar preguntas, respuestas y usuarios utilizando una arquitectura **stateless**, seguridad con **JWT** y una base de datos relacional.

El proyecto busca aplicar principios del **desarrollo backend moderno**, como autenticación segura, integridad de datos y organización eficiente de la información.

---

# 🚀 Funcionalidades Principales

### 🔐 Autenticación y Seguridad
El sistema utiliza **Spring Security** y **JWT** para proteger el acceso a la API.  
Cada usuario puede iniciar sesión y acceder a los recursos según sus permisos.

### 📝 Gestión de Tópicos
Permite crear, consultar, actualizar y eliminar tópicos (CRUD).  
Cada tópico está relacionado con un **autor y un curso**, lo que permite mantener la información organizada.

### ✅ Respuestas y Soluciones
Cuando una respuesta es marcada como solución:
- La respuesta se registra como **solucionada**.
- El tópico cambia automáticamente su estado a **SOLUCIONADO**.

### 🗑️ Borrado Lógico
Los tópicos no se eliminan físicamente de la base de datos.  
En su lugar, se marcan como **inactivos**, lo que permite conservar el historial y estadísticas del foro.

### 🔎 Búsqueda y Filtros
La API permite filtrar tópicos por:
- **Curso**
- **Año de creación**

---

## 🏗️ Estructura del Proyecto

El proyecto está organizado en capas para facilitar el mantenimiento, la escalabilidad y la separación de responsabilidades.

forohub/
├── src/main/java/com/aluracursos/forohub/
│   ├── controller/            # Endpoints de la API (Tópicos, Respuestas, Login, etc.)
│   ├── domain/                # Entidades JPA, DTOs y lógica de negocio
│   │   ├── topico/            # Modelado y reglas de Tópicos
│   │   ├── respuesta/         # Modelado y reglas de Respuestas
│   │   ├── usuario/           # Gestión de usuarios
│   │   ├── perfil/            # Roles o perfiles de usuario
│   │   └── curso/             # Catálogo de cursos
│   ├── infra/                 # Infraestructura y configuraciones generales
│   │   ├── security/          # Seguridad y filtros JWT
│   │   ├── springdoc/         # Configuración de Swagger (OpenAPI)
│   │   └── errores/           # Manejo global de excepciones
│   └── ForoHubApplication.java # Clase principal de la aplicación
│
└── src/main/resources/
    ├── db/migration/          # Migraciones de base de datos con Flyway
    └── application.properties # Configuración de la aplicación
    
---

# ⚙️ Tecnologías Utilizadas

- **Java 17**
- **Spring Boot**
- **Spring Security**
- **JWT**
- **Spring Data JPA**
- **MySQL**
- **Maven**
- **Flyway**
- **SpringDoc OpenAPI (Swagger)**

---

# 🚀 Cómo ejecutar el proyecto

### 1. Clonar el repositorio
https://github.com/guille2506/ForoChallenge.git

### 2. Configurar variables de entorno
Configura las siguientes variables:

- `DB_USERNAME`
- `DB_PASSWORD`
- `JWT_SECRET`

### 3. Crear la base de datos
Crear una base de datos llamada:
forohub_db

### 4. Ejecutar la aplicación
Inicia la clase principal:
ForoHubApplication.java

Flyway se encargará de crear automáticamente las tablas necesarias.


---

# 📄 Licencia
Este proyecto está bajo la **Licencia MIT**.
