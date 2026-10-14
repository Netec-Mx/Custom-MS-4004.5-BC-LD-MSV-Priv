# Laboratorio 2: Construir rúbricas de riesgo a partir de reglas de negocio

**Duración:** 19 min

## Descripción
Los participantes trabajarán con un conjunto ficticio de reglas de negocio relacionadas con el caso. Solicitarán a Copilot identificar y estructurar los criterios necesarios para construir una rúbrica de clasificación de riesgo, definiendo categorías, condiciones de aplicación, niveles o umbrales, excepciones, evidencia requerida y situaciones que necesitan revisión profesional. Posteriormente, proporcionarán distintos escenarios ficticios para probar la rúbrica construida y solicitarán a Copilot proponer ajustes en la estructura sin modificar por iniciativa propia las reglas de negocio originales.

## Pasos para ejecutar la práctica

1. **Construcción de la Rúbrica de Clasificación de Riesgo:**
   * Abre Microsoft 365 Copilot Chat, adjunta el documento `Estrategia_Analisis_Expediente.docx` y envía:
     ```text
     Genera un conjunto de 5 Reglas de Negocio Financieras ficticias para evaluación de crédito corporativo (cobertura de deuda, endeudamiento, liquidez, riesgo sectorial y gobierno corporativo).
     
     Transforma esas reglas en una Rúbrica de Clasificación de Riesgo en formato tabla con las columnas: Criterio_Evaluacion, Umbral_Bajo_Riesgo, Umbral_Riesgo_Medio, Umbral_Alto_Riesgo, Excepciones y Evidencia_Requerida.
     ```

2. **Prueba de escenarios y refinamiento de la rúbrica:**
   * En el mismo chat, envía la siguiente instrucción para evaluar la solidez de la rúbrica:
     ```text
     Somete la rúbrica creada a 2 escenarios de prueba ficticios:
     - Escenario 1: Excelente cobertura de deuda pero alto riesgo sectorial.
     - Escenario 2: Indicadores de liquidez ajustados pero garantías sólidas.
     
     Analiza si existen solapamientos o condiciones ambiguas y propone ajustes en la estructura de la rúbrica sin alterar el espíritu de las reglas originales.
     ```

3. **Exportación de la rúbrica a Word:**
   * Selecciona **Exportar a Word** y guarda el archivo con el nombre exacto: `Rubrica_Riesgo_Financiero.docx`.

## Resultado esperado
Un archivo en Word llamado `Rubrica_Riesgo_Financiero.docx` con los criterios de riesgo calibrados y probados ante escenarios límite.
