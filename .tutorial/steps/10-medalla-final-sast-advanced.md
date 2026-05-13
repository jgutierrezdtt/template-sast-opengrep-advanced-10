# Paso 10. Medalla final sast advanced

## Objetivo de aprendizaje

Cerrar el recorrido advanced con una vista final del análisis SAST y dejar un cambio comprensible en `docs/sast-analysis.md`.

## Que vas a cambiar y por que

En este último paso vas a usar `docs/sast-analysis.md` como resumen final del programa avanzado. El documento debe dejar claro qué hallazgos importan, qué regla o fuente los originó, con qué severidad y confianza se interpretan y qué decisión operativa tomó el equipo. Esa estructura funciona como cierre del tutorial y como evidencia de madurez mínima.

## Archivo y seccion que debes modificar

- Archivo objetivo: `docs/sast-analysis.md`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```markdown
## Hallazgo
## Regla o fuente
## Severidad
## Confianza
## Decision
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Haz que `## Decision` conecte el análisis con una acción concreta: corregir, aceptar temporalmente o seguir investigando.
- Usa este paso como cierre del recorrido, no como repetición literal del paso anterior.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento puede leerse como resumen final del nivel advanced alcanzado.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-10.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Regla o fuente` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Severidad` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Confianza` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/sast-analysis.md`.

## Criterio de finalizacion

El paso 10 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Este es el ultimo paso del tutorial.
