# 🕒 Módulo de Fichaje de Asistencia - Odoo 17

Este módulo ha sido desarrollado para gestionar de manera eficiente el registro de jornadas laborales (entradas, descansos y salidas) dentro del ecosistema **Odoo 17**, utilizando una arquitectura profesional basada en contenedores.

## 👤 Autor
* **Alejandro Martinez Bou** 🎓

## 📋 Descripción del Proyecto
La aplicación permite a los empleados registrar su asistencia de forma sencilla. El sistema garantiza la integridad de los datos, permitiendo seleccionar el empleado, la fecha/hora y el tipo de acción, con persistencia total en una base de datos relacional.

## 🛠️ Tecnologías y Arquitectura
* **ERP**: Odoo 17 (Community Edition) 🖥️
* **Lenguajes**: Python (Lógica de negocio) y XML (Vistas e Interfaz) 🐍
* **Base de Datos**: PostgreSQL 15 🐘
* **Infraestructura**: Despliegue mediante **Docker** y **Docker Compose** 🐋
* **Gestión de DB**: pgAdmin 4 para auditoría de tablas 📊

---

## 🚀 Proceso de Instalación y Despliegue

### 1. Despliegue de la Infraestructura
Se ha utilizado un archivo `docker-compose.yml` para levantar tres servicios interconectados: el servidor de Odoo, la base de datos PostgreSQL y la herramienta de gestión pgAdmin.

> **Captura 1: Estado de los Contenedores**
> *(Añadir captura de la interfaz donde se ven odoo, db y pgadmin en verde)*
> ![Panel de Control](./capturas/01_contenedores_ok.png)

### 2. Carga del Módulo Personalizado
Para integrar el módulo `fichaje` en el servidor, se siguieron los siguientes comandos:
```bash
# Copia de archivos al volumen del contenedor
docker cp . odoo:/mnt/extra-addons/fichaje

# Reinicio del servicio para detectar cambios
docker restart odoo
