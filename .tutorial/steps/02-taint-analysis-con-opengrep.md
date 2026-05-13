# Paso 2. Taint analysis con opengrep

## Objetivo de aprendizaje

Este paso introduce el razonamiento de taint analysis y debe dejar un cambio comprensible en `rules/security-rules.yml`.

## Que vas a cambiar y por que

En este paso sigues trabajando sobre `rules/security-rules.yml`, pero con una lectura más avanzada: no basta con detectar una llamada peligrosa, también importa pensar cómo llega el dato hasta ese sink. Aunque el validador siga comprobando la misma regla base, el aprendizaje aquí es interpretar `eval($X)` como un punto de llegada de datos potencialmente contaminados.

## Archivo y seccion que debes modificar

- Archivo objetivo: `rules/security-rules.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
rules:
  - id: insecure-eval
    message: Detecta uso inseguro de eval con entrada controlable
    severity: ERROR
    pattern: eval($X)
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `message` para reflejar que el problema no es solo `eval`, sino el flujo de datos que puede alcanzarlo.
- Piensa esta regla como punto de partida para evolucionar luego a fuentes, sanitización y sinks más precisos.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- La regla ya sugiere una lectura de flujo de datos y no solo una coincidencia textual aislada.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-02.py` comprueba este paso contra el archivo configurado.
- El workflow busca `rules:` dentro de `rules/security-rules.yml`.
- El workflow busca `id: insecure-eval` dentro de `rules/security-rules.yml`.
- El workflow busca `message:` dentro de `rules/security-rules.yml`.
- El workflow busca `severity: ERROR` dentro de `rules/security-rules.yml`.
- El workflow busca `pattern: eval($X)` dentro de `rules/security-rules.yml`.

## Criterio de finalizacion

El paso 2 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 3.
