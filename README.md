# 🚪 API Gateway (Spring Cloud Gateway)

Punto de entrada único (*Single Entry Point*) y orquestador de tráfico perimetral para la arquitectura de microservicios. Implementado con **Spring Cloud Gateway** y **Spring Boot 3**.

---

## 🚀 Características Principales

* **Enrutamiento Dinámico & Balanceo de Carga:** Ruteo transparente hacia servicios satélites mediante resolución de nombres y balanceo de carga con **Netflix Eureka** (`lb://`).
* **Seguridad Perimetral & CORS Centralizado:** Configuración estricta de políticas de intercambio de recursos de origen cruzado (`CorsFilter`) con soporte para credenciales/cookies (`allowCredentials`).
* **Resiliencia & Timeouts:** Control granular de tiempos de espera de conexión (`connect-timeout`) y respuesta (`response-timeout`) a nivel de cliente HTTP perimetral.
* **Descubrimiento Autónomo:** Registro y sincronización de instancias activas mediante **Eureka Client**.

---

## Mapa de Rutas de Microservicios

| Servicio Destino | Prefijo de Ruta | Identificador Eureka |
| :--- | :--- | :--- |
| **Autenticación** | `/api/auth/**` | `lb://AUTH` |
| **Convenios & Cuadrillas** | `/api/cuadrillas/**`, `/api/personal/**`, `/api/departamentos/**` | `lb://LIBRERIA` |
| **Ubicaciones** | `/api/ubicaciones/**` | `lb://UBICACION` |
| **Gestión Institucional**| `/api/gestion/**` | `lb://SERVICIO-GESTION-INSTITUCIONAL` |
| **Incidencias** | `/api/incidencias/**` | `lb://SERVICIOINCIDENCIAS` |
| **Notificaciones** | `/api/notificaciones/**` | `lb://NOTIFICACIONES` |
| **Evidencias** | `/api/evidencias/**` | `lb://SERVICIO-EVIDENCIAS` |
| **Seguimiento** | `/api/comentarios/**` | `lb://COMENTARIOS-SEGUIMIENTO` |
| **Reportes** | `/api/reportes/**` | `lb://REPORTES` |

---

## Stack Tecnológico

* **Lenguaje:** Java 17+
* **Framework:** Spring Boot 3.x, Spring Cloud Gateway
* **Service Discovery:** Netflix Eureka Client
* **Balanceo de Carga:** Spring Cloud LoadBalancer

---
