# 🧪 Estrategia de Pruebas - Proyecto QA Tiketera

## 🎯 Objetivo General

Garantizar la calidad funcional, estabilidad, rendimiento y usabilidad del sistema **Tiketera**, a través de pruebas manuales, automatizadas, de APIs y de carga, documentadas y ejecutadas con enfoque profesional.

---

## 🔍 Alcance de las Pruebas

Se abordarán los siguientes aspectos:

- Validación de flujos funcionales: login, gestión de tickets, búsquedas, filtros, asignaciones.
- Verificación de errores visuales, campos obligatorios y reglas de negocio.
- Pruebas exploratorias para detectar errores ocultos.
- Automatización de flujos repetitivos y críticos.
- Evaluación del rendimiento y estabilidad bajo carga.
- Validación de APIs utilizadas por el sistema.
- Análisis de tiempos de respuesta y detección de cuellos de botella.

---

## 🧭 Tipos de Pruebas Aplicadas

| Tipo de prueba       | Descripción                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| Funcional manual     | Validación de flujos principales mediante casos estructurados.              |
| Exploratoria         | Pruebas dinámicas para descubrir errores no anticipados.                    |
| Automatización UI    | Cobertura de flujos críticos mediante scripts en Cypress.                   |
| Pruebas de API       | Validación de endpoints, status, y estructura con Postman + Newman.         |
| Rendimiento y estrés | Simulación de carga concurrente y picos con K6 / JMeter.                    |
| Regressión           | Repetición de pruebas tras cambios, automatizada o manual según impacto.   |

---

## 🛠 Herramientas utilizadas

| Categoría            | Herramientas                         |
|----------------------|--------------------------------------|
| Pruebas manuales     | GitHub Issues                        |
| Automatización UI    | Cypress                              |
| Pruebas de API       | Postman + Newman                     |
| Rendimiento / estrés | K6, JMeter                           |
| Reportes / CI-CD     | GitHub Actions, Jenkins              |

---

## 🌐 Entorno de pruebas

- **URL del sistema:** [http://vsrv-idnet:9098/login/](http://vsrv-idnet:9098/login/)
- **Navegadores utilizados:** Chrome, Brave, Edge
- **Entorno:** Interno / Preproducción
- **Resoluciones evaluadas:** 1920x1080, 1366x768, 1024x768, 375x667

---

## ✅ Criterios de Aceptación

- Todos los flujos críticos deben completarse sin errores funcionales o bloqueos.
- Las APIs deben responder con status 200 y estructura esperada.
- El sistema debe comportarse estable con hasta X usuarios concurrentes (a definir).
- El tiempo de carga debe ser ≤ 3 segundos en condiciones normales.
- No deben existir errores graves en consola ni enlaces rotos.

---

## 🚫 Criterios de Salida

- Ejecución completa de todos los casos definidos.
- Todos los bugs críticos o altos deben estar corregidos o justificados.
- Evidencias almacenadas y revisadas.
- Reporte de resultados finalizado y documentado.
