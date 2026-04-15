Laboratorio #2 – Implementación del Login en Laravel
1. Prerrequisitos (Ecosistema de desarrollo)
Para la ejecución de este laboratorio, se configuró el siguiente entorno:

Sistema Operativo: Windows 11 🪟 (Ejecutado con Terminal en modo Administrador).

Lenguaje: PHP versión 8.3.28 🐘

Gestor de Dependencias: Composer versión 2.7.2 📦

Framework: Laravel 13.3.0 🏗️

Entorno de Desarrollo: WampServer 3.3.0 🛠️

Servidor Web: Apache 2.4.54

Base de Datos: MySQL 8.4.7

Editor de Código: Visual Studio Code 💻

Gestor de Paquetes: NPM / Node.js v20.x ⚡ (Necesario para la compilación de Vite).

Flujo de Comandos Utilizados
Para la instalación y configuración del ecosistema de autenticación, se siguió esta secuencia:

Bash
# 1. Crear el proyecto en el directorio de WAMP
cd C:\wamp64\www
laravel new proyecto

# 2. Instalar el paquete de interfaz de usuario de Laravel (UI)
composer require laravel/ui

# 3. Generar el andamiaje de autenticación con Bootstrap
php artisan ui bootstrap --auth

# 4. Instalación de dependencias de Node y compilación de assets
npm install
npm run build

2. Introducción y Arquitectura MVC
El objetivo de este laboratorio es implementar un sistema de autenticación funcional aprovechando la arquitectura Modelo-Vista-Controlador (MVC) de Laravel, la cual separa la lógica de negocio de la interfaz de usuario.

Modelos (app/Models): Gestionan la estructura de los datos y las reglas de negocio (ej. el modelo User).

Vistas (resources/views): Contienen el código HTML/Blade que el usuario visualiza (formularios de login y registro).

Controladores (app/Http/Controllers): Actúan como intermediarios, procesando las peticiones de las rutas y enviando datos a las vistas.

Rutas (routes/web.php): Definen las URLs de la aplicación y qué controlador debe responder a cada una.

Objetivo del laboratorio: Lograr una integración exitosa entre el framework y el servidor de base de datos para gestionar el acceso de usuarios de forma segura.

3. Resultado Visible
A continuación, se muestra el resultado final del sistema de autenticación funcionando correctamente:



4. Base de Datos
El entorno de base de datos se gestionó a través de WampServer utilizando MySQL.

Configuración del archivo .env
Se vincularon las credenciales por defecto de WAMP para permitir la comunicación:

Code snippet
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=proyecto
DB_USERNAME=root
DB_PASSWORD=
Migraciones y Tablas
Para levantar la estructura de datos necesaria para el sistema de login (tablas de usuarios, sesiones y reseteo de contraseñas), se utilizó el comando:

Bash
php artisan migrate
Nota: Se generó un respaldo (backup) de la base de datos proyecto.sql ubicado en la carpeta /database/backup de este repositorio.

5. Dificultades y Soluciones
Conflicto de Node.js (NPM/NPX): Al inicio, el comando npx no era reconocido.

Solución: Se descargó e instaló Node.js LTS, permitiendo la ejecución de Vite y los scripts de frontend.

Límite de caracteres en MySQL (Error 1071): La versión de MySQl de WAMP arrojó un error de longitud de llave en los índices.

Solución: Se editó el archivo AppServiceProvider.php agregando Schema::defaultStringLength(191);.

Permisos de Escritura: Errores al crear el scaffolding de Bootstrap.

Solución: Se reinició la terminal con Privilegios de Administrador para permitir que Laravel creara los archivos en la carpeta www.

Ejecución de Servidor:

Solución: Se utilizó el comando consolidado composer run dev para levantar el servidor y Vite simultáneamente de forma estable.

6. Referencias
Documentación Oficial de Laravel: https://laravel.com/docs/11.x/authentication

Guía de Instalación de WampServer: https://forum.wampserver.com/

Repositorio de Laravel UI (GitHub): https://github.com/laravel/ui

---
> [!IMPORTANT]
> **Este laboratorio ha sido desarrollado por el estudiante de la Universidad 
Tecnológica de Panamá: **
> 
> **Nombre:** Ahmed Diaz  
> **Correo:** ahmed.diaz@utp.ac.pa 
> **Curso:** Desarrollo de Software VI  
> **Instructor de Laboratorio:** Ing. Irina Fong

