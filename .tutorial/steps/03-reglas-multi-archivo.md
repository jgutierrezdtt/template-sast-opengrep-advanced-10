# Paso 3. Reglas multi archivo

## Objetivo de aprendizaje

Este paso introduce la idea de reglas multi archivo y debe dejar un cambio comprensible en `rules/security-rules.yml`.

## Que vas a cambiar y por que

En este paso sigues trabajando sobre `rules/security-rules.yml`, pero ahora con una mirada más amplia: muchos problemas reales no se entienden aislando una línea, sino enlazando cómo un dato nace en un archivo y termina ejecutándose en otro. Aunque el validador siga usando la misma regla base, el objetivo didáctico es que leas `eval($X)` como un sink útil dentro de una historia distribuida entre varios ficheros.

## Archivo y seccion que debes modificar

- Archivo objetivo: `rules/security-rules.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
rules:
  - id: insecure-eval
    message: Detecta sink eval que puede recibir datos desde otros archivos
    severity: ERROR
    pattern: eval($X)
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Redacta `message` pensando en un caso donde la fuente y el sink no estén juntos.
- Usa esta regla como base conceptual para evolucionar después hacia contexto interprocedimental o entre módulos.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- La regla ya sugiere que el análisis puede cruzar límites de archivo y no solo coincidencias locales.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-03.py` comprueba este paso contra el archivo configurado.
- El workflow busca `rules:` dentro de `rules/security-rules.yml`.
- El workflow busca `id: insecure-eval` dentro de `rules/security-rules.yml`.
- El workflow busca `message:` dentro de `rules/security-rules.yml`.
- El workflow busca `severity: ERROR` dentro de `rules/security-rules.yml`.
- El workflow busca `pattern: eval($X)` dentro de `rules/security-rules.yml`.

## Criterio de finalizacion

El paso 3 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 4.
