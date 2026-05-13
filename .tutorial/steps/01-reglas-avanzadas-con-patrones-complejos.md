# Paso 1. Reglas avanzadas con patrones complejos

## Objetivo de aprendizaje

Este paso introduce la base de una regla avanzada de SAST y debe dejar un cambio comprensible en `rules/security-rules.yml`.

## Que vas a cambiar y por que

En este paso vas a definir una regla propia en `rules/security-rules.yml`. Aunque el patrón inicial sea compacto, la enseñanza aquí es importante: una regla avanzada no empieza por ser compleja, sino por tener una intención clara, un identificador estable, una severidad coherente y un mensaje útil para quien la recibe.

## Archivo y seccion que debes modificar

- Archivo objetivo: `rules/security-rules.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
rules:
  - id: insecure-eval
    message: Detecta uso inseguro de eval
    severity: ERROR
    pattern: eval($X)
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa un `id` estable y legible porque luego te servirá para triage y excepciones.
- Haz que `message` explique el problema sin obligar a leer la regla completa.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- La regla ya parece utilizable en un repositorio real y no solo en una demo abstracta.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-01.py` comprueba este paso contra el archivo configurado.
- El workflow busca `rules:` dentro de `rules/security-rules.yml`.
- El workflow busca `id: insecure-eval` dentro de `rules/security-rules.yml`.
- El workflow busca `message:` dentro de `rules/security-rules.yml`.
- El workflow busca `severity: ERROR` dentro de `rules/security-rules.yml`.
- El workflow busca `pattern: eval($X)` dentro de `rules/security-rules.yml`.

## Criterio de finalizacion

El paso 1 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 2.
