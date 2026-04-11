# Caso de estudio — Calistenia Chascomús

**De WhatsApp caótico a plataforma con 130+ alumnos en 23 días**

> Construido 100% con Claude Code. Sin equipo de desarrollo. Sin experiencia previa en programación.

---

## Métricas clave

| | |
|--|--|
| ⏱ Tiempo de desarrollo | 23 días (16 mar → 8 abr 2026) |
| 📦 Commits | 140 |
| 👥 Alumnos activos | 130+ |
| 🔒 Score de seguridad | A+ (securityheaders.io) |
| 🚀 Deploy | Vercel (producción continua) |
| 💳 Pagos | Mercado Pago integrado |

---

## El cliente

**Agus Acosta** — entrenador de calistenia en Chascomús, Buenos Aires.
Emprendimiento personal con más de 130 alumnos activos.

---

## El problema

Agus manejaba todo su emprendimiento con herramientas informales:

- **130 alumnos preguntando simultáneamente** por WhatsApp cómo ejecutar cada ejercicio
- **Sin sistema de organización** de alumnos, asistencia ni progreso
- **Sin presencia web profesional** que mostrara su trabajo y metodología
- **Sin forma de cobrar online** — todo efectivo o transferencias manuales

El resultado: tiempo enorme dedicado a responder las mismas preguntas, imposible escalar, y ninguna diferenciación frente a otros entrenadores.

---

## La solución

Plataforma web completa, accesible desde cualquier dispositivo, con tres módulos:

### 🌳 Skill Trees — La guía de ejercicios interactiva
Árbol visual de progresión de habilidades. Cada alumno ve exactamente en qué nivel está y qué debe dominar para avanzar. Elimina el 80% de las consultas repetitivas por WhatsApp.

### 📅 Booking público
Página pública donde cualquier alumno agenda su clase sin necesitar cuenta. Agus ve el panel completo con agenda, confirmaciones y cancelaciones.

### 💳 Cobros con Mercado Pago
Checkout integrado. El alumno paga online, el sistema confirma automáticamente. Sin transferencias manuales ni seguimiento.

### 📧 Emails automáticos
Confirmaciones y recordatorios via Resend. Agus no tiene que hacer seguimiento manual de cada alumno.

---

## Cómo se construyó

**Herramienta:** Claude Code (Anthropic) — 100% del código generado y revisado con IA.

**Mi rol como orquestador:**
1. Definí la arquitectura antes de escribir una línea — modelos de datos, flujos de usuario, decisiones de stack
2. Especifiqué cada feature con contexto completo: qué problema resuelve, restricciones técnicas, casos edge
3. Revisé cada decisión de seguridad — el sistema pasó de 0 a A+ en securityheaders.io con 13 fixes específicos
4. Validé el sistema con un simulador Python de 130 alumnos y 6 meses de datos antes del lanzamiento
5. Gestioné el deploy a Vercel con variables de entorno, dominio y configuración de producción

**Lo que esto demuestra:** el cuello de botella en desarrollo no es escribir código — es saber qué construir, en qué orden, y cómo hacerlo seguro. Eso es lo que aporté.

---

## Arquitectura técnica

```
┌─────────────────────────────────────────────┐
│              ALUMNO / PÚBLICO               │
│   Booking sin cuenta · Skill Trees · Cobro  │
└─────────────────┬───────────────────────────┘
                  │
┌─────────────────▼───────────────────────────┐
│           Next.js 16 — App Router           │
│   Server Components · Server Actions        │
│   Middleware Auth (Edge Runtime)            │
└──────┬──────────────────────────┬───────────┘
       │                          │
┌──────▼──────┐          ┌────────▼────────┐
│  Neon DB    │          │  Servicios ext.  │
│  Prisma 7   │          │  MP · Resend     │
│  PostgreSQL │          │  Upstash Redis   │
└─────────────┘          └─────────────────┘
```

**Stack completo:**
`Next.js 16.2` · `React 19` · `TypeScript` · `Prisma 7` · `Neon PostgreSQL` · `NextAuth v5` · `Mercado Pago SDK 2.12` · `Resend` · `Upstash Redis` · `Tailwind v4` · `Vercel`

**Decisiones técnicas destacadas:**

- **Rate limiting con Upstash Redis** — protección contra bots en endpoints de booking sin impactar performance (serverless-compatible)
- **Auth split Edge/Node** — `auth.config.ts` corre en Edge Runtime para el middleware, `auth.ts` en Node para la lógica de sesión. Necesario por las limitaciones de Next.js 16
- **Prisma 7 Driver Adapter** — `PrismaNeon` para conexiones serverless de corta duración en Vercel
- **Simulación pre-lanzamiento** — script Python que generó 130 alumnos ficticios con 6 meses de actividad para detectar bugs de performance antes de ir a producción

---

## Resultado

La plataforma está en producción desde el 8 de abril de 2026 con **130+ alumnos activos**.

Agus pasó de gestionar todo por WhatsApp a tener un sistema profesional que:
- Responde automáticamente cómo hacer cada ejercicio (skill trees)
- Organiza su agenda sin intervención manual
- Cobra online sin fricción
- Muestra su trabajo con presencia web propia

---

## Lo que aprendí

**El mayor obstáculo no fue técnico — fue de producto.**

Definir exactamente qué necesitaba Agus (vs. lo que parecía necesitar) fue más difícil que cualquier decisión de arquitectura. Los skill trees no estaban en el brief original — surgieron al entender el problema real: los alumnos no sabían qué ejercicio practicar, no que no podían agendar.

Eso es lo que hace la diferencia entre un developer que ejecuta y un orquestador que entiende.

---

## Sobre el proceso de desarrollo

Este proyecto fue construido completamente con **Claude Code**, el CLI de Anthropic.

No escribo código manualmente. Mi trabajo es:
- Entender el problema de negocio en profundidad
- Tomar decisiones de arquitectura con sus trade-offs
- Especificar features con contexto completo para la IA
- Revisar seguridad, performance y calidad del resultado
- Entregar productos que funcionen en producción

**Ver el producto en vivo:** [calistenia-chascomus.vercel.app](https://calistenia-chascomus.vercel.app)

**Construir algo similar para tu negocio:** [aidoagencia.com](https://aidoagencia.com)

---

*Carlo Olivera — AIDO Digital Agency · Chascomús, Buenos Aires*
