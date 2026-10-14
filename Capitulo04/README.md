# Laboratorio 4: Gestionar y consolidar evidencia con Copilot Notebooks

**Duración:** 19 min

## Descripción
Los participantes crearán un Copilot Notebook que funcionará como espacio de trabajo para el expediente. Incorporarán progresivamente las reglas y la rúbrica construida, resultados provenientes de diferentes bloques documentales y los hallazgos obtenidos mediante Investigador. Utilizarán el contexto reunido para contrastar información, identificar coincidencias, contradicciones, vacíos de evidencia y aspectos que requieren profundización, conservando la relación entre los hallazgos y los criterios utilizados para evaluarlos. Finalmente, generarán un mapa mental jerárquico.

## Pasos para ejecutar la práctica

1. **Consolidación del Expediente en Copilot Notebooks:**
   * Abre **Copilot Notebooks** (Bloc de notas de Copilot).
   * Adjunta como fuentes de contexto los archivos creados previamente: `Estrategia_Analisis_Expediente.docx`, `Rubrica_Riesgo_Financiero.docx` e `Informe_Investigacion_Sectorial.docx`.
   * En el panel de instrucciones de Notebooks, envía el siguiente prompt:
     ```text
     Sintetiza la información recopilada en los tres documentos vinculados en este Notebook.
     
     Identifica:
     1. Coincidencias entre la rúbrica interna de riesgo y el contexto externo del sector.
     2. Vacíos de evidencia (criterios de la rúbrica que aún no cuentan con datos cualitativos ni cuantitativos).
     3. Posibles contradicciones entre las reglas financieras y las tendencias macroeconómicas.
     ```

2. **Generación del Mapa Mental de Riesgo:**
   * En el mismo Copilot Notebook, envía la siguiente instrucción para representar visualmente las relaciones:
     ```text
     A partir del contexto consolidado del expediente en este Notebook, genera la estructura jerárquica de un Mapa Mental de Evaluación de Riesgo.
     
     Organiza con sangría y viñetas:
     - Nodo Principal: Evaluación de Operación Corporativa 2026
       - Rama 1: Reglas y Rúbricas de Riesgo
       - Rama 2: Factores Externos y Sectoriales (Investigador)
       - Rama 3: Evidencia Disponible vs. Vacíos de Información
       - Rama 4: Aspectos Pendientes de Análisis Cuantitativo
     ```

3. **Exportación de la síntesis del expediente a Word:**
   * Copia o exporta el resultado consolidado del Notebook a un documento de Word con el nombre exacto: `Expediente_Consolidado_Notebook.docx`.

## Resultado esperado
Un documento guardado como `Expediente_Consolidado_Notebook.docx` que unifica las fuentes internas y externas, identifica vacíos de evidencia y proporciona un mapa mental jerárquico de factores de riesgo.
