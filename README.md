# 🧪 Laboratorio #2 – Implementación del Login en Laravel

![Laravel](https://img.shields.io/badge/Laravel-13.x-red)
![PHP](https://img.shields.io/badge/PHP-8.3-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.4-orange)
![Node](https://img.shields.io/badge/Node.js-20.x-green)
![License](https://img.shields.io/badge/Status-Academic-informational)

---

## 📑 Tabla de Contenido

1. [Prerrequisitos](#1-️-prerrequisitos-ecosistema-de-desarrollo)  
2. [Flujo de Comandos](#2-️-flujo-de-comandos-utilizados)  
3. [Arquitectura MVC](#3--introducción-y-arquitectura-mvc)  
4. [Resultado Visible](#4--resultado-visible)  
5. [Base de Datos](#5-️-base-de-datos)  
6. [Dificultades y Soluciones](#6-️-dificultades-y-soluciones)  
7. [Capturas del Sistema](#7--capturas-del-sistema)  
8. [Referencias](#8--referencias)  
9. [Información del Estudiante](#-información-del-estudiante)  

---

## 1. 🛠️ Prerrequisitos (Ecosistema de desarrollo)

Para la ejecución de este laboratorio, se configuró el siguiente entorno:

- **Sistema Operativo:** Windows 11 🪟 (Terminal en modo Administrador)
- **Lenguaje:** PHP 8.3.28 🐘
- **Gestor de Dependencias:** Composer 2.7.2 📦
- **Framework:** Laravel 13.3.0 🏗️
- **Entorno de Desarrollo:** WampServer 3.3.0 🛠️
- **Servidor Web:** Apache 2.4.54
- **Base de Datos:** MySQL 8.4.7
- **Editor de Código:** Visual Studio Code 💻
- **Gestor de Paquetes:** Node.js v20.x / NPM ⚡ (para Vite)

---

## 2. ⚙️ Flujo de Comandos Utilizados

```bash
# 1. Crear el proyecto en el directorio de WAMP
cd C:\wamp64\www
laravel new proyecto

# 2. Instalar Laravel UI
composer require laravel/ui

# 3. Generar autenticación con Bootstrap
php artisan ui bootstrap --auth

# 4. Instalar dependencias y compilar assets
npm install
npm run build
```

---

## 3. 🧱 Introducción y Arquitectura MVC

El objetivo de este laboratorio es implementar un sistema de autenticación funcional utilizando la arquitectura **MVC (Modelo-Vista-Controlador)** de Laravel.

### 3.1 Componentes del MVC

- **Modelos (app/Models):**  
  Gestionan la estructura de datos y lógica de negocio  
  Ejemplo: `User`

- **Vistas (resources/views):**  
  Contienen el código HTML/Blade visible al usuario  

- **Controladores (app/Http/Controllers):**  
  Procesan las peticiones y conectan modelos con vistas  

- **Rutas (routes/web.php):**  
  Definen las URLs de la aplicación  

### 3.2 Objetivo

Lograr una integración correcta entre Laravel y la base de datos para gestionar autenticación segura de usuarios.

---

## 4. 👀 Resultado Visible

El sistema permite:

- Registro de usuarios  
- Inicio de sesión  
- Gestión de sesiones  

---

## 5. 🗄️ Base de Datos

### 5.1 Configuración `.env`

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=proyecto
DB_USERNAME=root
DB_PASSWORD=
```

### 5.2 Migraciones

```bash
php artisan migrate
```

📌 Genera:

- users  
- sessions  
- password_resets  

📌 Backup incluido en:

```
/database/backup
```

---

## 6. ⚠️ Dificultades y Soluciones

### 🔹 Node.js (NPX no reconocido)
**Solución:** Instalar Node.js LTS

---

### 🔹 Error MySQL 1071
```php
Schema::defaultStringLength(191);
```

---

### 🔹 Permisos de escritura
**Solución:** Ejecutar terminal como Administrador

---

### 🔹 Ejecución del servidor
```bash
composer run dev
```

---

## 7. 📸 Capturas del Sistema

### 🔐 Pantalla de Login
![Login](docs/images/login.png)

### 📝 Registro de Usuario
![Registro](docs/images/register.png)

### 🏠 Dashboard
![Dashboard](docs/images/dashboard.png)

📌 **Nota:**  
Colocar las imágenes en la carpeta:

```
/docs/images/
```

---

## 8. 📚 Referencias

- https://laravel.com/docs/11.x/authentication  
- https://forum.wampserver.com/  
- https://github.com/laravel/ui  

---

## 📌 Información del Estudiante

> [!IMPORTANT]
> **Desarrollado por:**

- **Nombre:** Ahmed Diaz  
- **Correo:** ahmed.diaz@utp.ac.pa  
- **Curso:** Desarrollo de Software VI  
- **Instructor:** Ing. Irina Fong  

---
