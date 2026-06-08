# MobiExpress-Node API

Esta es la API (Backend) para la aplicación **MobiExpress**, desarrollada con Node.js y Express. Provee los servicios, rutas y manejo de base de datos necesarios para que la aplicación funcione, manejando desde la autenticación de usuarios hasta la gestión de productos, órdenes, tarjetas y facturación.

## 🚀 Tecnologías y Herramientas

El proyecto está construido bajo el estándar ES Modules (`"type": "module"`) y utiliza las siguientes librerías principales:

- **Node.js** y **Express**: Framework principal para el servidor.
- **MongoDB** y **Mongoose**: Base de datos NoSQL y su ODM para el modelado de datos.
- **Argon2**: Para el hasheo seguro de contraseñas.
- **JSON Web Token (JWT)**: Para la autenticación y autorización mediante tokens.
- **Multer**: Para el manejo y subida de archivos (imágenes/archivos servidos estáticamente en la ruta `/uploads`).
- **Morgan** & **Helmet** & **Cors**: Middlewares de seguridad, registro de peticiones HTTP y control de acceso.
- **express-rate-limit**: Protección contra ataques de fuerza bruta (limite de peticiones).

## 📂 Estructura del Proyecto

```text
├── configs/          # Configuraciones de la base de datos (MongoDB) y el servidor (Express)
├── middlewares/      # Middlewares personalizados (ej. Rate Limiter, Validadores, JWT)
├── src/              # Controladores, modelos y rutas organizados por dominios
│   ├── auth/         # Autenticación de usuarios (Registro, Login)
│   ├── bills/        # Gestión de facturas
│   ├── Cards/        # Gestión de tarjetas de pago
│   ├── category/     # Gestión de categorías de productos
│   ├── order/        # Gestión de pedidos/órdenes
│   ├── products/     # Gestión de productos
│   └── user/         # Gestión de usuarios
├── uploads/          # Carpeta donde se guardan los archivos subidos (ej. imágenes)
├── index.js          # Punto de entrada de la aplicación
└── package.json      # Dependencias y scripts del proyecto
```

## 🛠️ Instalación y Configuración

1. **Clonar el repositorio** y acceder a la carpeta:
   ```bash
   cd MobiExpress-Node
   ```

2. **Instalar las dependencias**:
   ```bash
   npm install
   ```

3. **Configurar las variables de entorno**:
   Crea un archivo `.env` en la raíz del proyecto basándote en un archivo de ejemplo (si existe) o agrega las variables necesarias como:
   ```env
   PORT=3000
   MONGO_URI=tu_cadena_de_conexion_de_mongodb
   JWT_SECRET=tu_secreto_para_jwt
   ```
   *(Asegúrate de configurar los valores de acuerdo a tu entorno local de base de datos).*

## 🏃 Ejecución

Para iniciar el servidor en entorno de desarrollo (con recarga automática activada nativamente en node):

```bash
npm run dev
```

El servidor estará escuchando en el puerto definido en tus variables de entorno (por defecto podría ser el 3000 u otro, dependiendo de tu configuración).

## 📡 Rutas Principales (API v1)

La API expone sus servicios a través del prefijo `/v1/`.

- **Autenticación**: `/v1` (Rutas de login, registro, etc. contenidas en `authRoutes`)
- **Usuarios**: `/v1/user`
- **Categorías**: `/v1/category`
- **Productos**: `/v1/products`
- **Tarjetas**: `/v1/cards`
- **Facturas**: `/v1/bill`
- **Órdenes**: `/v1/order`
- **Archivos Estáticos**: `/uploads` (Acceso a las imágenes subidas)

