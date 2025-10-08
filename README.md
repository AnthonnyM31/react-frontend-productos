# ⚛️ Frontend React: Consumo de API y Proxy de Desarrollo

<p align="center">
  <img src="[https://img.shields.io/badge/React-2024-61DAFB?logo=react&logoColor=white](https://img.shields.io/badge/React-2024-61DAFB?logo=react&logoColor=white)" alt="React"/>
  <img src="[https://img.shields.io/badge/NPM-Proxy-red](https://img.shields.io/badge/NPM-Proxy-red)" alt="NPM Proxy"/>
</p>

## 🎯 Objetivo

Este repositorio contiene la capa de presentación mínima construida con React, diseñada para comunicarse con la API REST del backend (`api-cache-proxy-arquitectura`) y visualizar el funcionamiento del sistema de productos.

---

## 🔗 Estrategia de Comunicación

Para facilitar el desarrollo y evitar conflictos de CORS (Cross-Origin Resource Sharing) entre el frontend (`:3000`) y el backend (`:8080`):

* **Proxy de Desarrollo (`package.json`):**
    El archivo `package.json` está configurado con `"proxy": "http://localhost:8080"`. Esto permite que el componente `App.js` llame a `/api/products` directamente, mientras el servidor de desarrollo de React se encarga de redirigir silenciosamente la solicitud al puerto del backend.
* **CORS Global en Backend:** El backend también tiene una configuración CORS global (`WebConfig.java`) para asegurar la compatibilidad en otros entornos.

---

## ▶️ Guía de Inicio Rápido

### Requisitos

* Node.js (LTS) y npm

### Pasos

1.  **Asegurar Backend:** Confirme que el servidor Spring Boot esté **ejecutándose** en `http://localhost:8080`.
2.  Navegue a la carpeta raíz de este proyecto (`react-frontend-productos`).
3.  Instale las dependencias (si es necesario):
    ```bash
    npm install
    ```
4.  Ejecute la aplicación:
    ```bash
    npm start
    ```

La aplicación se abrirá automáticamente en `http://localhost:3000` y mostrará la lista de productos obtenida de la API.
