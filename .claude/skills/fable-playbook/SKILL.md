---
name: fable-playbook
description: Cómo ataco un problema de software de punta a punta — entender, planificar, ejecutar, verificar, reportar. Usar al empezar cualquier tarea no trivial (implementar un feature, arreglar un bug, revisar código) para seguir el método completo en vez de improvisar.
---

# Fable Playbook — cómo ataco un problema

Documentado en primera persona: así razono cuando trabajo bien. Cinco fases,
en orden. Saltear una fase es la causa #1 de trabajo desperdiciado.

## Fase 0 — Entender antes de tocar

- Reformulo el pedido en **una frase**. Si no puedo, no lo entendí.
- Leo el código relevante **antes** de opinar o editar. El repo siempre le
  gana a mi memoria: convenciones, versiones y APIs las saco de acá, no de
  lo que "suelo hacer".
- Si es un bug: lo **reproduzco** primero. Un bug que no puedo reproducir no
  lo puedo arreglar — puedo, como mucho, adivinar.
- Identifico qué es dato verificado y qué es supuesto mío. Los supuestos se
  verifican o se declaran, nunca se ocultan.

### Checklist de salida de Fase 0
- [ ] Puedo decir el pedido en una frase
- [ ] Leí los archivos que voy a tocar
- [ ] Si es bug: lo reproduje y tengo el error real a la vista

## Fase 1 — Planificar

- Escribo un plan corto (5–10 líneas): archivos a tocar, cambio mínimo que
  cumple el pedido, cómo voy a verificar.
- Decido explícitamente **qué NO voy a tocar**. El alcance se define acá,
  no sobre la marcha.
- Elijo el cambio más chico que resuelve el problema de verdad. "Más chico"
  no es "parche": es mínimo *y* correcto.
- Si aparecen dos diseños posibles, elijo uno y anoto por qué en una línea.
  No abro debates conmigo mismo a mitad de la edición.

### Checklist de salida de Fase 1
- [ ] Plan escrito antes del primer edit
- [ ] Sé qué queda fuera del alcance
- [ ] Sé cómo voy a verificar el resultado (comando concreto, no "revisar")

## Fase 2 — Ejecutar

- Cambios chicos y verificables. Si un cambio no se puede verificar solo,
  lo parto.
- Imito el estilo del código que ya existe: nombres, idioma de los
  comentarios, patrones. Mi código no debe delatarse como "de otro autor".
- No agrego dependencias, abstracciones ni configuración "por las dudas".
- Si a mitad de camino descubro que el plan estaba mal, **paro y replanifico**.
  No fuerzo un plan muerto a base de parches.

## Fase 3 — Verificar

- Ejecuto de verdad: tests, build, el flujo afectado. "Debería funcionar"
  no es un estado terminal.
- Verifico el **comportamiento**, no solo que compile: corro el caso que el
  pedido pedía, más un caso límite.
- Si la verificación falla, entro al protocolo de `loop-verificacion`.

## Fase 4 — Reportar

- Abro con el resultado: qué cambió y si funciona, en la primera frase.
- Muestro evidencia (salida del test, comando ejecutado), no adjetivos.
- Digo qué quedó fuera y qué vi que valdría la pena arreglar — sin haberlo
  tocado.
- Antes de enviar, paso por `auto-refutacion`.

## Anti-patrones que me prohíbo

- Editar antes de leer.
- "Arreglar" el test en vez del código (o al revés) sin entender el fallo.
- Declarar éxito sin re-ejecutar la verificación completa.
- Responder con proceso ("primero hice X, después Y...") en vez de resultado.
- Agrandar el alcance porque "ya que estoy".
