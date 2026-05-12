# SAST OpenGrep Advanced 10

Tutorial avanzado y compacto de análisis estático con OpenGrep en 10 pasos clave.

## Objetivo

Aplicar un conjunto seleccionado de prácticas avanzadas de SAST con OpenGrep: reglas custom complejas, gestión de falsos positivos, excepciones con criterio, integración en pipeline y reporting operativo.

## Audiencia

Equipos de AppSec y DevSecOps con experiencia previa en análisis estático que quieran consolidar prácticas avanzadas en formato compacto.

## Requisitos previos

- Haber completado el tutorial SAST OpenGrep Professional o tener experiencia equivalente.
- Conocimientos sólidos de GitHub Actions.
- Experiencia operando reglas de análisis estático.

## Herramientas utilizadas

- OpenGrep
- GitHub Actions
- SARIF
- Scripts de validación del curso

## Inicio del tutorial

[Empezar tutorial](https://github.com/new?template_name=template-sast-opengrep-advanced-10&template_owner=jgutierrezdtt)

## Acceso al repositorio

- [Crear mi repositorio desde este template](https://github.com/new?template_name=template-sast-opengrep-advanced-10&template_owner=jgutierrezdtt)
- [Volver al portal general](https://github.com/jgutierrezdtt/security-learning-portal)

## Gestión del progreso

- [Validar progreso](../../actions/workflows/validate.yml)
- [Probar integridad del tutorial](../../actions/workflows/test-tutorial.yml)
- [Ejecutar tests funcionales del tutorial](../../actions/workflows/functional-tests.yml)
- [Reiniciar tutorial](../../actions/workflows/reset-tutorial.yml)
- [Ver pasos del tutorial](./.tutorial/steps/)

## Arquitectura del laboratorio

El laboratorio condensa los 10 controles avanzados más relevantes de OpenGrep en un flujo operativo completo, desde reglas complejas hasta integración real en pipeline CI/CD con quality gates y reporting.

## Tabla de pasos

| Paso | Tema |
| --- | --- |
| 0 | Introducción |
| 1 | Reglas avanzadas con patrones complejos |
| 2 | Taint analysis con OpenGrep |
| 3 | Reglas multi-archivo |
| 4 | Gestión avanzada de falsos positivos |
| 5 | Excepciones con criterio y trazabilidad |
| 6 | Integración SARIF en GitHub |
| 7 | Quality gate bloqueante por criticidad |
| 8 | Política organizativa y reglas prohibidas |
| 9 | Métricas y reporting operativo |
| 10 | Medalla final SAST Advanced |

## Paso 0

El paso 0 describe el entorno, permisos y limitaciones del laboratorio. No bloquea el flujo: el botón principal abre directamente el paso 1.

## Actualización desde template

Este repositorio incluye `.template-version` y workflow de actualización para revisar cambios del template sin sobrescribir trabajo del usuario.

## Badge final

Al cerrar el curso se generan artefactos de finalización en:

- `.tutorial/badges/completion-badge.md`
- `.tutorial/badges/completion-badge.svg`
- `.tutorial/evidence/completion.json`

## Referencias

- [OpenGrep](https://github.com/opengrep/opengrep)
- [GitHub Actions](https://docs.github.com/actions)
- [SARIF](https://sarifweb.azurewebsites.net/)
