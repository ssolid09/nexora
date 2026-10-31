# NEXORA

**Controla · Planifica · Ahorra**  
*Tu vida financiera, en tus manos.*

NEXORA es el proyecto de una plataforma fintech para la gestión de finanzas personales y familiares, con enfoque premium y arquitectura preparada para multiusuario.

## Estado del proyecto

Frontend funcional en `frontend/index.html` (archivo único): login, resumen, quincena, último del mes, tarjetas, transferencia, movimientos, presupuestos, metas, reportes y configuración. Esquema PostgreSQL y migración del Excel en `database/migrations/`. Ver `docs/INSTALACION.md` para ejecutar y para la lista de pendientes.

## Estructura

- `docs/`: documentación funcional, técnica y decisiones del proyecto.
- `design/brand/`: identidad visual y guía de marca.
- `design/references/`: referencias visuales y capturas aprobadas.
- `frontend/`: aplicación de interfaz (pendiente de definir según el proyecto actual).
- `backend/`: API y lógica de negocio (pendiente de auditoría).
- `database/migrations/`: migraciones de base de datos.
- `database/seeds/`: datos iniciales no sensibles.
- `scripts/`: automatizaciones y utilidades.
- `tests/`: pruebas unitarias, integración y seguridad.
- `assets/`: logotipos, iconos e imágenes.

## Regla fundamental

Antes de modificar el sistema existente, realizar una copia de seguridad, auditar la tecnología y diseñar un plan de migración. No eliminar ni sobrescribir registros originales.

## Próximo paso

Incorporar la carpeta completa del sistema actual y ejecutar la auditoría descrita en `docs/PLAN_DE_TRABAJO.md`.
