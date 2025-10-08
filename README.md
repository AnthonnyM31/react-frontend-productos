# ⚛️ Frontend React: Consumo de API y Proxy de Desarrollo

<p align="center">
  <img src="https://img.shields.io/badge/React-2024-61DAFB?logo=react&logoColor=white" alt="React"/>
  <img src="https://img.shields.io/badge/NPM-Proxy-red" alt="NPM Proxy"/>
  <img src="https://img.shields.io/badge/Comunicación-CORS_Solucionado-yellowgreen" alt="CORS Solucionado"/>
</p>

## 🎯 Objetivo y Rol Arquitectónico

Este repositorio contiene la **Capa de Presentación** (Frontend) construida con React, cuyo único propósito es consumir y visualizar los datos proporcionados por el *backend* de Spring Boot (`api-cache-proxy-arquitectura`).

La aplicación está diseñada para ser minimalista, enfocándose en la **prueba funcional** de los *endpoints* y la **verificación del rendimiento** del sistema de caché.

---

## 🔗 Estrategia de Comunicación

Para garantizar una comunicación fluida entre el *frontend* (`:3000`) y el *backend* (`:8080`), implementamos la estrategia más eficiente para desarrollo:

1.  **Proxy de Desarrollo (`package.json`):**
    * La línea `"proxy": "http://localhost:8080"` en el archivo `package.json` redirige todas las solicitudes internas (como `fetch("/api/products")`) del *frontend* al servidor de Spring Boot.
    * **Ventaja:** Esto evita problemas de **CORS (Cross-Origin Resource Sharing)** en el entorno local de desarrollo.

2.  **Lógica del Componente (`src/App.js`):**
    * Utiliza el *hook* **`useEffect`** para realizar la llamada **`GET /api/products`** al montar la página.
    * La recarga manual del navegador es el método utilizado para **forzar una nueva solicitud** y probar el funcionamiento del caché en el *backend*.

---

## ▶️ Guía de Inicio Rápido

### 1. Requisitos

* Node.js (LTS) y npm.
* **El Backend debe estar corriendo:** Asegure que el servidor Spring Boot esté **ejecutándose** en `http://localhost:8080`.

### 2. Pasos para la Ejecución

1.  Navegue a la carpeta raíz de este proyecto (`react-frontend-productos`) en su terminal.
2.  Instale las dependencias (si es necesario):
    ```bash
    npm install
    ```
3.  Inicie el servidor de desarrollo:
    ```bash
    npm start
    ```

La aplicación se abrirá automáticamente en `http://localhost:3000`.

### 🧪 Prueba de Caché

Para realizar la prueba de rendimiento completa, siga los pasos detallados en el `README` del repositorio del *backend*.

1.  Asegúrese de que al menos un producto haya sido insertado vía `POST`.
2.  **Carga Inicial:** Visite `http://localhost:3000`. La consola del *backend* debe mostrar el acceso a la Base de Datos (Cache Miss).
3.  **Recarga Inmediata:** Recargue la página (**F5**). La consola del *backend* **no debe mostrar** el mensaje de acceso a la Base de Datos (Cache Hit).
