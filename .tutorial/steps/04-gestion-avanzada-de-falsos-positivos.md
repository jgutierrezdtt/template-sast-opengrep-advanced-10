# Paso 4. Gestion avanzada de falsos positivos

## Objetivo de aprendizaje

Este paso introduce un criterio avanzado para tratar falsos positivos y debe dejar un cambio comprensible en `rules/security-rules.yml`.

## Que vas a cambiar y por que

En este paso vas a usar `rules/security-rules.yml` para mostrar que gestionar falsos positivos no significa borrar reglas a la primera señal de ruido. Una parte importante del trabajo avanzado consiste en ajustar severidad y criterio para mantener visibilidad sin bloquear innecesariamente al equipo.

## Archivo y seccion que debes modificar

- Archivo objetivo: `rules/security-rules.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
rules:
  - id: demo-rule
    severity: WARNING
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `WARNING` cuando la señal siga siendo útil pero no deba romper el flujo por sí sola.
- No conviertas todos los casos dudosos en `WARNING`; el objetivo es afinar la señal, no diluirla.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende que la severidad también es una herramienta de gestión del ruido.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-04.py` comprueba este paso contra el archivo configurado.
- El workflow busca `rules:` dentro de `rules/security-rules.yml`.
- El workflow busca `id: demo-rule` dentro de `rules/security-rules.yml`.
- El workflow busca `severity: WARNING` dentro de `rules/security-rules.yml`.

## Criterio de finalizacion

El paso 4 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 5.
