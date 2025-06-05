# 🧪 Proyecto QA - Tiketera (Sistema de Tickets Interno)

## 🎯 Objetivo del Proyecto

Este repositorio contiene las actividades de aseguramiento de calidad realizadas sobre el sistema **Tiketera**, utilizado internamente por la empresa.  
Se aplicarán pruebas funcionales, no funcionales, de rendimiento, pruebas a APIs, pruebas de estrés y automatización de flujos críticos donde sea posible.

---

## 🔍 Alcance

Las pruebas cubrirán los siguientes aspectos:

- ✅ **Pruebas funcionales**: validación de login, gestión de tickets, asignaciones, búsquedas, filtros y flujos principales del sistema.
- ⚙️ **Pruebas no funcionales**: accesibilidad, usabilidad, compatibilidad, estabilidad y seguridad básica.
- 📈 **Pruebas de rendimiento**: tiempos de carga, respuesta de APIs y comportamiento bajo carga.
- 🔌 **Pruebas de APIs**: validación de endpoints, respuestas, status codes y datos estructurados.
- 💥 **Pruebas de estrés**: evaluación del comportamiento bajo condiciones extremas.
- 🤖 **Automatización**: flujos críticos automatizados con Cypress.

---

## 🛠 Herramientas que se utilizarán

| Tipo de prueba          | Herramienta principal         |
|--------------------------|-------------------------------|
| Funcional Manual         | GitHub Issues                 |
| Automatización UI        | Cypress                       |
| API Testing              | Postman + Newman              |
| Rendimiento y estrés     | K6 / JMeter                   |
| Reportes y CI/CD         | GitHub Actions / Jenkins      |

---

## 🌐 Entorno de pruebas

- **URL del sistema**: [http://vsrv-idnet:9098/login/](http://vsrv-idnet:9098/login/)
- **Entorno**: Interno / Pre-producción
- **Navegadores utilizados**: Chrome, Brave, Edge
- **Dispositivos**: Desktop

---

## 📁 Estructura del repositorio
Tiketera-QA/
├── 01-Funcional/
│ ├── CasosDePrueba.md
│ └── Evidencias/
├── 02-Automatizacion/
│ ├── Cypress/
│ └── Playwright/
├── 03-API/
│ ├── Postman/
│ └── Newman/
├── 04-Performance/
│ ├── k6/
│ └── jmeter/
├── docs/
│ ├── EstrategiaQA.md
│ ├── Checklist.md
│ └── README.md
└── README.md
