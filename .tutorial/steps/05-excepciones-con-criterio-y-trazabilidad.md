# Paso 5. Excepciones con criterio y trazabilidad

## Objetivo de aprendizaje

Este paso introduce un registro serio de excepciones y debe dejar un cambio comprensible en `docs/sast-exceptions.yml`.

## Que vas a cambiar y por que

En este paso vas a definir `docs/sast-exceptions.yml` para que una excepción no sea un simple bypass del hallazgo. El objetivo es dejar claro qué regla se exceptúa, en qué ruta, por qué motivo, quién se hace responsable y hasta cuándo sigue siendo aceptable.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/sast-exceptions.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
exceptions:
  - rule_id: insecure-eval
    path: src/legacy/unsafe.js
    reason: "Caso legado pendiente de refactorización controlada"
    owner: "team-appsec"
    expires_on: "2026-12-31"
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `reason` para justificar la aceptación de riesgo, no para repetir el nombre de la regla.
- Añade `owner` y `expires_on` desde el inicio para que la excepción nazca con seguimiento.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- La excepción se entiende como deuda controlada y no como desactivación indefinida.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-05.py` comprueba este paso contra el archivo configurado.
- El workflow busca `exceptions:` dentro de `docs/sast-exceptions.yml`.
- El workflow busca `rule_id:` dentro de `docs/sast-exceptions.yml`.
- El workflow busca `path:` dentro de `docs/sast-exceptions.yml`.
- El workflow busca `reason:` dentro de `docs/sast-exceptions.yml`.
- El workflow busca `owner:` dentro de `docs/sast-exceptions.yml`.
- El workflow busca `expires_on:` dentro de `docs/sast-exceptions.yml`.

## Criterio de finalizacion

El paso 5 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 6.
