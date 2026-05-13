# Paso 6. Integracion sarif en github

## Objetivo de aprendizaje

Este paso introduce la integración SARIF y debe dejar un cambio comprensible en `.github/workflows/sast.yml`.

## Que vas a cambiar y por que

En este paso vas a reforzar `.github/workflows/sast.yml` para que el pipeline no se limite a ejecutar OpenGrep, sino que produzca resultados en un formato que GitHub pueda consumir mejor. SARIF importa porque convierte el análisis estático en hallazgos explotables dentro del ecosistema de revisión, seguridad y seguimiento.

## Archivo y seccion que debes modificar

- Archivo objetivo: `.github/workflows/sast.yml`.
- Aplícalo en la parte del archivo que corresponde al título del paso.
- Si el archivo aún no existe, créalo con este contenido inicial y luego evoluciona desde ahí en los siguientes pasos.

## Cambio base recomendado

Este bloque no es para pegar a ciegas: úsalo como punto de partida y ajústalo al contexto del repositorio.

```yaml
Export SARIF
--sarif
results.sarif
```

## Como adaptarlo correctamente

- Mantén el cambio pequeño y centrado en una sola idea por paso.
- Usa `Export SARIF` como paso legible dentro del workflow y no como comando opaco.
- Haz visible `results.sarif` para que se entienda qué artefacto sale del análisis.
- Evita añadir configuración que no esté relacionada con el objetivo del paso.

## Que deberia verse al terminar

- La intención del cambio se entiende leyendo el archivo.
- El archivo muestra el control sin depender de comentarios ambiguos.
- Los marcadores esperados del paso aparecen de forma natural en la configuración.
- Se entiende que el pipeline ya prepara resultados reutilizables por GitHub y no solo texto en consola.

## Que valida el workflow automaticamente

- `validate-steps.yml` se ejecuta con `push`, `pull_request` y `workflow_dispatch`.
- `scripts/validate-step-06.py` comprueba este paso contra el archivo configurado.
- El workflow busca `Export SARIF` dentro de `.github/workflows/sast.yml`.
- El workflow busca `--sarif` dentro de `.github/workflows/sast.yml`.
- El workflow busca `results.sarif` dentro de `.github/workflows/sast.yml`.

## Criterio de finalizacion

El paso 6 queda completado cuando el workflow de GitHub Actions valida este cambio sin errores.

Siguiente paso: Paso 7.
