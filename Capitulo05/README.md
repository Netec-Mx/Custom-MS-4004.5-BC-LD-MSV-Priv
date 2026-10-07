# Práctica: Utilizar Analista (Analyst) para identificar patrones y variaciones en información cuantitativa ficticia del expediente

## Metadatos
| Variable | Valor |
| :--- | :--- |
| **Duración** | 10 minutos |
| **Complejidad** | Difícil (Hard) |
| **Nivel Bloom** | Analizar (Analyze) |

## Descripción General
En esta práctica de nivel avanzado, aprenderás a interactuar con el agente especializado **Analista (Analyst)** de Microsoft 365 Copilot Premium. El objetivo es procesar y evaluar de manera ágil un expediente financiero cuantitativo estructurado en Microsoft Excel. Utilizarás la capacidad de ejecución de código del agente en un sandbox seguro para calcular métricas de riesgo complejas como el *Altman Z-Score* e identificarás desviaciones críticas en las tendencias de flujo de caja y cartera. Para garantizar el rigor técnico del análisis, guiarás al agente en el diseño de una matriz de validación de evidencia que separe de forma inequívoca las verdades basadas en datos (*hard-data*) de las hipótesis analíticas que requieren investigación complementaria.

## Objetivos de Aprendizaje
Al finalizar esta práctica, serás capaz de:
- [ ] Inicializar e interactuar con el agente especializado **Analista (Analyst)** de Microsoft 365 Copilot en un entorno tabular corporativo.
- [ ] Ejecutar análisis cuantitativos avanzados (variaciones YoY, correlaciones de variables y Altman Z-Score) garantizando la precisión matemática libre de alucinaciones.
- [ ] Identificar patrones de riesgo divergentes como la desalineación de la facturación respecto a la generación real de caja.
- [ ] Estructurar y poblar una matriz de trazabilidad y validación de evidencia para diferenciar hechos contables de interpretaciones preliminares.

## Prerrequisitos
- Comprensión teórica básica del indicador de solvencia *Altman Z-Score* para empresas privadas y análisis de correlación lineal.
- Cuenta corporativa con suscripción activa a **Microsoft 365 Copilot Premium** (Licencia Add-on de Copilot para M365 sobre una base de suite E3 o E5).
- Acceso a Microsoft OneDrive para la Empresa o SharePoint Online asociado a la cuenta.

## Entorno de Laboratorio

### Requisitos de Hardware
- Estación de trabajo con Windows 11 Enterprise (Versión 23H2 o superior) o macOS Sonoma (Versión 14.4 o superior).
- Resolución de pantalla mínima de 1920x1080 píxeles para visualización en pantalla dividida (Excel + Consola de Copilot).
- Conexión a Internet de banda ancha (velocidad mínima de 20 Mbps simétricos de subida y bajada).

### Requisitos de Software y Herramientas

| Aplicación / Servicio | Versión Sugerida | Origen / Enlace Oficial |
| :--- | :--- | :--- |
| Microsoft Edge | Versión 128.0.2739.42 o superior | [Microsoft Edge](https://www.microsoft.com/edge) |
| Microsoft Excel Online | Versión 16.0 (Build 2024) o superior | [Microsoft 365 Portal](https://portal.office.com) |
| Agente Analista (Copilot Analyst) | Service Update 2404 o superior | Integrado en Microsoft 365 Copilot Premium |

### Archivo de Soporte local
El archivo necesario para realizar la práctica debe ubicarse en la siguiente ruta local o ser guardado con la siguiente estructura exacta dentro de tu OneDrive:
*   **Ruta local:** `C:\M365_Copilot_Labs\Datos_Financieros_Expediente.xlsx`

## Instrucciones Paso a Paso

### Paso 1: Inicialización del Entorno y Preparación de los Datos Cuantitativos
**Objetivo:** Asegurar que los datos financieros ficticios del expediente estén correctamente formateados y accesibles para que el agente Analista pueda ejecutar código matemático sobre ellos.

1. Abre tu navegador **Microsoft Edge** e inicia sesión en el portal de Microsoft 365 (`https://portal.office.com`) utilizando tus credenciales organizacionales autorizadas.
2. Abre **Microsoft Excel Online** y crea un nuevo libro de trabajo en blanco o abre un archivo existente guardándolo en tu OneDrive con el nombre de `Datos_Financieros_Expediente.xlsx`.
3. Si estás creando el archivo desde cero, copia y pega la siguiente tabla de datos financieros simulados en la hoja de cálculo (celdas `A1:I5`):

| Año | Ventas | EBIT | Activos_Totales | Capital_Trabajo | Utilidades_Retenidas | Pasivos_Totales | Cuentas_Cobrar | Flujo_Caja_Operativo |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Año 1 | 1000000 | 120000 | 1500000 | 300000 | 450000 | 600000 | 150000 | 110000 |
| Año 2 | 1200000 | 140000 | 1650000 | 310000 | 520000 | 680000 | 220000 | 95000 |
| Año 3 | 1500000 | 165000 | 1900000 | 250000 | 600000 | 850000 | 410000 | 40000 |
| Año 4 | 1900000 | 180000 | 2200000 | 120000 | 680000 | 1200000 | 780000 | -25000 |

4. Selecciona todo el rango de datos (`A1:I5`), presiona la combinación de teclas **`Ctrl + T`** (o selecciona *Insertar > Tabla*), asegúrate de marcar la casilla *"La tabla tiene encabezados"* y haz clic en **Aceptar**.
5. En la pestaña *Diseño de tabla* (Table Design), cambia el nombre de la tabla en el cuadro de texto superior izquierdo a **`Datos_Financieros_Historicos`**. Esto evitará ambigüedades al momento de enviar las instrucciones a Copilot.

*Resultado Esperado:* Una tabla formalizada de Excel con encabezados únicos y formato numérico limpio, sin celdas vacías intermedias, guardada en la nube de Microsoft 365.

*Verificación:* Verifica que en la esquina superior izquierda de la hoja de cálculo se liste el nombre de la tabla como `Datos_Financieros_Historicos`.

---

### Paso 2: Activación del Agente Especializado Analista (Analyst) en Copilot
**Objetivo:** Invocar la interfaz del agente "Analista" en el entorno de Microsoft 365 para iniciar el análisis cuantitativo automatizado.

1. En la parte superior derecha de la ventana de Excel Online, haz clic en el icono verde de **Copilot** para abrir el panel lateral de chat.
2. Si utilizas la versión web consolidada de Copilot (`https://copilot.microsoft.com`), haz clic en la sección de "Agentes" (Agents) en la barra lateral derecha o menú de aplicaciones y selecciona específicamente el agente **Analista (Analyst)**.
3. Asegúrate de que la sesión del chat muestra que estás interactuando con el agente especializado de análisis matemático. En la ventana del panel de Excel, el sistema se conectará directamente a la hoja activa.

*Resultado Esperado:* El panel de Copilot se abre con un mensaje de bienvenida que indica que está listo para analizar y realizar cálculos en el archivo activo.

*Verificación:* Observa que en el cuadro de chat aparezca un indicador como *"Analizando Datos_Financieros_Historicos..."* o un icono representativo de procesamiento analítico/de datos.

---

### Paso 3: Ejecución de Prompt Complejo para Cálculo de Altman Z-Score y Desviaciones
**Objetivo:** Utilizar un prompt avanzado y altamente detallado para calcular el indicador Altman Z-Score mediante código exacto e identificar patrones de divergencia en el flujo de caja.

1. Copia el siguiente prompt estructurado y pégalo en el cuadro de texto del agente Analista de Copilot:

```text
Actúa como un Analista de Riesgo de Crédito Senior con máxima precisión metodológica. Analiza la tabla de datos "Datos_Financieros_Historicos" y realiza las siguientes tareas analíticas:

1. Calcula las siguientes 5 variables para cada uno de los 4 años registrados:
   - X1: Capital_Trabajo / Activos_Totales
   - X2: Utilidades_Retenidas / Activos_Totales
   - X3: EBIT / Activos_Totales
   - X4: Utilidades_Retenidas / Pasivos_Totales (Sustituir por patrimonio neto estimado si corresponde, pero para este ejercicio usa Utilidades_Retenidas / Pasivos_Totales como aproximación de solvencia patrimonial)
   - X5: Ventas / Activos_Totales

2. Aplica la fórmula del Altman Z-Score para empresas privadas: 
   Z = 0.717*(X1) + 0.847*(X2) + 3.107*(X3) + 0.420*(X4) + 0.998*(X5)

3. Determina en qué zona de riesgo se encuentra la empresa para cada año:
   - Zona Segura (Safe): Z > 2.90
   - Zona Gris (Gray): 1.23 <= Z <= 2.90
   - Zona de Peligro (Distress): Z < 1.23

4. Calcula la correlación de Pearson entre la variable 'Ventas' y 'Flujo_Caja_Operativo' a lo largo de los 4 años. Identifica de manera cuantitativa si existe un patrón de divergencia o sobrecalentamiento operativo (es decir, ventas subiendo pero flujo de caja bajando).

Devuelve los resultados en tablas de Markdown claras, detallando la fórmula y los resultados del script ejecutado.
```

2. Haz clic en **Enviar** y espera a que el agente Analista procese la consulta. Verás que Copilot indica que está ejecutando código interno para realizar los cálculos matemáticos sobre la tabla.

*Resultado Esperado:* El agente generará una respuesta detallada con:
- Una tabla de resultados anuales de las variables $X1$ a $X5$.
- El cálculo exacto del Altman Z-Score anualizado, clasificando el Año 1 y 2 en una zona y los Años 3 y 4 en una zona de severo deterioro (Gris o Distress).
- El coeficiente de correlación de Pearson, el cual debe ser negativo debido a la divergencia directa entre el aumento constante de ventas y la caída estrepitosa del flujo de caja.

*Verificación:* 
- Revisa que para el **Año 4** los componentes calculados den un valor de Altman Z de aproximadamente 1.3 - 1.5 (Zona Gris / Distress bajo).
- Confirma que la correlación entre ventas y flujo de caja operativo sea negativa (cercana a $-0.98$), lo que delata un colapso sistémico del capital de trabajo.

---

### Paso 4: Construcción de la Matriz de Triangulación de Evidencia (Hechos vs. Hipótesis)
**Objetivo:** Segmentar el reporte final del agente de manera objetiva para no confundir realidades matemáticas con suposiciones de analista que requieran auditoría física externa.

1. Una vez que el agente te proporcione los cálculos del Paso 3, ingresa el siguiente prompt de refinamiento metodológico en la misma conversación:

```text
Excelente. Ahora, para garantizar el rigor de nuestro expediente de riesgo, construye una Tabla de Validación de Evidencia y Trazabilidad con las siguientes columnas:

1. 'Hallazgo Cuantitativo / Alerta': El comportamiento numérico detectado (ej. deterioro de Z-Score, divergencia ventas/flujo).
2. 'Sustento Matemático Exacto': Cifras y variaciones porcentuales exactas que lo demuestran.
3. 'Estado de Validación': Clasifica estrictamente cada fila como "SUSTENTADO" (si los datos de la tabla lo demuestran plenamente en un 100%) o "HIPÓTESIS" (si es una interpretación lógica que requiere documentos o validaciones externas que no están en este Excel).
4. 'Evidencia Requerida / Plan de Acción': Especifica qué información cualitativa externa (ej. reporte de auditoría de cuentas por cobrar, políticas comerciales, antigüedad de saldos, etc.) necesitamos solicitar al cliente o investigar en el sector para confirmar la sospecha si está marcada como HIPÓTESIS.

Evita cualquier asunción interpretativa no justificada en los datos numéricos y mantén un tono de auditoría técnica.
```

2. Envía el prompt y revisa el esquema tabular generado por Copilot.

*Resultado Esperado:* Una tabla estructurada en formato Markdown que diferencie de manera científica las conclusiones numéricas directas (como la reducción del ratio ácido o el incremento en cuentas por cobrar) de las hipótesis operativas (como la asunción de "clientes morosos" o "problemas de cobranza" que no se pueden probar solo con el balance sin ver la antigüedad de saldos).

| Hallazgo Cuantitativo / Alerta | Sustento Matemático Exacto | Estado de Validación | Evidencia Requerida / Plan de Acción |
| :--- | :--- | :--- | :--- |
| Caída del Z-Score hacia zona de alerta | El valor pasó de un rango seguro en Año 1 a zona gris/distress en Año 4 (reducción de más del 40%). | **SUSTENTADO** | Ninguna, el cálculo matemático directo de balance está completo. |
| Divergencia severa entre Ventas y Flujo Operativo | Correlación de Pearson negativa de ~ -0.98; incremento de ventas del 90% frente a flujo de caja operativo negativo (-$25K) en el Año 4. | **SUSTENTADO** | Ninguna para la correlación; la divergencia matemática es un hecho. |
| Problemas potenciales de cobro o clientes ficticios / sobre-facturación | Las cuentas por cobrar aumentaron en más de 400% (de $150K a $780K) superando ampliamente el crecimiento de ventas. | **HIPÓTESIS** | Solicitar el reporte detallado de antigüedad de saldos (Aging Report) y confirmar la existencia de facturas mediante circularización de clientes. |

*Verificación:* Asegúrate de que el agente haya clasificado la causa del aumento de cuentas por cobrar como una **HIPÓTESIS** y que no lo haya dado por hecho comprobado de forma categórica, lo cual demuestra el éxito de la instrucción restrictiva aplicada.

---

## Validación y Pruebas

Para garantizar la fiabilidad del análisis realizado por el agente, realizaremos una prueba de robustez y resiliencia ante anomalías (Test Adversario).

### Caso de Prueba Adversario: Tratamiento de Datos Incompletos o Erróneos
1. Inserta una nueva fila de datos en tu tabla `Datos_Financieros_Historicos` simulando un "Año 5" con las siguientes celdas:
   - Año: `Año 5`
   - Ventas: `2500000`
   - EBIT: `210000`
   - Activos_Totales: `-500000` (Simulación de error de captura o balance descuadrado extremo con activos negativos)
   - Capital_Trabajo: `100000`
   - Utilidades_Retenidas: `720000`
   - Pasivos_Totales: `1500000`
   - Cuentas_Cobrar: `1100000`
   - Flujo_Caja_Operativo: `30000`
2. En el chat del agente Analista, ingresa el siguiente prompt de auditoría de inconsistencias:

```text
Analiza los datos del Año 5 que acabo de ingresar a la tabla 'Datos_Financieros_Historicos'. ¿Qué advertencia o inconsistencia matemática y de riesgo detectas en las variables ingresadas de este nuevo período? Justifica técnicamente si los cálculos de ratios financieros estándar como el Altman Z-Score siguen siendo metodológicamente válidos bajo estas condiciones.
```

3. El agente debe responder alertando inmediatamente que los **Activos Totales son negativos** (`-500000`), lo cual es una inconsistencia financiera contable grave (los activos no pueden ser negativos en contabilidad real) y que esto invalida o distorsiona por completo las divisiones del Altman Z-Score ($X1, X2, X3, X5$) al generar signos invertidos que falsearían el diagnóstico de quiebra.

*Resultado de Validación Exitoso:* El sistema demuestra resiliencia al no procesar el cálculo a ciegas y alertar de manera proactiva sobre la anomalía del dato financiero de entrada.

---

## Solución de Problemas

A continuación, se listan dos problemas habituales durante el desarrollo del laboratorio y sus correspondientes soluciones:

### Problema 1: El agente Copilot no detecta la tabla en Excel Online o indica "No encuentro datos para procesar".
- **Causa:** El rango de datos no está formateado oficialmente como tabla en Excel, o el archivo no ha terminado de sincronizarse en OneDrive/SharePoint.
- **Solución:** Selecciona el rango completo `A1:I6`, pulsa `Ctrl + T`, confirma la creación de la tabla y escribe el nombre de tabla `Datos_Financieros_Historicos` en la pestaña de diseño. Refresca la ventana de tu navegador Microsoft Edge e inténtalo de nuevo.

### Problema 2: El cálculo matemático del Altman Z-Score arroja valores incomprensibles o errores "NaN" (Not a Number).
- **Causa:** Las columnas numéricas tienen texto incrustado (como letras "USD", signos de dólar escritos manualmente, o comas/puntos de miles desalineados con la configuración regional del navegador).
- **Solución:** Asegúrate de que las celdas contengan únicamente números limpios (ej. `1000000` y no `$1,000,000 USD`). Selecciona las columnas de datos en Excel, haz clic en el formato de número de la barra de inicio y configúralas como *"Número"* o *"General"*.

---

## Limpieza
Una vez finalizada la práctica, realiza las siguientes tareas de mantenimiento del entorno:
1. Elimina la fila de prueba del "Año 5" de tu archivo `Datos_Financieros_Expediente.xlsx` para evitar que interfiera en análisis de módulos posteriores.
2. Guarda los cambios del archivo en tu OneDrive para asegurar la persistencia de las versiones correctas calculadas en el Paso 3.
3. Cierra la pestaña de Excel Online y limpia la memoria caché activa del navegador Microsoft Edge si estás compartiendo una máquina de entrenamiento virtual.

---

## Resumen
En esta práctica de 10 minutos has aprendido a:
- **Operar con el agente especializado Analista (Analyst):** Delegar tareas matemáticas y de programación en un sandbox para realizar operaciones exactas de ratios financieros como el Altman Z-Score.
- **Extraer patrones y correlaciones de riesgo:** Detectar mediante la correlación de Pearson la peligrosa divergencia entre ventas crecientes y un flujo de efectivo decreciente.
- **Rigor analítico:** Desarrollar una matriz de trazabilidad y validación de evidencia, delimitando la frontera entre los datos numéricos indudables (hechos) y las asunciones operativas de cobros (hipótesis) que deben ser validadas en auditorías físicas posteriores.

---

# Práctica: Incorporar los hallazgos cuantitativos al Notebook vinculándolos con los criterios de la rúbrica

## Metadatos

| Métrica | Valor |
| :--- | :--- |
| **Duración** | 5 minutos |
| **Complejidad** | Medio |
| **Nivel de Bloom** | Aplicar |

## Descripción General

En esta práctica, consolidarás la información cualitativa y cuantitativa de un expediente financiero en una sola vista estructurada dentro de **Copilot Notebooks**. Tomarás el resumen numérico y las alertas financieras obtenidas por el agente Analista en el ejercicio anterior y las integrarás formalmente con la rúbrica de riesgos y el dossier cualitativo del cliente. A través de instrucciones de consolidación avanzadas, forzarás a la Inteligencia Artificial a mapear de manera lógica cada métrica financiera con su correspondiente criterio normativo, identificando y documentando activamente cualquier discrepancia entre las declaraciones del cliente y la realidad que reflejan los números.

## Objetivos de Aprendizaje

Al finalizar esta práctica, serás capaz de:
- [ ] Integrar los resultados cuantitativos estructurados por el agente Analista en el Notebook de trabajo unificado.
- [ ] Asociar formalmente cada hallazgo numérico y alerta con un criterio específico de la rúbrica de riesgos.
- [ ] Identificar y documentar discrepancias lógicas entre lo que indican los números y lo reportado en los documentos cualitativos (por ejemplo, discrepancias de ingresos declarados vs. registrados).

## Prerrequisitos

Para realizar esta práctica con éxito, debes cumplir con los siguientes requisitos:
- **Conocimientos teóricos previos**: Comprensión básica de análisis de estados financieros (balances, ratios de apalancamiento, liquidez y Altman Z-Score) y familiaridad con la estructura de un expediente de crédito corporativo.
- **Acceso técnico**:
  - Cuenta organizacional activa con licencia de **Microsoft 365 Copilot Premium** habilitada.
  - Acceso a la interfaz web de Copilot a través de Microsoft Edge.
  - Haber realizado de manera simulada o real el levantamiento de datos del Módulo 4.0 (Estructuración del Notebook) y el análisis cuantitativo del agente Analista (Lab 05-00-01).

## Entorno de Laboratorio

El laboratorio requiere el uso del navegador web en un entorno seguro de estación de trabajo.

### Software y Licencias

| Software / Herramienta | Versión / Edición | Fuente Oficial |
| :--- | :--- | :--- |
| **Sistema Operativo** | Windows 11 Enterprise (Versión 23H2, arquitectura x64) | [ENLACE OFICIAL](https://www.microsoft.com/es-es/evalcenter/evaluate-windows-11-enterprise) |
| **Navegador Web** | Microsoft Edge (Versión 128.0.2739.42, 64-bit) | [ENLACE OFICIAL](https://www.microsoft.com/es-es/edge/business/download) |
| **Licenciamiento IA** | Microsoft 365 Copilot Premium (Actualización de Septiembre de 2024) | [ENLACE OFICIAL](https://www.microsoft.com/es-es/microsoft-365/copilot) |

### Directorios de Trabajo y Archivos

- **Ruta de almacenamiento local predefinida**: `C:\M365_Copilot_Labs`
- **Ruta del directorio de trabajo por defecto (guardado de outputs)**: `C:\Capacitacion-Copilot\Casos-Finanzas\Modulos_1_4\`
- **Archivos requeridos**: Para asegurar la independencia de este laboratorio, los insumos cualitativos y cuantitativos se proporcionan de forma directa en forma de bloques de texto (prompts) durante el procedimiento, evitando dependencias estrictas de archivos locales perdidos de sesiones anteriores.

## Instrucciones Paso a Paso

### Paso 1: Inicializar el entorno de Copilot Notebook y cargar los datos base

**Objetivo**: Cargar en el espacio de trabajo persistente (Copilot Notebook) tanto el dossier cualitativo original de la empresa bajo análisis como la síntesis cuantitativa de alertas financieras generada previamente.

1. Abre **Microsoft Edge** (Versión 128.0.2739.42).
2. Dirígete a la dirección URL oficial de Copilot: [copilot.microsoft.com](https://copilot.microsoft.com) e inicia sesión con tus credenciales de Microsoft 365 asociadas a la licencia Premium.
3. En la interfaz superior de Copilot, selecciona el modo **Notebook**. *(Nota: Si la interfaz muestra la barra lateral de Edge, asegúrate de expandir el navegador a pantalla completa para habilitar la visualización del panel de Notebook, el cual admite hasta 18,000 caracteres de entrada).*
4. Copia el siguiente texto consolidado (que simula el estado de tu Notebook acumulado en las fases previas) y pégalo en el panel izquierdo del **Notebook**:

```text
=========================================
ESTADO DEL DOSSIER: INVERSIONES RETAIL S.A.
=========================================

--- SECCIÓN 1: DECLARACIONES CUALITATIVAS ---
- Declaración de la Gerencia: "La empresa mantiene un perfil de endeudamiento sumamente conservador. Todos los préstamos están concentrados en moneda local (CLP) y el crecimiento operativo proyectado para el cierre de año es del 15% interanual. No se reportan pasivos contingentes significativos ni variaciones materiales en el flujo de caja."
- Gobierno Corporativo: Estructura familiar con controles centralizados.

--- SECCIÓN 2: DATOS CUANTITATIVOS (SÍNTESIS DEL AGENTE ANALISTA) ---
- Margen Operativo (EBIT): Cayó del 12% al 4% en el último ejercicio.
- Deuda Financiera: Incremento del 240% en pasivos de corto plazo, de los cuales el 65% está denominado en USD (moneda extranjera).
- Ciclo de Conversión de Efectivo: Se extendió de 45 días a 98 días, impulsado por un crecimiento desproporcionado del 180% en las Cuentas por Cobrar, mientras las Ventas reales solo aumentaron un 3%.
- Altman Z-Score Calculado: 1.12 (Ubicación: Zona de Peligro / Distress Financiero).

--- SECCIÓN 3: RÚBRICA NORMATIVA DE RIESGOS (CRITERIOS DE CLASIFICACIÓN) ---
- Criterio A (Liquidez): Excelente (>1.5x Acid Test), Moderado (1.0x - 1.5x), Crítico (<1.0x o ciclo de conversión >90 días).
- Criterio B (Apalancamiento): Conservador (<30% deuda total/activos), Moderado (30% - 60%), Crítico (>60% o alta exposición cambiaria sin cobertura).
- Criterio C (Gobernanza y Transparencia): Confiable (auditoría sin salvedades y revelación completa), Alerta (centralización de decisiones o falta de consistencia documental).
```

**Resultado Esperado**: El cuadro de entrada del Copilot Notebook debe mostrar claramente el texto de entrada estructurado listo para ser procesado por las instrucciones del modelo.

**Verificación**: Confirma visualmente que todo el texto de los bloques de entrada se encuentra en el editor del panel izquierdo sin truncamientos de caracteres.

---

### Paso 2: Ejecutar la instrucción de consolidación, mapeo a rúbrica y detección de inconsistencias

**Objetivo**: Utilizar una instrucción avanzada estructurada para que Copilot realice una conciliación cuali-cuantitativa, asocie las métricas financieras crudas con los criterios de la rúbrica y señale contradicciones directas entre los hechos cuantitativos y la declaración de la gerencia.

1. Sitúate al final del panel izquierdo de entrada del Notebook (o en el cuadro de prompts de ejecución adjunto al Notebook) y añade las siguientes instrucciones precisas para el modelo:

```text
Instrucción de Consolidación y Auditoría:
Actúa como un Analista de Riesgo de Crédito Senior y Auditor Forense. Analiza minuciosamente los datos cualitativos, cuantitativos y la rúbrica provista arriba, y genera un reporte estructurado que incluya obligatoriamente las siguientes secciones:

1. MATRIZ DE ASOCIACIÓN DE RIESGOS:
   - Construye una tabla en formato Markdown con las columnas: | Criterio de la Rúbrica | Métrica Cuantitativa Asociada | Nivel de Riesgo Resultante | Justificación Técnica basada en Datos |
   - Mapea de forma directa cada uno de los tres criterios normativos (Liquidez, Apalancamiento, Gobernanza) con la métrica cuantitativa correspondiente calculada por el Analista.

2. PANEL DE CONTRADICCIONES Y DISCREPANCIAS (CUALI-CUANTI):
   - Identifica y contrasta de manera explícita las discrepancias lógicas entre las declaraciones de la gerencia (Sección 1) y las métricas numéricas reales (Sección 2).
   - Para cada discrepancia encontrada, señala el impacto potencial en el análisis de riesgo.

3. RECOMENDACIÓN TÉCNICA DE VERIFICACIÓN (AUDITORÍA):
   - Define qué documentos específicos del expediente físico/digital debemos requerir de inmediato al cliente para aclarar cada una de las contradicciones identificadas.
```

2. Haz clic en el botón **Submit** / **Enviar** (o presiona el botón de ejecución de Copilot Notebook).

**Resultado Esperado**: Copilot generará una respuesta altamente estructurada en el panel derecho de la interfaz. Deberá mostrar una tabla Markdown completa donde el Criterio de Liquidez se categorice como "Crítico" (debido al ciclo de 98 días), el Apalancamiento como "Crítico" (por la exposición al tipo de cambio en USD del 65%) y la Gobernanza en "Alerta" por discrepancia documental. Además, listará de manera detallada al menos dos contradicciones clave (deuda en USD vs declaración de moneda local, y crecimiento de ventas de solo 3% vs proyección gerencial del 15%).

**Verificación**:
- Verifica que el resultado contenga una tabla estructurada con las 4 columnas solicitadas.
- Confirma que la sección de discrepancias identifique la incoherencia monetaria (deuda en USD vs pesos) y la de crecimiento (15% proyectado vs 3% real sustentado por cuentas por cobrar acumuladas).

---

## Validación y Pruebas

Para garantizar el cumplimiento riguroso de los objetivos de la práctica y poner a prueba los límites de análisis de la IA, realizaremos una prueba de estrés analítica (caso adverso/contradictorio).

### Caso de Prueba Adversario: Modificación de Datos de Control

Para evaluar la capacidad de Copilot de no alucinar y mantener una supervisión humana crítica sobre discrepancias ocultas:

1. Modifica la Sección 2 (Datos Cuantitativos) dentro del panel de entrada del Notebook con la siguiente línea contradictoria intencional:
   - *Cambia*: "Ventas reales solo aumentaron un 3%" por "Ventas reales crecieron un 25% anual en el último mes".
   - *Mantén*: "Ciclo de Conversión de Efectivo se extendió de 45 días a 98 días, impulsado por un crecimiento desproporcionado del 180% en las Cuentas por Cobrar".
2. Ejecuta el prompt de consolidación nuevamente.
3. **Análisis de Validación**: Comprueba si Copilot detecta una nueva inconsistencia interna en los datos cuantitativos: *Es financieramente improbable/anómalo que un incremento de ventas reales del 25% requiera un incremento de cuentas por cobrar del 180% con una degradación tan drástica del flujo de caja, a menos que se estén registrando ventas ficticias o que la calidad del crédito otorgado sea extremadamente deficiente.*
4. Si Copilot asume el incremento del 25% de ventas como "favorable" sin cuestionar la relación con el incremento del 180% en cuentas por cobrar, tú como analista humano debes intervenir y redactar la siguiente nota de control:
   > *"Nota de Supervisión Humana: Se detecta una alerta de fraude/calidad de cartera debido al desfase de crecimiento entre ingresos nominales y cuentas por cobrar (relación de 1 a 7.2x)."*

## Solución de Problemas

A continuación se presentan los dos problemas más comunes que pueden ocurrir durante la ejecución de esta práctica en Copilot Notebooks:

### Problema 1: El panel de entrada de Copilot Notebook borra la información o muestra un error de límite de longitud de caracteres
- **Sintomatología**: Al pegar la información unificada, la interfaz de Copilot falla o recorta el texto a la mitad, imposibilitando la lectura de la rúbrica.
- **Causa raíz**: Se está utilizando la interfaz de chat estándar de Copilot (límite de 4,000 caracteres) en lugar de la vista específica **Notebook** de `copilot.microsoft.com` (que expande el límite a 18,000 caracteres), o el navegador ha acumulado demasiada memoria en caché afectando los scripts de React del portal.
- **Solución**:
  1. Asegúrate de que estás en la pantalla de inicio de Copilot y haz clic explícitamente en la pestaña de la barra superior que dice **"Notebook"**.
  2. Si el problema persiste, presiona `Ctrl + F5` en Microsoft Edge para forzar una recarga limpia de la caché del portal e intenta pegar el bloque de texto nuevamente.

### Problema 2: Copilot genera clasificaciones de riesgo inconsistentes con los rangos definidos en la rúbrica
- **Sintomatología**: El reporte clasifica el "Criterio A" (Liquidez con ciclo de 98 días) como "Moderado" cuando la rúbrica estipula claramente que cualquier valor superior a 90 días debe clasificarse como "Crítico".
- **Causa raíz**: Pérdida de atención contextual de la IA debido a una baja densidad de restricciones en la instrucción, permitiendo que el modelo aplique criterios generales de finanzas en lugar de los parámetros restrictivos de la rúbrica ingresada.
- **Solución**: Refuerza la instrucción de mapeo agregando la siguiente regla de cumplimiento estricto al final del prompt de consolidación:
  > *"Restricción de Cumplimiento Normativo Absoluto: No utilices criterios externos de la industria para definir los niveles de riesgo. Debes ceñirte exclusivamente a los umbrales numéricos de la Sección 3 (Rúbrica). Si el Ciclo de Conversión de Efectivo es de 98 días, debes catalogarlo forzosamente como Crítico."*

## Limpieza

Para resguardar los datos del ejercicio y mantener ordenada la estación de trabajo local:

1. Selecciona todo el contenido generado en el panel de resultados de Copilot.
2. Abre un editor de texto plano (como el Bloc de notas) o VS Code, pega el resultado estructurado y guárdalo en la ruta de trabajo local:
   `C:\Capacitacion-Copilot\Casos-Finanzas\Modulos_1_4\Matriz_Riesgo_Consolidada.md`
3. Haz clic en el botón de papelera o **"Limpiar conversación"** (icono de escoba/nuevo tema) en la interfaz de Copilot para borrar los datos temporales del espacio de trabajo del modelo en la nube y asegurar que no queden remanentes en la sesión del navegador.

## Resumen

En esta práctica has consolidado de manera lógica y rigurosa datos cualitativos y cuantitativos utilizando las capacidades avanzadas de **Copilot Notebooks**. A diferencia de una simple síntesis automatizada, has forzado al modelo a:
1. Actuar como un analista de riesgos estructurado que vincula números concretos con una rúbrica regulatoria preestablecida.
2. Identificar discrepancias de información críticas, lo que expone contradicciones estratégicas en la carpeta de crédito del cliente (tales como deuda oculta en moneda extranjera y proyecciones de crecimiento inconsistentes).
3. Asegurar la trazabilidad y la necesidad de supervisión humana frente a la conciliación de evidencias cruzadas.
