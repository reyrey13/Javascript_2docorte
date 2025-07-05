# Javascript_2docorte
Examen del 2do corte de la materia JavaScript
 
# API REST de Gestión de Inventario

Este proyecto es una API construida con **Node.js** y **Express**, que incluye autenticación con **JWT y Refresh Tokens**, control de acceso por **roles de usuario** y un CRUD completo para administrar una entidad (por ejemplo, productos). La API se conecta a una base de datos **MySQL** mediante **Sequelize** y tiene una estructura organizada en carpetas.

## Funcionalidades

- Registro e inicio de sesión de usuarios.
- Autenticación con tokens JWT de acceso y de refresco.
- Autorización por rol (`admin` y `user`) para proteger rutas.
- CRUD completo sobre la entidad `productos`.
- Middleware para verificar tokens y roles.
- Base de datos relacional con Sequelize ORM.

## Tecnologías

- **Node.js / Express**
- **MySQL / Sequelize**
- **JWT** (`jsonwebtoken`)
- **Bcrypt** (`bcryptjs`)
- **Dotenv**
- **UUID**

## Estructura del Proyecto

project-root/
├── src/
│ ├── config/ # Conexión DB
│ ├── controllers/ # Lógica de negocio
│ ├── middlewares/ # Verificación de tokens y roles
│ ├── models/ # Definición de tablas
│ └── routes/ # Endpoints organizados
├── public/ # Frontend simple (HTML/CSS/JS)
├── .env.example # Variables de entorno
├── package.json
└── README.md

markdown
Copiar
Editar

## Instalación

1. Clona el repositorio o descomprime el ZIP.
2. Instala dependencias:
npm install

markdown
Copiar
Editar
3. Configura tu archivo `.env` con tus datos de MySQL y claves JWT.
4. Inicia la app:
npm run dev

yaml
Copiar
Editar

## Rutas Principales

| Método | Ruta                    | Protegido | Rol     | Función                      |
|--------|-------------------------|-----------|---------|------------------------------|
| POST   | /api/auth/register      | No        | —       | Crear cuenta de usuario      |
| POST   | /api/auth/login         | No        | —       | Iniciar sesión               |
| POST   | /api/auth/refresh       | No        | —       | Obtener nuevo access token   |
| GET    | /api/products           | Sí        | user    | Ver productos                |
| POST   | /api/products           | Sí        | admin   | Agregar producto             |
| PUT    | /api/products/:id       | Sí        | admin   | Editar producto              |
| DELETE | /api/products/:id       | Sí        | admin   | Eliminar producto            |

## Frontend

El proyecto incluye páginas básicas en HTML para probar el flujo de registro, login y navegación tras autenticarse.
