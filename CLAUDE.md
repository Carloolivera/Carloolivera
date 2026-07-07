# CLAUDE.md — Reglas permanentes de trabajo

Estas reglas aplican a **toda** sesión en este repositorio. No son sugerencias.

## Las 4 reglas

### 1. Planifica antes de escribir código
Antes de editar cualquier archivo: lee el código relevante, reformula el pedido
en una frase y escribe un plan corto (qué archivos tocás, qué cambio mínimo
cumple el pedido, cómo vas a verificar que funciona). Si el plan no cabe en
5–10 líneas, el pedido es demasiado grande: dividilo.

### 2. Refuta tu propia respuesta antes de dármela
Antes de entregar, atacá tu propio trabajo: buscá el caso que lo rompe, el
supuesto que no verificaste, la API que quizás inventaste. Si encontrás una
falla, corregila **antes** de responder. El detalle del checklist está en
`.claude/skills/auto-refutacion/SKILL.md`.

### 3. Abre con el resultado, no con el proceso
La primera frase de tu respuesta contesta "¿qué pasó?" o "¿qué encontraste?".
Nada de "Primero analicé...", "Empecé por...". El proceso va después, solo si
aporta. Si los tests fallan, decilo en la primera frase con el error.

### 4. No te salgas del alcance que te pedí
Hacé exactamente lo pedido. Nada de refactors oportunistas, renombres,
dependencias nuevas ni "mejoras" no solicitadas. Si ves algo que valdría la
pena arreglar, **mencionalo al final** — no lo toques sin permiso.

## Loop de verificación

Cuando el pedido implique que algo "funcione" o "pase" (tests, build, un flujo),
no te detengas al primer intento: **revisá tu salida, encontrá fallas y repetí
hasta que pase**, siguiendo el protocolo de
`.claude/skills/loop-verificacion/SKILL.md` (criterio de éxito definido antes
de iterar, re-diagnóstico si dos intentos no mueven el error, nunca declarar
éxito sin re-ejecutar la verificación completa).

## Razonamiento profundo (ultrathink)

Reservado para lo difícil, no para todo (quema más tokens):

- **Usalo en**: decisiones de arquitectura, bugs que resistieron 2+ intentos,
  seguridad, concurrencia, migraciones de datos, performance.
- **No lo uses en**: cambios de copy, estilos, CRUD simple, renombres.
- **Aterrizalo siempre**: al pedir más razonamiento, decí en qué pensar más —
  casos límite, seguridad, rendimiento — no solo "pensá más".

## Skills del playbook

Cómo razono, documentado por mí mismo, en `.claude/skills/`:

| Skill | Qué cubre |
|---|---|
| `fable-playbook` | Cómo ataco un problema de punta a punta: entender → planificar → ejecutar → verificar → reportar |
| `auto-refutacion` | Checklist para refutar mi propia respuesta antes de entregarla |
| `loop-verificacion` | Protocolo de iteración hasta que pase, con reglas anti-espiral |
