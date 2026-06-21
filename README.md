# spring-cloud-config

Repositorio **Git de configuración externa**. No es una aplicación ejecutable: contiene archivos `.properties` que el **config-server** sirve a los microservicios.

## Contenido

| Archivo | Descripción |
|---------|-------------|
| `msvc-items.properties` | Configuración base de `msvc-items` (puerto 8005) |
| `msvc-items-dev.properties` | Perfil de desarrollo (texto, autor, email) |
| `msvc-items-prod.properties` | Perfil de producción (puerto 8007) |

## Importancia en el ecosistema

Es la **fuente de verdad** de la configuración remota. Los cambios aquí se propagan a los servicios que usan Config Server sin tocar su código fuente.

**Relación con otros proyectos:**

- **config-server** lo lee desde Git (o desde una ruta local en desarrollo).
- **msvc-items** recibe estas propiedades al arrancar según su perfil activo (`dev`, `prod`, etc.).

Para que funcione en local, el contenido debe estar pusheado al remoto configurado en `config-server` o apuntar el servidor al path local del repositorio.
