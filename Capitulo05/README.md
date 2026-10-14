# Laboratorio 5: Analizar evidencia cuantitativa mediante el agente Analista

**Duración:** 15 min

## Descripción
Los participantes utilizarán Analista (Analyst) sobre un conjunto ficticio de información cuantitativa asociado con la operación evaluada, incluyendo evolución de indicadores, exposición por categorías, comportamiento histórico, concentraciones y otras variables relevantes para la evaluación. Solicitarán identificar patrones, variaciones, relaciones entre variables y comportamientos relevantes para los criterios de riesgo definidos previamente, diferenciando entre resultados sustentados directamente por los datos e interpretaciones que requieren evidencia adicional. Posteriormente, incorporarán los hallazgos al expediente.

## Pasos para ejecutar la práctica

1. **Generación del dataset financiero cuantitativo:**
   * Abre Microsoft 365 Copilot Chat y envía el siguiente prompt para crear los datos de la operación:
     ```text
     Genera una tabla de datos cuantitativos ficticios sobre los estados financieros de la empresa a evaluar (años 2023, 2024, 2025).
     
     Incluye columnas: Año, Ratio_Cobertura_Deuda, Nivel_Endeudamiento_Pct, Ratio_Liquidez, Margen_EBITDA_Pct y Exposicion_USD con variaciones que muestren deterioro paulatino de liquidez a pesar del crecimiento en ingresos.
     ```
   * Exporta o guarda la tabla generada en Microsoft Excel con el nombre: `Datos_Cuantitativos_Cliente.xlsx`.

2. **Análisis cuantitativo con el agente Analista:**
   * Activa el agente **Analista (Analyst)** en Microsoft 365 Copilot.
   * Adjunta el archivo `Datos_Cuantitativos_Cliente.xlsx` y envía:
     ```text
     Analiza los indicadores financieros del archivo adjunto Datos_Cuantitativos_Cliente.xlsx.
     
     Identifica:
     1. Patrones de variaciones, tendencias en los ratios y concentraciones de riesgo.
     2. Desglose en dos secciones:
        - HALLAZGOS CUANTITATIVOS SUSTENTADOS (hechos numéricos probados).
        - INTERPRETACIONES Y ALERTAS (comportamientos que amenazan el cumplimiento de los umbrales de riesgo).
     ```

3. **Exportación de los hallazgos cuantitativos:**
   * Al finalizar la respuesta de Copilot, selecciona **Exportar a Word** y guarda el informe con el nombre exacto: `Hallazgos_Cuantitativos_Analista.docx`.

## Resultado esperado
Un libro de Excel llamado `Datos_Cuantitativos_Cliente.xlsx` y un informe guardado como `Hallazgos_Cuantitativos_Analista.docx` que vincula los datos numéricos con alertas explícitas de riesgo.
