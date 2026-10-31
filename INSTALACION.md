# NEXORA · Instalación y operación

## Sin Supabase (modo local)
Abre `frontend/index.html`. Cuentas y datos quedan solo en ese navegador (para pruebas; no es seguridad real).

## Con Supabase (multiusuario real)
1. Crea un proyecto en supabase.com.
2. SQL Editor: ejecuta `database/migrations/001_nexora_schema.sql`.
3. En `frontend/index.html` busca `const CFG={url:'',key:''}` y pega la Project URL y la anon key (clave pública; nunca uses `service_role`).
4. Authentication > URL Configuration: agrega la URL donde publiques como Site URL.
5. Sube el repo a GitHub y activa Settings > Pages con la carpeta `/frontend`.

## Importar el Excel
Regístrate en la app, abre `database/migrations/002_importar_excel.sql`, cambia `TU_CORREO` y ejecútalo. Se revierte si los totales no coinciden con el Excel. Supuestos: año 2026, quincena día 15, último del mes = último día, sueldo día 1.

## Variables de configuración
| Nombre | Dónde | Descripción |
|---|---|---|
| `CFG.url` | `frontend/index.html` | URL del proyecto Supabase |
| `CFG.key` | `frontend/index.html` | anon key (pública, protegida por RLS) |

## Respaldo
- App: Configuración > Descargar respaldo (JSON).
- Supabase: Database > Backups o `pg_dump`. Respalda antes de ejecutar cualquier migración.

## Funcionalidades
**Implementadas (frontend):** login/registro, cierre de sesión, quincena, último del mes, tarjetas, transferencia con captura, movimientos con categorías, presupuestos con alertas, metas con aportes, reportes por período, perfil/moneda/fecha, cambio de contraseña, respaldo, modo claro/oscuro, identidad NEXORA.

**Pendientes:**
- Conectar la app a las tablas relacionales de `001` (hoy guarda una fila JSON por usuario en `gastos_data`).
- Cuentas múltiples y transferencias entre cuentas.
- Grupos familiares: tablas creadas; faltan invitaciones, roles, políticas de gastos compartidos y su interfaz.
- Importar hojas COLCHON y Hoja2 (cuotas).
- Logos adicionales (horizontal, fondo claro, icono de app) y pruebas automatizadas (`tests/`).
- Exportación de reportes y notificaciones.
