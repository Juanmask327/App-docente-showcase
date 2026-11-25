# App-docente-showcase

# 📚 App Docente

**Plataforma para digitalizar y automatizar el trabajo diario del docente de colegio:** asistencia, observador de convivencia, control de uniforme, notas, trabajos, calendario, archivos y ficha por estudiante, todo en un solo lugar.

Una sola base de código que funciona en **web, móvil (Android/iOS) y escritorio (Windows/macOS/Linux)**.

🔗 **Demo en vivo:** https://app-docente-snowy.vercel.app
🔒 **Código privado.** Es un proyecto con fines comerciales; el código está disponible para revisión bajo solicitud.

---

## 🚀 Pruébala

Entra a la demo y presiona **"Explorar la demo (solo lectura)"**, o inicia sesión con:

| Correo | Contraseña |
|---|---|
| `demo.appdocente@example.com` | `Demo2026App` |

La cuenta demo tiene **2 cursos y 24 estudiantes ficticios** con asistencia, observador, uniforme, notas, trabajos y calendario. Es de **solo lectura**: puedes recorrer todos los módulos, pero los cambios no se guardan. El bloqueo lo aplica la base de datos, no solo la interfaz.

> Todos los datos de la demo son inventados. La app maneja información de menores de edad, por eso nunca se usan datos reales.

---

## 🧩 Módulos

- **Inicio**: resumen del día con eventos próximos, alertas y actividad reciente.
- **Cursos y estudiantes**: ficha completa por estudiante, acudientes, traslado entre cursos y baja lógica (nunca se borra el historial).
- **Asistencia**: registro diario por curso (presente, ausente, tarde) con justificaciones y exportación a Excel.
- **Observador**: novedades de convivencia, académicas, disciplinarias y positivas, con estados abierto, pendiente y cerrado, y evidencias adjuntas.
- **Uniforme**: registro rápido de faltas de uniforme y hoja de control en Excel.
- **Trabajos**: tareas por curso con seguimiento de entregas por estudiante (entregado, tarde, pendiente).
- **Notas y planilla**: calificaciones en texto libre ("4.5" o "Sobresaliente") y una planilla por estudiante que combina notas, asistencia y uniforme.
- **Calendario**: eventos institucionales y fechas importantes por curso (exámenes, entregas, citaciones, nivelaciones).
- **Notificaciones y actividad reciente**: alertas pendientes y línea de tiempo de todo lo registrado.
- **Archivos**: los documentos generados se organizan solos por curso y por estudiante.
- **Reportes y búsqueda**: historial exportable y búsqueda global de estudiantes y funciones.
- **Configuración**: perfil, tema, tamaño de letra, datos del colegio y seguridad de la cuenta.

---

## 🛠️ Stack

| Capa | Tecnologías |
|---|---|
| Frontend | Next.js 16 (App Router), React 19, TypeScript, Tailwind CSS v4, shadcn/ui, Base UI |
| Datos en el cliente | TanStack Query, react-hook-form, Zod |
| Backend | Supabase: PostgreSQL, Auth, Storage, Realtime, Row Level Security, Edge Functions (Deno) |
| Multiplataforma | Capacitor (Android/iOS), Tauri (escritorio) |
| Pruebas | Vitest + Testing Library, Playwright (E2E), pgTAP (base de datos) |
| Infraestructura | Vercel, GitHub Actions (CI) |

---

## 🏗️ Arquitectura y seguridad

- **Un solo código para tres plataformas**: la misma app Next.js se empaqueta para móvil con Capacitor y para escritorio con Tauri.
- **Sin backend propio**: Supabase como backend como servicio; la lógica sensible vive en la base de datos y en Edge Functions.
- **Multi-tenant por fila**: cada tabla está protegida con políticas de Row Level Security. Un docente solo puede ver y modificar lo suyo, y el `docente_id` siempre lo deriva el servidor, nunca el cliente.
- **Historial que no se pierde**: las bajas son lógicas y la fecha y hora de cada registro las pone el sistema; no se pueden editar a mano.
- **Archivos seguros**: los Excel se generan en Edge Functions, protegidos contra inyección de fórmulas, y se entregan con URLs firmadas.
- **Recuperación de contraseña confinada**: la sesión temporal de recuperación no da acceso completo a la cuenta.
- **Demo de solo lectura a nivel de base de datos**: triggers y políticas de Storage bloquean cualquier escritura de la cuenta demo.

**En números:** 20 pantallas · 11 migraciones con RLS · 5 Edge Functions · 170 pruebas unitarias · 14 flujos E2E · 6 suites de pruebas de aislamiento entre docentes.

---

## 👤 Mi rol

**Director de producto y arquitecto de la solución.** Definí el MVP, el modelo de negocio, los requerimientos, la arquitectura y los wireframes. Coordiné agentes de IA especializados (backend, frontend, móvil, escritorio, QA, ciberseguridad y DevOps) que implementaron y desplegaron el código, mientras yo auditaba cada entrega, los errores y la seguridad. Todo el proceso queda registrado en el historial de commits del repositorio, disponible bajo solicitud.

---

## 🗺️ Estado

- ✅ Fase 1: cursos, estudiantes, ficha y asistencia
- ✅ Fase 2: observador, uniforme, archivos, web/escritorio y tiempo real
- ✅ Fase 3: calendario, notificaciones y configuración
- ✅ Fase 4: trabajos, reportes y actividad reciente
- ✅ Fase 5: notas y planilla
- 🔜 Modo sin conexión (offline-first)

---

## 📬 Contacto

**Juan Manuel Benitez Skolik**
✉️ Juanmabennitez2008@gmail.com · 💼 [LinkedIn](https://www.linkedin.com/in/juan-manuel-benitez-skolik-9863673a7/) · 🌐 [Portafolio](https://juanmask327.github.io/Portafolio/) · 🆔 [ORCID](https://orcid.org/0009-0009-2170-4617)

---

© 2026 Juan Manuel Benitez Skolik. Todos los derechos reservados.
