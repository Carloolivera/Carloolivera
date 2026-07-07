---
name: auto-refutacion
description: Checklist para refutar mi propia respuesta antes de entregarla — encontrar el caso que la rompe, el supuesto no verificado o la API inventada, y corregir antes de responder. Usar siempre antes de dar por terminada una tarea o respuesta técnica.
---

# Auto-refutación — atacá tu respuesta antes de entregarla

El objetivo no es "revisar por arriba": es intentar **demolerla** como lo
haría el revisor más duro. Si la respuesta sobrevive, se entrega. Si no,
se corrige primero — el usuario nunca ve la versión rota.

## El ataque, en orden

### 1. ¿Respondí la pregunta que me hicieron?
Releé el pedido original, no tu memoria del pedido. Es el error más común:
responder la pregunta que quería responder en vez de la que hicieron.

### 2. ¿Qué input rompe esto?
Buscá activamente el contraejemplo:
- vacío / null / undefined / lista de cero elementos
- duplicados, unicode, strings larguísimos
- concurrencia: ¿dos requests a la vez? ¿doble click?
- permisos: ¿qué pasa si lo llama alguien sin rol?
- timezone, límites de fecha, off-by-one
- el estado "sucio": datos viejos que no cumplen el formato nuevo

### 3. ¿Verifiqué o asumí?
- ¿Ejecuté el código o "debería funcionar"?
- ¿Esa API/función/flag existe **en este repo y esta versión**, o la estoy
  recordando de otro contexto? Si no la vi en el código o en la doc, es
  inventada hasta que se demuestre lo contrario.
- ¿El número/dato que estoy afirmando salió de una fuente o de mi intuición?

### 4. ¿Me contradice el propio repo?
¿Hay un test, un comentario, una migración o un uso existente que contradiga
mi cambio? Buscarlo cuesta un grep; no buscarlo cuesta un bug.

### 5. ¿Qué rompí sin mirar?
¿Quién más llama a lo que toqué? Los otros call sites del símbolo editado
se revisan, no se presumen compatibles.

### 6. ¿Estoy exagerando el resultado?
Nada de "todo funciona" si corrí un solo caso. El reporte dice exactamente
qué se verificó y qué no.

## Regla de cierre

Si el ataque encontró algo: **se corrige y se vuelve a atacar**. Refutar y
entregar la versión refutada con una disculpa no cuenta como refutar.

Si el ataque no encontró nada después de un intento honesto: entregá. La
auto-refutación es una pasada seria, no un loop de ansiedad infinito.
