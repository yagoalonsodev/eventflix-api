<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Gracias por revisar esta plantilla de README. Si tienes sugerencias para mejorarla, haz un fork del repositorio y crea un pull request o abre un issue con la etiqueta "enhancement".
*** ¡No olvides darle una estrella al proyecto!
*** ¡Gracias de nuevo! ¡Ahora ve y crea algo INCREÍBLE! :D
-->

<!-- PROJECT SHIELDS -->
<!--
*** Uso de enlaces de referencia en markdown para mayor legibilidad.
*** Los enlaces de referencia están entre corchetes [ ] en vez de paréntesis ( ).
*** Consulta la declaración de variables de referencia al final de este documento.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <img src="logo.png" alt="EventApp Logo" width="120" height="120">
</div>
# 🎫 Eventflix  - Backend API

## 📋 Descripción General
Este es el backend de una aplicación completa de gestión de eventos y venta de entradas, desarrollada con Laravel 10. Proporciona una API RESTful robusta y segura que permite la gestión integral de eventos, procesamiento de pagos, generación de documentación y gestión de usuarios.

### 🎯 Objetivo del Proyecto
Crear una plataforma completa que permita:
- A los organizadores gestionar sus eventos de manera eficiente
- A los participantes comprar entradas de forma segura
- Automatizar la generación y envío de documentación
- Proporcionar una experiencia de usuario fluida y segura

## 🚀 Características Detalladas

### 👥 Gestión de Usuarios
- Sistema de roles (Organizador, Participante, Administrador)
- Registro y autenticación seguros
- Perfiles personalizables
- Recuperación de contraseña
- Autenticación con Google (OAuth2)

### 📅 Gestión de Eventos
- CRUD completo de eventos
- Gestión de tipos de entradas
- Control de aforo
- Gestión de fechas y horarios
- Ubicación con integración de mapas
- Sistema de categorías y etiquetas
- Búsqueda y filtrado avanzado

### 🎟️ Sistema de Entradas
- Múltiples tipos de entradas por evento
- Control de stock en tiempo real
- Generación de códigos únicos
- Códigos QR para validación
- Sistema anti-reventa
- Cancelaciones y reembolsos


### 📄 Generación de Documentos
- Entradas en PDF personalizadas
- Facturas según normativa
- Códigos QR únicos
- Envío automático por email
- Validación en tiempo real

### 📧 Sistema de Notificaciones
- Emails transaccionales
- Confirmaciones de compra

## 💻 Tecnologías y Herramientas

### 🛠️ Core
- PHP 8.1
- Laravel 10.x
- Supabase
- Redis (caché y colas)
- Nginx/Apache

### 📚 Principales Paquetes
```json
{
    "require": {
        "php": "^8.1",
        "laravel/framework": "^10.0",
        "laravel/sanctum": "^3.2",
        "barryvdh/laravel-dompdf": "^2.0",
        "simplesoftwareio/simple-qrcode": "^4.2",
        "guzzlehttp/guzzle": "^7.5",
        "predis/predis": "^2.0"
    }
}
```

## 🐳 Guía de Despliegue con Docker (Aún no desplegado)

### Requisitos Previos
- Docker Engine 24.0.0 o superior
- Docker Compose 2.20.0 o superior
- Git
- Cuenta en Supabase (para la base de datos)

### Pasos de Despliegue

1. **Clonar el Repositorio:**
   ```bash
   git clone https://github.com/LaSalleGracia-Projectes/projecte-aplicaci-web-servidor-g6richardstallman.git
   cd projecte-aplicaci-web-servidor-g6richardstallman
   ```

2. **Configurar Variables de Entorno:**
   Crea un archivo `.env` en la raíz del proyecto:
   ```env
   # Configuración de la aplicación
   APP_NAME="Sistema de Eventos"
   APP_ENV=production
   APP_DEBUG=false
   APP_URL=https://tu-dominio.com

   # Supabase (Base de datos)
   DB_CONNECTION=pgsql
   DB_HOST=db.example.supabase.co
   DB_PORT=5432
   DB_DATABASE=postgres
   DB_USERNAME=postgres
   DB_PASSWORD=ejemplo_password

   # Redis
   REDIS_HOST=redis
   REDIS_PASSWORD=null
   REDIS_PORT=6379

   # Correo
   MAIL_MAILER=smtp
   MAIL_HOST=smtp.tuservidor.com
   MAIL_PORT=587
   MAIL_USERNAME=tu@email.com
   MAIL_PASSWORD=tu_contraseña
   MAIL_ENCRYPTION=tls
   MAIL_FROM_ADDRESS=noreply@tudominio.com
   MAIL_FROM_NAME="${APP_NAME}"
   ```

3. **Construir y Levantar los Contenedores:**
   ```bash
   docker-compose up -d --build
   ```

4. **Ejecutar Migraciones y Seeders:**
   ```bash
   docker-compose exec app php artisan migrate --seed --force
   ```

5. **Optimizar la Aplicación:**
   ```bash
   docker-compose exec app php artisan config:cache
   docker-compose exec app php artisan route:cache
   docker-compose exec app php artisan view:cache
   ```

### Estructura de Docker

El proyecto utiliza los siguientes servicios en Docker:

```yaml
version: '3.8'

services:
  app:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: eventos-app
    restart: unless-stopped
    working_dir: /var/www/
    volumes:
      - ./:/var/www
    networks:
      - eventos-network

  nginx:
    image: nginx:alpine
    container_name: eventos-nginx
    restart: unless-stopped
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./:/var/www
      - ./docker/nginx/conf.d:/etc/nginx/conf.d/
    networks:
      - eventos-network

  redis:
    image: redis:alpine
    container_name: eventos-redis
    restart: unless-stopped
    networks:
      - eventos-network

networks:
  eventos-network:
    driver: bridge
```

### Dockerfile

```dockerfile
FROM php:8.1-fpm

# Argumentos definidos en docker-compose.yml
ARG user
ARG uid

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

# Limpiar cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Instalar extensiones PHP
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# Obtener Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Crear usuario del sistema
RUN useradd -G www-data,root -u $uid -d /home/$user $user
RUN mkdir -p /home/$user/.composer && \
    chown -R $user:$user /home/$user

# Establecer directorio de trabajo
WORKDIR /var/www

USER $user
```

### Comandos Útiles

```bash
# Ver logs de los contenedores
docker-compose logs -f

# Reiniciar un servicio específico
docker-compose restart app

# Detener todos los contenedores
docker-compose down

# Eliminar volúmenes (¡cuidado, esto borrará los datos!)
docker-compose down -v
```
## 🏗️ Arquitectura del Sistema

### 📂 Estructura de Directorios
```
app/
├── Http/
│   ├── Controllers/
│   │   ├── Api/
│   │   └── Auth/
│   ├── Middleware/
│   └── Requests/
├── Models/
├── Services/
├── Repositories/
├── Mail/
├── Events/
├── Listeners/
└── Jobs/
```

### 🔄 Flujo de Datos
1. Request HTTP → Middleware
2. Middleware → Controller
3. Controller → Service
4. Service → Repository
5. Repository → Model
6. Response → Cliente

## 📦 Instalación y Configuración

### 📋 Requisitos Previos Detallados
- PHP >= 8.1
  - Extensiones: BCMath, Ctype, JSON, Mbstring, OpenSSL, PDO, Tokenizer, XML
- Composer 2.x
- Cuenta Supabase
- Servidor web (Nginx/Apache)

### 🔧 Proceso de Instalación

1. Clonar el repositorio:
```bash
git clone https://github.com/tuorganizacion/eventos-backend.git
cd eventos-backend
```

2. Instalar dependencias:
```bash
composer install --optimize-autoloader --no-dev
```

3. Configuración del entorno:
```bash
cp .env.example .env
php artisan key:generate
php artisan storage:link
```

4. Configuración detallada del .env:
```env
# Configuración de la aplicación
APP_NAME="Sistema de Eventos"
APP_ENV=production
APP_DEBUG=false
APP_URL=https://tu-dominio.com

# Base de datos
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=eventos_db
DB_USERNAME=usuario
DB_PASSWORD=contraseña

# Redis
REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

# Correo
MAIL_MAILER=smtp
MAIL_HOST=smtp.tuservidor.com
MAIL_PORT=587
MAIL_USERNAME=tu@email.com
MAIL_PASSWORD=tu_contraseña
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=noreply@tudominio.com
MAIL_FROM_NAME="${APP_NAME}"

# JWT y Seguridad
JWT_SECRET=tu_jwt_secret
JWT_TTL=60
SANCTUM_STATEFUL_DOMAINS=tu-dominio.com
```

5. Preparar la base de datos:
```bash
php artisan migrate --seed --force
```

6. Optimizar:
```bash
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

## 📚 API Documentation

### 🔐 Autenticación
Todas las rutas (excepto login/registro) requieren token Bearer:
```http
Authorization: Bearer <tu_token>
```

### 📝 Ejemplos de Endpoints

#### Autenticación
```http
POST /api/auth/login
Content-Type: application/json

{
    "email": "usuario@email.com",
    "password": "contraseña"
}
```

#### Crear Evento
```http
POST /api/eventos
Content-Type: application/json
Authorization: Bearer <token>

{
    "nombre": "Mi Evento",
    "descripcion": "Descripción del evento",
    "fecha": "2024-12-31",
    "hora": "20:00",
    "ubicacion": "Dirección del evento",
    "aforo_maximo": 100
}
```


## 👥 Equipo de Desarrollo

### 🧑‍💻 Desarrolladores Principales
- **Yago Alonso**
  - Rol: Lead Backend Developer
  - Responsabilidades: Arquitectura, API, Seguridad
  - GitHub: [YagoAlonso](https://github.com/yagoalonso1)

- **Arnau Gil**
  - Rol: Backend Developer
  - Responsabilidades: Testing, Integración, Base de datos
  - GitHub: [ArnauGil](https://github.com/XxArnauGxX)

- **Alex Vilanova**
  - Rol: Backend Developer
  - Responsabilidades: Documentación, Seguridad, API
  - GitHub: [AlexVilanova](https://github.com/alexvilanova05)



## 📄 Licencia y Términos

Este proyecto está bajo la Licencia MIT. Ver el archivo [LICENSE.md](LICENSE.txt) para más detalles.

---
Desarrollado con ❤️ por el equipo de EventosApp
