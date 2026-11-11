<div align="center">

# Carlos Olivera

### Desarrollo web asistido por IA · fundador de AIDO · Chascomús, Argentina

*No soy programador: dirijo a la IA desde la idea hasta que el sistema funciona en producción, y lo mantengo.*

[![Web](https://img.shields.io/badge/aidoagenciaweb.com.ar-000?style=for-the-badge)](https://aidoagenciaweb.com.ar)
[![Brooklyn Blade](https://img.shields.io/badge/En_producción-brooklynblade.com.ar-d71f28?style=for-the-badge)](https://brooklynblade.com.ar)

</div>

---

## Sobre mí

Técnico en **Informática Personal y Profesional** (E.E.S.T. N.º 1, Chascomús). Fundé **AIDO**, una agencia que ayuda
a negocios locales a vender más y organizarse mejor con sistemas simples, webs y contenido.

No escribo código a mano. Trabajo con **Claude Code**: yo decido qué hay que resolver y cómo se tiene que comportar
el sistema, la IA escribe el código, y yo compruebo que funcione —con pruebas automáticas, revisiones de seguridad
y el sistema andando en el navegador y en el teléfono— antes de darlo por terminado.

## Cómo trabajo

1. **Entiendo el problema del negocio**: qué le traba el día a día y qué tiene que poder hacer el sistema.
2. **Lo parto en pasos chicos**: una rama de Git por cambio y pull request para unirlo.
3. **Lo compruebo**: pruebas automáticas, revisores automáticos de calidad y seguridad desde varios puntos de vista, y el sistema funcionando de verdad.
4. **Lo publico y lo mantengo**: servidor propio con Docker, HTTPS y copias de seguridad; dominio, Google Business Profile, Bing y Meta Business Suite.

---

## Cómo fuimos evolucionando

| Cuándo | Qué | Con qué |
|---|---|---|
| **2025** | Primer año de la Tecnicatura en Ciencia de Datos e IA; vuelvo a programar, ahora con IA | Python, Claude Code |
| **oct 2025** | Primer aviso ofreciendo páginas web, con un sistema de heladería hecho en PHP | PHP, CodeIgniter 4 |
| **dic 2025** | Primera web de la agencia, [aidoagencia.com](https://aidoagencia.com) — la hizo mi ex socio, en Laravel | Laravel, Livewire, particles.js, Tailwind, Cloudflare, Hostinger |
| **feb–mar 2026** | Demos y primeros productos: turnos, tienda, entradas, delivery | Next.js, Prisma, PostgreSQL, Vercel |
| **mar–abr 2026** | Plataforma para un estudio de calistenia: reservas, panel del profesor y progreso de cada alumno. ~24 días de trabajo, con revisiones de seguridad. **El cliente finalmente no la adoptó**; el trabajo quedó hecho y es la base de un producto para gimnasios | Next.js, PostgreSQL |
| **abr–may 2026** | Sistema de socios y cuotas para un club deportivo, hecho como favor, en **Laravel** — y el mismo sistema rehecho en **.NET** | PHP 8.3, Laravel 12, Filament 4, MySQL · C# / .NET |
| **may–jun 2026** | **Primer cliente pago**: web de Central de Service (SEO 100 en Lighthouse) | HTML/CSS sin dependencias |
| **jun 2026 →** | **Fábrica de contenido**: reels, historias, motion graphics, logos animados, imágenes y video con IA | Remotion, CapCut, Google Flow, Blender, FFmpeg, Python |
| **ago–oct 2026** | App de pedidos para una hamburguesería (Brutal Burgers) · web y presencia en Google, Maps y Bing para Pampasuyu | Next.js · Google Business Profile, Bing Places, IndexNow |
| **oct–nov 2026** | **Brooklyn Blade**: turnos de una barbería, en uso diario con datos reales | Next.js, TypeScript, PostgreSQL, Docker, servidor propio |
| **nov 2026** | Sistema para un distribuidor que llevaba todo a mano: fiado, quién le debe y a quién debe, ventas, clientes, frecuencia de compra y último pedido · servidor propio de AIDO | Next.js, PostgreSQL · Ubuntu, Docker, Traefik |

---

## Qué resolvemos (problemas reales)

- **Horas sacando cuentas a mano** → un sistema que dice al instante quién debe, cuánto se vendió y quién hace cuánto que no compra.
- **Turnos por WhatsApp** → reservas online con panel para cada profesional (Brooklyn Blade).
- **Que el negocio no aparece** → web, Google Business Profile, Bing Places y Meta Business Suite; indexación pedida a mano para que Google la reconozca en uno o dos días; SEO y GEO para que **ChatGPT y Google** reconozcan al negocio (lo logramos con nuestro primer cliente).
- **Que la web se caiga sin que nadie se entere** → monitoreo que revisa cada web y avisa por correo.
- **Clientes que hablan otro idioma** → webs en español, inglés y portugués.
- **Redes sin contenido** → reels, historias y motion graphics hechos a medida.

---

## Proyectos

### 💈 Brooklyn Blade — turnos en uso diario · [brooklynblade.com.ar](https://brooklynblade.com.ar)
Reservas online y panel para dos barberos, con datos reales todos los días.
**61 pull requests · unas 545 pruebas automáticas · integración continua · servidor propio con Docker y copias cifradas.**
Tres revisiones independientes (calidad, seguridad y TypeScript) no encontraron fallas críticas.
`Next.js` · `TypeScript` · `PostgreSQL` · `Docker` — *el código es del cliente, por eso no es público.*

### ⚽ Club Rojo Deportivo — demo hecha para una entrevista · [ver demo](https://club-rojo.138-36-238-182.sslip.io)
**Creada pura y exclusivamente para mostrar en una entrevista de trabajo (PHP / Laravel).** Toma el sistema de socios y
cuotas que hicimos para un club, con marca y datos ficticios: socios, cuotas, reportes en PDF y Excel, portal por DNI,
web en **español, inglés y portugués** y escudo en 3D.
**318 pruebas automáticas · revisión de seguridad y auditoría de dependencias antes de publicar.**
`PHP 8.3` · `Laravel 12` · `Filament 4` · `MySQL` · `three.js` · `GSAP` · `Docker`

### 🤸 Plataforma para gimnasios y estudios · [calistenia-chascomus.vercel.app](https://calistenia-chascomus.vercel.app)
Reservas, panel del profesor y progreso de cada alumno. Hecha para un estudio que al final no la adoptó; hoy es la base
de un producto genérico para gimnasios. [Caso de estudio →](./case-studies/calistenia-chascomus.md)
`Next.js` · `PostgreSQL`

### 📅 Turnos para profesionales · [turnos.aidoagencia.com](https://turnos.aidoagencia.com)
`Next.js` · `PostgreSQL`

### 🔧 Webs y presencia de comercios locales
- **Central de Service** (nuestro primer cliente pago): web con SEO 100 y rendimiento 91 en Lighthouse; ChatGPT y Google lo reconocen.
- **Pampasuyu** (impresión 3D): web, perfil nuevo en Google Maps, alta en Bing e IndexNow.
- **Brutal Burgers**: app de pedidos.
- **La Nota Music Store**: en curso.

### 🎬 Contenido
Reels, historias, motion graphics y logos animados para clientes y para AIDO, producidos por script y medidos contra referencias:
`Remotion` · `CapCut` · `Google Flow` (imagen y video con IA) · `Blender` · `FFmpeg` · `Whisper`

---

## Con qué trabajo

`Claude Code` · `PHP` · `Laravel` · `Filament` · `MySQL` · `Next.js` · `TypeScript` · `PostgreSQL` · `C# / .NET` ·
`Pest` · `Vitest` · `Playwright` · `Docker` · `Linux` · `Git y GitHub` · `three.js` · `GSAP` · `Remotion` · `Python`
