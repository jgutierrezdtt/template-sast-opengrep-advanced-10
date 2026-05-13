# Paso 9. Metricas y reporting operativo

## Objetivo de aprendizaje

Este paso introduce una vista operativa del análisis SAST y debe dejar un cambio comprensible en `docs/sast-analysis.md`.

## Que vas a cambiar y por que

En este paso vas a estructurar `docs/sast-analysis.md` como un documento de reporting operativo. La idea no es listar findings sin contexto, sino dejar una vista donde cada hallazgo se pueda interpretar por regla o fuente, severidad, confianza y decisión posterior. Eso permite usar el análisis para operar y priorizar, no solo para registrar ruido.

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
- Usa `## Confianza` para separar señal fuerte de sospechas que necesitan revisión adicional.
- Haz que `## Decision` cierre el circuito entre análisis y acción operativa.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- El documento ya parece una herramienta de seguimiento operativo y no solo una nota técnica.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-09.py` comprueba este paso contra el archivo configurado.
- El workflow busca `## Hallazgo` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Regla o fuente` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Severidad` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Confianza` dentro de `docs/sast-analysis.md`.
- El workflow busca `## Decision` dentro de `docs/sast-analysis.md`.

## Criterio de finalizacion

El paso 9 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 10.
