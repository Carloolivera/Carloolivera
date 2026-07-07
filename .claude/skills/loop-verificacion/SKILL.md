---
name: loop-verificacion
description: Protocolo para iterar hasta que algo pase — tests, build, un flujo — sin detenerse al primer intento y sin entrar en espiral. Usar cuando el pedido implique "que funcione", "que pase", "arreglalo hasta que ande" o cuando una verificación de Fase 3 falla.
---

# Loop de verificación — repetí hasta que pase

La mitad de la ventaja de un buen agente es que no se detiene al primer
intento. La otra mitad es que no itera a ciegas. Este protocolo cubre las dos.

## Paso 0 — Definí "pasa" ANTES de iterar

Un criterio objetivo y ejecutable, escrito antes del primer intento:

> "Pasa" = `npm test` verde + `npm run build` sin errores
> "Pasa" = el endpoint devuelve 200 con el body esperado para el caso X

Sin criterio definido, el loop no tiene salida y "ya está" se decide por
cansancio. Eso está prohibido.

## El loop

```
1. EJECUTAR la verificación completa
2. LEER el error real — el mensaje literal, el stack trace, la línea.
   Nunca adivinar desde el síntoma.
3. UNA hipótesis — la más probable, escrita en una frase:
   "falla porque X"
4. FIX mínimo que ataca esa hipótesis (no tres cambios a la vez:
   si tocás tres cosas y pasa, no sabés cuál era)
5. VOLVER a 1 — la verificación COMPLETA, no solo el caso que fallaba
```

## Reglas anti-espiral

- **Dos intentos sin mover el error ⇒ frená y re-diagnosticá.** El problema
  ya no es el fix: es la hipótesis. Volvé a leer el código y el error desde
  cero; buscá qué supuesto de base está mal.
- **Nunca "arregles" borrando la señal**: comentar el test, bajar el linter,
  atrapar la excepción y seguir — eso es esconder el fallo, no pasarlo.
- **Cada iteración deja rastro**: qué hipótesis probé y qué pasó, en una
  línea. Repetir una hipótesis ya quemada es la definición de espiral.
- **Éxito = la verificación completa re-ejecutada en verde.** Arreglar el
  caso que fallaba y declarar victoria sin re-correr todo no cuenta: los
  fixes rompen cosas.
- **Tope honesto**: si tras varias rondas el diagnóstico apunta a algo fuera
  del alcance (un bug de la plataforma, un pedido ambiguo, credenciales que
  no tengo), se reporta el diagnóstico y dónde estoy trabado — con evidencia —
  en vez de seguir quemando intentos o declarar un éxito falso.

## Al salir del loop

Reportá: criterio usado, cuántas iteraciones, qué era la causa raíz, y la
salida de la verificación final en verde. Abrí con el resultado.
