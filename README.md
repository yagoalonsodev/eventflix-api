<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<a name="readme-top"></a>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
<!-- FUTURES
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]-->





<!-- PROJECT LOGO -->
<br />
<div align="center">
  <img src="README/images/logo.png" alt="EventApp Logo" width="120" height="120">
</div>

# 🎫 EventApp - Aplicación de Gestión de Eventos

## 📱 Sobre el Proyecto

EventApp es una aplicación móvil moderna desarrollada en Kotlin con Jetpack Compose que permite a los usuarios gestionar, comprar y organizar eventos de manera intuitiva y eficiente. La aplicación ofrece una experiencia de usuario fluida y moderna, siguiendo las últimas tendencias en diseño de Material Design 3.

### 🎯 Objetivos del Proyecto

- Proporcionar una plataforma intuitiva para la gestión de eventos
- Facilitar la compra y venta de entradas de manera segura
- Ofrecer herramientas avanzadas para organizadores de eventos
- Mejorar la experiencia del usuario en eventos presenciales y virtuales
- Integrar funcionalidades sociales para compartir y descubrir eventos

### 🌟 Características Principales

#### 👤 Para Participantes:
- **Exploración de Eventos:**
  - Búsqueda avanzada con filtros
  - Categorización por tipo, fecha y ubicación
  - Vista de mapa interactivo
  - Recomendaciones personalizadas

- **Gestión de Entradas:**
  - Proceso de compra seguro con múltiples métodos de pago
  - Generación de entradas en PDF con códigos QR
  - Sistema de reembolsos automatizado
  - Transferencia de entradas entre usuarios

- **Funcionalidades Personales:**
  - Perfil personalizado con historial de eventos
  - Sistema de valoraciones y reseñas
  - Lista de deseos y favoritos
  - Notificaciones personalizadas
  - Integración con calendario del dispositivo

- **Características Sociales:**
  - Compartir eventos en redes sociales
  - Crear grupos de asistentes
  - Chat integrado para grupos de eventos
  - Sistema de seguimiento de organizadores

#### 🎭 Para Organizadores:
- **Gestión de Eventos:**
  - Panel de control completo
  - Creación de eventos con plantillas
  - Gestión de múltiples tipos de entradas
  - Configuración de precios dinámicos
  - Sistema de códigos promocionales

- **Herramientas de Marketing:**
  - Análisis de datos y estadísticas
  - Informes de ventas en tiempo real
  - Herramientas de email marketing
  - Gestión de redes sociales

- **Gestión de Asistentes:**
  - Control de acceso mediante QR
  - Gestión de lista de espera
  - Sistema de acreditaciones
  - Comunicación masiva con asistentes

### 🛠️ Tecnologías Utilizadas

#### Frontend
- **UI/UX:**
  - Jetpack Compose (última versión)
  - Material Design 3
  - Animaciones personalizadas
  - Temas dinámicos y modo oscuro

- **Arquitectura:**
  - MVVM (Model-View-ViewModel)
  - Clean Architecture
  - Repository Pattern
  - Use Cases

#### Backend y Servicios
- **API y Networking:**
  - REST API con Laravel
  - GraphQL para consultas complejas
  - WebSockets para tiempo real
  - Cache con Redis

- **Almacenamiento:**
  - Room Database
  - SharedPreferences
  - Firebase Cloud Storage
  - SQLite local

#### Seguridad
- **Autenticación:**
  - JWT (JSON Web Tokens)
  - OAuth 2.0
  - Biometric Authentication
  - Google Sign-In

#### Integraciones
- **APIs Externas:**
  - Google Maps Platform
  - Stripe Payments
  - Firebase Analytics
  - Google Calendar API

### 📚 Bibliotecas Principales

```kotlin
dependencies {
    // Jetpack Compose
    implementation("androidx.compose.ui:ui:1.5.4")
    implementation("androidx.compose.material3:material3:1.1.2")
    implementation("androidx.compose.runtime:runtime:1.5.4")
    implementation("androidx.compose.foundation:foundation:1.5.4")
    
    // Navegación
    implementation("androidx.navigation:navigation-compose:2.7.5")
    implementation("androidx.navigation:navigation-runtime-ktx:2.7.5")
    
    // Lifecycle y ViewModel
    implementation("androidx.lifecycle:lifecycle-viewmodel-compose:2.7.0")
    implementation("androidx.lifecycle:lifecycle-runtime-compose:2.7.0")
    implementation("androidx.lifecycle:lifecycle-livedata-ktx:2.7.0")
    
    // Networking
    implementation("com.squareup.retrofit2:retrofit:2.9.0")
    implementation("com.squareup.retrofit2:converter-gson:2.9.0")
    implementation("com.squareup.okhttp3:logging-interceptor:4.11.0")
    
    // Inyección de Dependencias
    implementation("com.google.dagger:hilt-android:2.48")
    kapt("com.google.dagger:hilt-compiler:2.48")
    
    // Imágenes y Multimedia
    implementation("io.coil-kt:coil-compose:2.5.0")
    implementation("com.github.bumptech.glide:compose:1.0.0-alpha.5")
    
    // Almacenamiento
    implementation("androidx.room:room-runtime:2.6.0")
    implementation("androidx.room:room-ktx:2.6.0")
    kapt("androidx.room:room-compiler:2.6.0")
    
    // Firebase
    implementation(platform("com.google.firebase:firebase-bom:32.3.1"))
    implementation("com.google.firebase:firebase-analytics-ktx")
    implementation("com.google.firebase:firebase-messaging-ktx")
    
    // Testing
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.compose.ui:ui-test-junit4:1.5.4")
}
```

## 🚀 Instalación y Configuración

### Requisitos Previos
- Android Studio Hedgehog | 2023.1.1 o superior
- JDK 17 o superior
- Kotlin 1.9.0 o superior
- Gradle 8.0 o superior

### Pasos de Instalación

1. **Clonar el Repositorio:**
   ```bash
   git clone https://github.com/tuusuario/eventapp.git
   cd eventapp
   ```

2. **Configurar Variables de Entorno:**
   Crea un archivo `local.properties` en la raíz del proyecto:
   ```properties
   sdk.dir=TU_RUTA_SDK_ANDROID
   BASE_URL="TU_URL_API"
   MAPS_API_KEY="TU_CLAVE_API_GOOGLE_MAPS"
   STRIPE_PUBLIC_KEY="TU_CLAVE_PUBLICA_STRIPE"
   FIREBASE_APP_ID="TU_APP_ID_FIREBASE"
   ```

3. **Configurar Firebase:**
   - Descarga el archivo `google-services.json`
   - Colócalo en la carpeta `app/`

4. **Sincronizar y Compilar:**
   ```bash
   ./gradlew clean build
   ```

### Configuración del Entorno de Desarrollo

1. **Android Studio:**
   - Instalar plugins recomendados
   - Configurar el emulador o dispositivo físico
   - Verificar la configuración de Gradle

2. **Configuración de Git:**
   ```bash
   git config user.name "Tu Nombre"
   git config user.email "tu@email.com"
   ```

## 🏗️ Arquitectura

### Estructura del Proyecto
```
app/
├── api/                 # Servicios de red y modelos de API
│   ├── interceptors/    # Interceptores de red
│   ├── models/          # Modelos de datos API
│   └── services/        # Interfaces de servicios
├── di/                  # Módulos de inyección de dependencias
│   ├── modules/         # Módulos Hilt
│   └── qualifiers/      # Calificadores personalizados
├── domain/             # Lógica de negocio
│   ├── models/          # Modelos de dominio
│   ├── repositories/    # Interfaces de repositorio
│   └── usecases/       # Casos de uso
├── data/              # Implementación de datos
│   ├── local/          # Fuentes de datos locales
│   ├── remote/         # Fuentes de datos remotas
│   └── repositories/   # Implementaciones de repositorio
├── ui/
│   ├── components/     # Componentes reutilizables
│   ├── screens/        # Pantallas de la aplicación
│   ├── theme/          # Temas y estilos
│   └── navigation/     # Navegación
├── util/              # Utilidades y extensiones
└── viewmodel/         # ViewModels
```

### Patrones de Diseño Implementados
- **MVVM (Model-View-ViewModel)**
- **Repository Pattern**
- **Factory Pattern**
- **Dependency Injection**
- **Observer Pattern**
- **Builder Pattern**

## 🔐 Seguridad

### Medidas Implementadas
- **Autenticación:**
  - JWT con renovación automática
  - Almacenamiento seguro de tokens
  - Biometric authentication
  
- **Datos Sensibles:**
  - Encriptación AES-256
  - Secure SharedPreferences
  - ProGuard/R8 optimización
  
- **Red:**
  - Certificate Pinning
  - HTTPS obligatorio
  - Validación de certificados

### Buenas Prácticas
- Sanitización de inputs
- Prevención de inyección SQL
- Rate limiting
- Logging seguro

## 🌐 API y Endpoints

### Base URL
```
https://api.eventapp.com/v1/
```

### Endpoints Principales

#### Autenticación
```
POST /auth/login
POST /auth/register
POST /auth/refresh
POST /auth/logout
```

#### Eventos
```
GET /events
POST /events
GET /events/{id}
PUT /events/{id}
DELETE /events/{id}
```

#### Entradas
```
GET /tickets
POST /tickets/purchase
GET /tickets/{id}
POST /tickets/{id}/transfer
```

## 📱 Capturas de Pantalla y Diseño

### Pantallas Principales
[Aquí se incluirían las capturas de pantalla organizadas por sección]

### Guía de Estilos
- **Colores:**
  - Primary: #FF5722
  - Secondary: #2196F3
  - Background: #FFFFFF
  - Surface: #F5F5F5
  
- **Tipografía:**
  - Familia: Roboto
  - Tamaños: 12sp - 24sp
  
- **Espaciado:**
  - Padding: 8dp - 24dp
  - Márgenes: 16dp - 32dp

## 🤝 Contribución

### Proceso de Contribución
1. Fork del repositorio
2. Crear rama feature (`git checkout -b feature/NuevaCaracteristica`)
3. Commit cambios (`git commit -m 'Añadir nueva característica'`)
4. Push a la rama (`git push origin feature/NuevaCaracteristica`)
5. Crear Pull Request

### Guías de Contribución
- Seguir convenciones de código
- Documentar cambios
- Añadir tests unitarios
- Mantener compatibilidad

### Flujo de Trabajo Git
- Main: Producción
- Develop: Desarrollo
- Feature/*: Nuevas características
- Hotfix/*: Correcciones urgentes

## ✅ Testing

### Tipos de Tests
- **Unitarios:** JUnit, Mockito
- **Integración:** Espresso
- **UI:** Compose Testing
- **End-to-End:** Maestro

### Cobertura de Código
- Mínimo 80% en lógica de negocio
- Reportes automáticos en CI/CD

## 📈 Análisis y Monitoreo

### Herramientas
- Firebase Analytics
- Crashlytics
- Performance Monitoring
- Google Analytics

### Métricas Principales
- Tiempo de inicio
- Tasa de errores
- Uso de memoria
- Rendimiento de red

## ✍️ Autores

- **Yago Alonso** - *Frontend Developer* - [GitHub](https://github.com/tuusuario)
  - Especializado en UI/UX y arquitectura
  - Líder técnico del proyecto

- **Arnau Gil** - *Frontend Developer* - [GitHub](https://github.com/tuusuario)
  - Experto en integración de APIs
  - Desarrollo de funcionalidades core

- **Alex Vilanova** - *Frontend Developer* - [GitHub](https://github.com/tuusuario)
  - Especialista en testing y seguridad
  - Optimización de rendimiento

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE.md](LICENSE.md) para detalles

### Términos Principales
- Uso comercial permitido
- Modificación permitida
- Distribución permitida
- Uso privado permitido

## 🙏 Agradecimientos

- **Frameworks y Librerías:**
  - Material Design por la guía de diseño
  - JetBrains por Android Studio
  - Google por Jetpack Compose
  
- **Recursos:**
  - Icons8 por los iconos
  - Unsplash por las imágenes
  - Firebase por la infraestructura

- **Comunidad:**
  - Contribuidores de código abierto
  - Beta testers
  - Usuarios iniciales

## 📞 Soporte y Contacto

### Canales de Soporte
- Email: support@eventapp.com
- Discord: [EventApp Community]
- Twitter: @EventApp

### Reportar Problemas
- Usar GitHub Issues
- Incluir logs y pasos de reproducción
- Adjuntar capturas de pantalla

---
Desarrollado con ❤️ por Yago Alonso, Arnau Gil y Alex Vilanova

[Última actualización: 2024]

[![Contributors][contributors-shield]][contributors-url]
[![MIT License][license-shield]][license-url]

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
        <li><a href="#deployment">Deployment</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#test">Test</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

Describe de repo content in 3-5 lines

Here's a blank template to get started: To avoid retyping too much info. Do a search and replace with your text editor for the following: `github_username`, `repo_name`, `twitter_handle`, `linkedin_username`, `email_client`, `email`, `project_title`, `project_description`

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributors
[![Contributors][contributors-shield]][contributors-url]

Your Name - [@twitter_handle](https://twitter.com/twitter_handle) - email@email_client.com

### Built With

* [![Next][Next.js]][Next-url]
* [![React][React.js]][React-url]
* [![Vue][Vue.js]][Vue-url]
* [![Laravel][Laravel.com]][Laravel-url]
* [![Bootstrap][Bootstrap.com]][Bootstrap-url]

<!-- See: https://github.com/alexandresanlim/Badges4-README.md-Profile?tab=readme-ov-file#-terminal -->

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

### Prerequisites

Requirements for the software and other tools to build, test and push 
- [Example 1](https://www.example.com)
- [Example 2](https://www.example.com)


### Installation

1. Create directory
   ```sh
   mkdir project-dir
   ```
2. Get a free API Key at [https://example.com](https://example.com)
3. Clone the repo
   ```sh
   git clone https://github.com/github_username/repo_name.git
   ```
4. Install NPM packages
   ```sh
   npm install
   ```
5. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```
### Deployment

#### Despliegue del Backend (Laravel 11)

1. **Clona el repositorio backend:**
   ```bash
   git clone https://github.com/LaSalleGracia-Projectes/projecte-aplicaci-web-servidor-g6richardstallman.git
   cd projecte-aplicaci-web-servidor-g6richardstallman
   ```
2. **Instala dependencias:**
   ```bash
   composer install --optimize-autoloader --no-dev
   ```
3. **Configura el entorno:**
   ```bash
   cp .env.example .env
   php artisan key:generate
   php artisan storage:link
   ```
   * Edita `.env` con los datos de tu base de datos, correo, claves JWT, etc.
4. **Prepara la base de datos:**
   ```bash
   php artisan migrate --seed --force
   ```
5. **Optimiza la configuración:**
   ```bash
   php artisan config:cache
   php artisan route:cache
   php artisan view:cache
   ```
6. **Arranca el servidor:**
   ```bash
   php artisan serve
   ```
   O configura Nginx/Apache para producción.

#### Despliegue del Frontend (App Android)

1. **Clona este repositorio:**
   ```bash
   git clone https://github.com/tuusuario/eventapp.git
   cd eventapp
   ```
2. **Configura variables de entorno:**
   Crea o edita `local.properties`:
   ```
   sdk.dir=TU_RUTA_SDK_ANDROID
   BASE_URL="https://TU_BACKEND_URL/api"
   MAPS_API_KEY="TU_CLAVE_API_GOOGLE_MAPS"
   STRIPE_PUBLIC_KEY="TU_CLAVE_PUBLICA_STRIPE"
   FIREBASE_APP_ID="TU_APP_ID_FIREBASE"
   ```
3. **Configura Firebase:**
   Descarga `google-services.json` y colócalo en la carpeta `app/`.
4. **Abre el proyecto en Android Studio.**
5. **Sincroniza y compila:**
   ```bash
   ./gradlew clean build
   ```
6. **Ejecuta la app:**
   * Conecta un dispositivo o inicia un emulador.
   * Haz clic en "Run" en Android Studio.
7. **Despliegue en producción:**
   * Genera el APK o App Bundle (Build > Generate Signed Bundle/APK).
   * Firma la app y distribúyela (Google Play o interno).

#### Integración Frontend-Backend
* La app consume endpoints REST protegidos con JWT/Sanctum.
* Configura correctamente CORS y dominios en el backend.
* Asegúrate de que la URL base de la API esté bien configurada en la app.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

For more examples, please refer to the [Documentation](https://example.com) <!--Link to Memory PDF --> or see de video [Video](https://example.com)<!--Link to Video PDF -->

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Test

### Testing Frontend
* Ejecuta tests instrumentados desde Android Studio.
* Usa emuladores y dispositivos reales para pruebas de UI y rendimiento.

### Testing Backend
Run the artisant tests
   ```php
   php artisan test
   ```
<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ROADMAP -->
## Roadmap

- [X] Feature 1
- [ ] Feature 2
- [X] Feature 3
    - [X] Nested Feature

<!-- See the [open issues](https://github.com/github_username/repo_name/issues) for a full list of proposed features (and known issues). -->

<p align="right">(<a href="#readme-top">back to top</a>)</p>




<!-- LICENSE -->
## License

[![MIT License][license-shield]][license-url]

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. 
* [Choose an Open Source License](https://choosealicense.com)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)
* [Font Awesome](https://fontawesome.com)
* [Laravel](https://laravel.com/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/github_username/repo_name.svg?style=for-the-badge
[contributors-url]: https://github.com/github_username/repo_name/graphs/contributors
[license-shield]: https://img.shields.io/github/license/github_username/repo_name.svg?style=for-the-badge
[license-url]: https://github.com/github_username/repo_name/blob/master/LICENSE.txt
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com

# 🚀 Guía de Despliegue

## Despliegue del Backend (Laravel 11)

1. **Clona el repositorio backend:**
   ```bash
   git clone https://github.com/LaSalleGracia-Projectes/projecte-aplicaci-web-servidor-g6richardstallman.git
   cd projecte-aplicaci-web-servidor-g6richardstallman
   ```
2. **Instala dependencias:**
   ```bash
   composer install --optimize-autoloader --no-dev
   ```
3. **Configura el entorno:**
   ```bash
   cp .env.example .env
   php artisan key:generate
   php artisan storage:link
   ```
   * Edita `.env` con los datos de tu base de datos, correo, claves JWT, etc.
4. **Prepara la base de datos:**
   ```bash
   php artisan migrate --seed --force
   ```
5. **Optimiza la configuración:**
   ```bash
   php artisan config:cache
   php artisan route:cache
   php artisan view:cache
   ```
6. **Arranca el servidor:**
   ```bash
   php artisan serve
   ```
   O configura Nginx/Apache para producción.

---

## Despliegue del Frontend (App Android)

1. **Clona este repositorio:**
   ```bash
   git clone https://github.com/tuusuario/eventapp.git
   cd eventapp
   ```
2. **Configura variables de entorno:**
   Crea o edita `local.properties`:
   ```
   sdk.dir=TU_RUTA_SDK_ANDROID
   BASE_URL="https://TU_BACKEND_URL/api"
   MAPS_API_KEY="TU_CLAVE_API_GOOGLE_MAPS"
   STRIPE_PUBLIC_KEY="TU_CLAVE_PUBLICA_STRIPE"
   FIREBASE_APP_ID="TU_APP_ID_FIREBASE"
   ```
3. **Configura Firebase:**
   Descarga `google-services.json` y colócalo en la carpeta `app/`.
4. **Abre el proyecto en Android Studio.**
5. **Sincroniza y compila:**
   ```bash
   ./gradlew clean build
   ```
6. **Ejecuta la app:**
   * Conecta un dispositivo o inicia un emulador.
   * Haz clic en "Run" en Android Studio.
7. **Despliegue en producción:**
   * Genera el APK o App Bundle (Build > Generate Signed Bundle/APK).
   * Firma la app y distribúyela (Google Play o interno).

---

## 🧩 Integración Frontend-Backend
* La app consume endpoints REST protegidos con JWT/Sanctum.
* Configura correctamente CORS y dominios en el backend.
* Asegúrate de que la URL base de la API esté bien configurada en la app.

---

## 🧪 Testing
* **Frontend:**
  * Ejecuta tests instrumentados desde Android Studio.
  * Usa emuladores y dispositivos reales para pruebas de UI y rendimiento.
* **Backend:**
  * Ejecuta tests con `php artisan test`.

