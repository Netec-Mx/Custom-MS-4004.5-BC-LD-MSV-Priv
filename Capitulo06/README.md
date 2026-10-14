# Laboratorio 6: Aplicar la rúbrica y sustentar una clasificación de riesgo

**Duración:** 20 min

## Descripción
Utilizando la rúbrica construida y la evidencia consolidada durante el caso, los participantes solicitarán a Copilot evaluar los diferentes criterios y generar una matriz de clasificación trazable. Para cada criterio deberá indicar la clasificación obtenida, regla aplicable, evidencia que la sustenta, fuente de origen, información faltante y aspectos que requieren revisión profesional. Antes de aceptar el resultado, realizarán una revisión final de cobertura y suficiencia de evidencia para consolidar una síntesis ejecutiva.

## Pasos para ejecutar la práctica

1. **Aplicación de la rúbrica y Matriz de Clasificación Trazable:**
   * Abre Microsoft 365 Copilot Chat.
   * Adjunta los archivos creados en el flujo: `Rubrica_Riesgo_Financiero.docx`, `Expediente_Consolidado_Notebook.docx` y `Hallazgos_Cuantitativos_Analista.docx`.
   * Envía el siguiente prompt:
     ```text
     Aplica la Rúbrica de Riesgo sobre toda la evidencia cualitativa y cuantitativa disponible en los archivos adjuntos.
     
     Genera la Matriz de Clasificación de Riesgo en formato tabla con las columnas: Criterio, Nivel_Riesgo_Asignado, Regla_Aplicada, Evidencia_Sustento, Archivo_Origen e Información_Faltante.
     ```

2. **Sintesis ejecutiva y dictamen de riesgo en Word:**
   * En el mismo chat, envía la siguiente instrucción:
     ```text
     Con base en la matriz anterior, redacta la Síntesis Ejecutiva del Dictamen de Riesgo Financiero.
     
     Estructura:
     1. Perfil Global de Riesgo Sugerido (Bajo, Medio, Alto).
     2. Principales Factores Sustentados por Evidencia.
     3. Incertidumbres y Aspectos que Requieren Escalamiento Profesional.
     ```
   * Exporta esta respuesta a un archivo de Word con el nombre exacto: `Dictamen_Final_Riesgo_Financiero.docx`.

3. **Evaluación interactiva mediante prueba de opción múltiple:**
   * En Copilot Chat, envía la siguiente instrucción para realizar la prueba de cierre:
     ```text
     Con base en el archivo Dictamen_Final_Riesgo_Financiero.docx, actúa como el Comité Risk Manager y evalúa mi criterio de decisión.

     Reglas:
     1. Hazme 3 preguntas consecutivas de selección múltiple (A, B, C, D) sobre la trazabilidad de las reglas aplicadas y la suficiencia de la evidencia.
     2. Formula una pregunta a la vez y espera a que yo responda solo indicando la letra de la opción elegida.
     3. Entrega retroalimentación inmediata sobre la respuesta seleccionada antes de continuar con la siguiente pregunta.
     ```

## Resultado esperado
Un documento en Word llamado `Dictamen_Final_Riesgo_Financiero.docx` con la matriz de clasificación trazable y la síntesis del dictamen, junto con la validación de opción múltiple completada en Copilot Chat.
