# Paso 8. Politica organizativa y reglas prohibidas

## Objetivo de aprendizaje

Este paso introduce el concepto de política organizativa aplicada a reglas prohibidas y debe dejar un cambio comprensible en `rules/security-rules.yml`.

## Que vas a cambiar y por que

En este paso vas a seguir trabajando sobre `rules/security-rules.yml`, pero ya no solo como catálogo técnico. La regla `insecure-eval` puede representar una decisión organizativa: hay patrones que el equipo no quiere permitir porque su coste de riesgo supera cualquier conveniencia local. El objetivo es que la regla se lea como política verificable, no como preferencia informal.

## Archivo y seccion que debes modificar

- Archivo objetivo: `rules/security-rules.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
rules:
  - id: insecure-eval
    message: Prohibe uso de eval por politica de seguridad del repositorio
    severity: ERROR
    pattern: eval($X)
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Haz que `message` refleje la intención de política y no solo la mecánica del patrón.
- Usa `severity: ERROR` cuando quieras expresar que el patrón está directamente prohibido.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- La regla se percibe como una decisión común del repositorio y no como criterio improvisado.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-08.py` comprueba este paso contra el archivo configurado.
- El workflow busca `rules:` dentro de `rules/security-rules.yml`.
- El workflow busca `id: insecure-eval` dentro de `rules/security-rules.yml`.
- El workflow busca `message:` dentro de `rules/security-rules.yml`.
- El workflow busca `severity: ERROR` dentro de `rules/security-rules.yml`.
- El workflow busca `pattern: eval($X)` dentro de `rules/security-rules.yml`.

## Criterio de finalizacion

El paso 8 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 9.
