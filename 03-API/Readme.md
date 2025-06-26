# Pruebas de API con Postman para Tiketera

Este directorio contiene la colección y el ambiente de Postman para probar la API de Tiketera.

## Prerrequisitos
- Tener instalada la aplicación de [Postman](https://www.postman.com/downloads/).

## Configuración
1.  **Importar el Ambiente:** En Postman, ve a `File > Import...` y selecciona el archivo `Tiketera_Desarrollo.postman_environment.json`.
2.  **Importar la Colección:** Vuelve a `File > Import...` y selecciona el archivo `Tiketera_API.postman_collection.json`.
3.  **Seleccionar el Ambiente:** Asegúrate de seleccionar `Tiketera - Desarrollo` como tu ambiente activo en la esquina superior derecha de Postman.

## Flujo de Ejecución
La mayoría de los endpoints de esta API requieren autenticación. El flujo correcto para las pruebas es:

1.  **Ejecutar `POST /login`:** Ejecuta esta petición primero para obtener un token de autorización. El script en la pestaña "Tests" guardará automáticamente el token en la variable de ambiente `{{authToken}}`.
2.  **Ejecutar otras peticiones:** Todas las demás peticiones ya están configuradas para usar el token guardado (`Bearer {{authToken}}`). Simplemente ejecútalas después de haber hecho login.

## Bugs Conocidos
- **[BUG CRÍTICO]** El endpoint `POST /eventos` devuelve un código de éxito (`200 OK`) incluso cuando la creación del recurso falla. Ver detalles en el reporte general.
