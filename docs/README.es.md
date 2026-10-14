# Adversarial Engineering Skills

**Cuestiona el plan. Revisa los cambios. Demuestra el resultado.**

[English](../README.md) · Español · [Todos los idiomas](../README.md)

Una habilidad de gestión de ingeniería para agentes de programación, basada en tres controles de calidad con evidencia. Quien revisa debe identificar una ruta de fallo concreta; el agente principal debe corregir el problema o justificar su rechazo con pruebas.

## Tres controles

1. **Plan**: antes de una implementación sustancial, revisar restricciones, contratos de API y datos, permisos, estados, consumidores omitidos y complejidad innecesaria.
2. **Cambios**: después de cada bloque coherente y antes de fusionarlo, revisar el diff real y el comportamiento afectado. Añadir una revisión de seguridad cuando corresponda.
3. **Aceptación**: antes de declarar el trabajo terminado, respaldar las afirmaciones con resultados actuales de ejecución o inspección de los entregables, indicando lo que no se comprobó.

Los cambios pequeños requieren comprobaciones pequeñas; los de alto riesgo, perspectivas independientes y bloques verificables. La autorrevisión se identifica como tal y no sustituye una revisión independiente obligatoria. Los bloqueos sin resolver impiden aprobar el control. La habilidad no autoriza despliegues ni publicaciones.

## Instalación

Con Git y Node.js/npm disponibles, ejecuta desde el proyecto de destino:

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering
```

Elige los agentes de forma interactiva o añade `-a claude-code`, `-a codex` o `-a cursor`. Usa `--copy` para evitar enlaces simbólicos y `-g` para instalar a nivel de usuario. Consulta la [guía de instalación](INSTALL.md) para otros agentes, instalación manual y desinstalación. La compatibilidad depende de la lista actual de Skills CLI; no implica pruebas de funcionamiento en todos los agentes.

## Uso

> Usa adversarial-engineering para este cambio. Cuestiona el plan antes de implementar, revisa el diff y verifica los criterios de aceptación antes de declarar la finalización. Indica cómo se resolvió cada hallazgo, la evidencia y los límites de la verificación.

Para una revisión sin cambios, añade «No modifiques archivos». Revisa de nuevo los hallazgos afectados por las correcciones; no repitas comprobaciones cuya evidencia siga siendo válida. Nuevos ciclos requieren nueva evidencia o una corrección sustancial.

El [SKILL.md en inglés](../skills/adversarial-engineering/SKILL.md) es la referencia normativa. Esta página es una introducción localizada. No es una garantía de ausencia de defectos ni un control automático de CI. Véanse [validación](VALIDATION.md), [contribuciones](../CONTRIBUTING.md) y [licencia MIT](../LICENSE). Se agradecen revisiones de hablantes nativos.
