# Fable Playbook

Los hábitos de trabajo de Claude Fable 5, documentados por el propio modelo
y empaquetados para instalarse en cualquier proyecto con Claude Code.
La idea: lo que hace bueno al modelo no es magia — **planifica antes de
escribir, se refuta a sí mismo, abre con el resultado y respeta el alcance**.
Son hábitos, y los hábitos se copian.

## Qué contiene este repo

| Movimiento | Qué es | Dónde vive |
|---|---|---|
| **1 — El playbook como skills** | Fable 5 documentó cómo razona: su método de ataque, sus checklists, sus reglas anti-espiral | [`.claude/skills/fable-playbook/`](../.claude/skills/fable-playbook/SKILL.md) · [`auto-refutacion/`](../.claude/skills/auto-refutacion/SKILL.md) · [`loop-verificacion/`](../.claude/skills/loop-verificacion/SKILL.md) |
| **2 — Las reglas en CLAUDE.md** | Las 4 reglas permanentes que Claude lee en cada sesión: planificar antes, refutarse, abrir con el resultado, no salirse del alcance | [`CLAUDE.md`](../CLAUDE.md) |
| **3 — El loop** | «Revisá tu salida, encontrá fallas y repetí hasta que pase», con criterio de éxito definido antes de iterar y reglas anti-espiral | [`.claude/skills/loop-verificacion/`](../.claude/skills/loop-verificacion/SKILL.md) + comando [`/hasta-que-pase`](../.claude/commands/hasta-que-pase.md) |
| **4 — Razonamiento profundo** | Cuándo usar `ultrathink` (y cuándo no), y cómo aterrizarlo diciéndole en qué pensar más | Sección "Razonamiento profundo" de [`CLAUDE.md`](../CLAUDE.md) |

## Instalar en un proyecto

Desde la raíz de este repo, copiá al proyecto destino:

```bash
cp CLAUDE.md /ruta/al/proyecto/CLAUDE.md   # o pegá las secciones en el CLAUDE.md existente
cp -r .claude/skills /ruta/al/proyecto/.claude/
cp -r .claude/commands /ruta/al/proyecto/.claude/
```

Si el proyecto ya tiene `CLAUDE.md`, no lo pises: agregale las secciones
"Las 4 reglas", "Loop de verificación" y "Razonamiento profundo".

## Instalar global (todas tus sesiones)

Las skills y reglas en `~/.claude/` aplican a todos tus proyectos:

```bash
cp -r .claude/skills ~/.claude/
cp -r .claude/commands ~/.claude/
cat CLAUDE.md >> ~/.claude/CLAUDE.md
```

## Cómo se usa en el día a día

- Las reglas de `CLAUDE.md` actúan solas: Claude las lee en cada sesión.
- Las skills se activan solas cuando la tarea coincide con su descripción,
  o a mano: *"seguí la skill fable-playbook para esto"*.
- `/hasta-que-pase npm test` lanza el loop de verificación con criterio
  explícito.
- Para lo difícil de verdad (arquitectura, bugs resistentes, seguridad),
  agregá `ultrathink` al prompt **y decile en qué pensar más**: casos
  límite, seguridad, rendimiento. Quema más tokens — usalo en lo difícil,
  no en todo.

## Origen

Basado en la serie de @ninodirector (jul 2026) sobre conservar los hábitos
de Fable 5. El contenido de las skills fue escrito por Fable 5 documentando
su propio proceso de razonamiento, en una sesión de Claude Code sobre este
repo.
