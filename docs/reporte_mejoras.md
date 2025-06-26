| ID       | Título de la Mejora                                        | Prioridad | Estado   | Módulo Afectado | Descripción de la mejora                                                                                         | Justificación                                                                                      | Recomendación                                                                                         | Reportado por     | Fecha      |
|----------|-------------------------------------------------------------|-----------|----------|------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|--------------------|------------|
| MEJ-001  | Bloqueo de usuario tras múltiples intentos fallidos de login | Alta      | Propuesta| Login            | Implementar un sistema de bloqueo temporal o definitivo tras varios intentos fallidos de inicio de sesión | Aumenta la seguridad del sistema ante intentos de fuerza bruta o accesos no autorizados           | Bloquear temporalmente la cuenta tras 5 intentos fallidos. Mostrar mensaje: “Usuario bloqueado. Contacte al administrador.” | Leandro G. Díaz    | 2025-06-05 |
| MEJ-002  | Evitar popup de sesión inactiva sin login activo                   | Media     | Propuesta| Control de sesión | Actualmente aparece un popup de sesión inactiva aunque no se haya iniciado sesión, lo cual es ilógico y confuso.     | Rompe la lógica de sesión y puede generar confusión en el usuario final.                                | Condicionar el popup para que solo se muestre si el usuario tiene una sesión activa iniciada correctamente. | Leandro G. Díaz    | 2025-06-05 |
| MEJ-005  | Aclarar que el login por email solo es válido para usuarios LDAP registrados | Media     | Propuesta| Login            | Actualmente se puede iniciar sesión con email si el usuario está registrado en LDAP, pero esto no se informa claramente. | Evita confusión al intentar ingresar con un email no reconocido por el sistema. Mejora la experiencia de usuario. | Mostrar un mensaje o placeholder aclarando: “Solo emails registrados internamente (LDAP) pueden usarse como usuario.” | Leandro G. Díaz    | 2025-06-05 |

# Reporte de Mejoras y Hallazgos

## Bug Crítico: El endpoint `POST /eventos` devuelve `200 OK` en caso de fallo

**ID del Bug:** API-001
**Fecha:** 26 de Junio de 2025
**Reportado por:** (Tu Nombre)
**Severidad:** Crítica

### Resumen
Al intentar crear un nuevo evento, la API responde con un código de estado `200 OK`, lo que incorrectamente indica éxito. Sin embargo, el cuerpo de la respuesta es el booleano `false` y el recurso no es creado en la base de datos. Este comportamiento es inconsistente y engañoso.

### Pasos para Reproducir
1.  Obtener un token de autorización válido a través del endpoint `POST /login`.
2.  Enviar una petición `POST` al endpoint de creación de eventos.
3.  Incluir el header `Authorization: Bearer <token>` con el token válido.
4.  Incluir un `Body` en formato JSON con los datos de un nuevo evento.

### Resultado Obtenido (Actual)
- El código de estado de la respuesta es `200 OK`.
- El cuerpo (`Body`) de la respuesta contiene únicamente el texto: `"false"`.
- Una petición posterior a `GET /eventos` no encuentra el recurso y devuelve `204 No Content`.

### Resultado Esperado
- **En caso de éxito:** El código de estado debería ser `201 Created` y el cuerpo de la respuesta debería contener el objeto del evento recién creado, incluyendo su nuevo `id`.
- **En caso de fallo:** El código de estado debería ser un error (ej: `400 Bad Request`) y el cuerpo debería contener un mensaje claro que explique por qué falló la creación.

### Impacto
Crítico. Impide saber si un evento se ha creado correctamente. La interfaz de usuario podría decirle al usuario "Evento creado" cuando en realidad no fue así, causando confusión y posibles pérdidas de datos. Hace que la API no sea fiable para integraciones.
