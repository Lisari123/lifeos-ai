# LifeOS AI

> Crear una aplicación inteligente que ayude a las personas a organizar su tiempo, mejorar sus hábitos y cumplir sus objetivos.

LifeOS AI reúne en un solo lugar tareas, tiempo, hábitos y objetivos, y usa inteligencia artificial para sugerir un plan diario según el tiempo realmente disponible. Es el Proyecto de Aula de **Estándares y Calidad de Software** (Fundación Universitaria Los Libertadores).

- **Equipo:** Lisari Córdoba Gómez (líder del proyecto) y Camilo Andrés Carrillo (programador y tester)
- **Docente:** Franklin Alfredo Viasus Rios
- **Metodología:** Scrum (Sprint de 2 semanas)
- **Estándares:** ISO/IEC/IEEE 12207 (ciclo de vida) e ISO/IEC 25010 (calidad del producto)

## Funciones del Sprint 1

| Historia | Función | Requisitos |
|---|---|---|
| HU-01 | Crear cuenta, iniciar sesión y perfil | R-01, R-02 |
| HU-02 | Crear, editar y eliminar tareas con fecha y hora; sincronización | R-03, R-04 |
| HU-03 | Recordatorios de tareas y hábitos | R-05 |
| HU-04 | Plan diario sugerido por IA | R-06 |

Pendientes para los siguientes Sprint: calendario semanal (R-07), seguimiento de hábitos (R-08), aislamiento de datos entre usuarios (R-09) y uso en celular y navegador (R-10). El detalle está en [`docs/trazabilidad.md`](docs/trazabilidad.md).

## Requisitos previos

- **Lenguaje / entorno de ejecución:** `[completar, p. ej. Node.js 20+ o Python 3.11+]`
- **Framework:** `[completar]`
- **Base de datos:** `[completar]`
- **Git** y un navegador web actualizado
- Una **clave de acceso al servicio de IA** (se pide al equipo; nunca se sube al repositorio)

## Instalación y ejecución local

```bash
# 1. Clonar el repositorio
git clone https://github.com/[usuario]/lifeos-ai.git
cd lifeos-ai

# 2. Instalar dependencias
[completar: p. ej. npm install  /  pip install -r requirements.txt]

# 3. Configurar las variables de entorno
cp .env.example .env
# Abrir .env y completar los valores (ver tabla de abajo)

# 4. Ejecutar la aplicación
[completar: p. ej. npm run dev  /  python app.py]
```

Cuando arranque, abrir `http://localhost:[puerto]` en el navegador.

### Variables de entorno

| Variable | Para qué sirve |
|---|---|
| `DATABASE_URL` | Conexión a la base de datos |
| `AI_API_KEY` | Clave del servicio de IA para el plan diario |
| `AI_TIMEOUT_MS` | Tiempo máximo de espera de la IA (meta: 5000 ms) |
| `SESSION_SECRET` | Secreto para firmar las sesiones |
| `PORT` | Puerto local |

## Despliegue en la nube

`[completar: plataforma, URL del despliegue y pasos. Ejemplo: configurar las mismas variables de entorno en el panel de la plataforma y conectar la rama main.]`

## Credenciales de prueba

Se usan **dos cuentas** porque la prueba de aislamiento de datos (R-09) las necesita.

| Cuenta | Correo | Contraseña |
|---|---|---|
| Usuario de prueba 1 | `[completar]` | `[completar]` |
| Usuario de prueba 2 | `[completar]` | `[completar]` |

> Son cuentas solo de prueba. Nunca usar datos personales reales.

## Cómo trabajamos (gestión de configuración)

- Una **rama por historia** que sale de `main`: `feature/HU-02-tareas`.
- **Nada se fusiona sin revisión por pares:** Lisari revisa el código y las pruebas; Camilo revisa los documentos.
- Los documentos viven en Google Drive con nombre y fecha de versión.

Las reglas completas están en [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Metas de calidad (ISO/IEC 25010)

| Característica | Meta |
|---|---|
| Usabilidad | Cuenta, primera tarea y plan del día en menos de 2 minutos desde el celular, sin manual |
| Eficiencia de desempeño | Menos de 2 s en el 95 % de las solicitudes; plan con IA en menos de 5 s |
| Seguridad | Contraseñas cifradas, cada usuario solo ve sus datos, accesos no autorizados registrados |
| Fiabilidad | 99 % de disponibilidad, ninguna tarea perdida al sincronizar, recordatorios a la hora (±1 min) |

## Estructura del repositorio

```
lifeos-ai/
├── README.md
├── CONTRIBUTING.md
├── .env.example
├── .gitignore
├── .github/
│   ├── pull_request_template.md
│   └── ISSUE_TEMPLATE/historia-de-usuario.md
├── docs/
│   ├── trazabilidad.md
│   └── configuracion-github.md
└── [src/]        # código fuente de la aplicación
```
