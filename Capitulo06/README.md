# Práctica: Evaluar el expediente con la rúbrica y generar una matriz de clasificación trazable con Copilot

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 10 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel de Taxonomía de Bloom** | Analizar (Analyze) |

## Descripción General

En este laboratorio práctico de consolidación final, utilizarás la interfaz avanzada de **Copilot Notebook** para contrastar la evidencia cualitativa y cuantitativa de un expediente financiero frente a una rúbrica corporativa de riesgo. El objetivo es estructurar un análisis de alta precisión metodológica sin depender de archivos locales externos propensos a fallos de sincronización. Mediante un prompt avanzado de evaluación estructurada, generarás una matriz de clasificación multidimensional que asocie criterios de riesgo, reglas de negocio, hallazgos, fuentes de información y brechas críticas de datos. Finalmente, redactarás un resumen ejecutivo diseñado para preservar el control de la decisión final bajo el criterio exclusivo del analista humano.

## Objetivos de Aprendizaje

Al finalizar este laboratorio, serás capaz de:
- [ ] Aplicar una rúbrica de riesgo parametrizada sobre evidencia consolidada utilizando la interfaz de **Copilot Notebook**.
- [ ] Construir una matriz de clasificación de riesgo multidimensional con trazabilidad estricta (Grounding) y mapeo de fuentes.
- [ ] Identificar de forma proactiva brechas de información (Gaps) y puntos de atención críticos que requieran la intervención del juicio profesional humano.
- [ ] Formular un resumen ejecutivo que diferencie hechos cuantificables de áreas grises sujetas a interpretación subjetiva.

## Prerrequisitos

Para completar este laboratorio con éxito, necesitas:
- **Conocimientos teóricos:** Comprensión de conceptos de análisis de riesgo de crédito (ratios de liquidez, apalancamiento, gobernanza corporativa) y fundamentos de ingeniería de prompts (anclaje de datos, delimitación de contexto y definición de roles).
- **Acceso técnico:** Una cuenta de usuario activa con la suscripción de **Microsoft 365 Copilot Premium** habilitada y acceso sin restricciones a la web de Copilot corporativa (`copilot.microsoft.com`).

## Entorno de Laboratorio

Este laboratorio se ejecuta en un navegador web compatible utilizando la funcionalidad integrada de Copilot Notebook.

### Especificaciones de Software y Herramientas

| Componente | Versión / Edición | Fuente Oficial de Descarga / Acceso |
| :--- | :--- | :--- |
| **Sistema Operativo** | Windows 11 Enterprise (Versión 23H2 o superior) | [Licenciamiento por Volumen de Microsoft](https://www.microsoft.com/es-es/licensing) |
| **Navegador Web** | Microsoft Edge (Versión 128.0.2739.42 o superior, 64 bits) | [Descarga Oficial de Edge](https://www.microsoft.com/es-es/edge/download) |
| **Licencia de IA** | Microsoft 365 Copilot Premium (Actualización de Septiembre de 2024) | [Portal de Administración de Microsoft 365](https://admin.microsoft.com) |
| **Interfaz de Trabajo** | Copilot Notebooks (Modo Expandido en Navegador) | Acceso directo vía [Copilot Web](https://copilot.microsoft.com) |

### Requisitos de Hardware mínimos
- **Resolución de pantalla:** Mínima de 1920x1080 píxeles para visualización óptima del panel dividido.
- **Conexión a Internet:** Banda ancha (mínimo 10 Mbps simétricos) con acceso libre a dominios de Microsoft (`*.microsoft.com`, `*.copilot.microsoft.com`).

---

## Instrucciones Paso a Paso

### Paso 1: Configurar el Copilot Notebook con el Expediente y la Rúbrica

**Objetivo:** Cargar los datos sintéticos del expediente de "XYZ Corp" y los parámetros de la rúbrica de riesgo directamente en la interfaz de Copilot Notebook para su análisis consolidado.

1. Abre tu navegador web **Microsoft Edge (128.0.2739.42)**.
2. Navega al portal oficial de Copilot corporativo: [https://copilot.microsoft.com](https://copilot.microsoft.com). Asegúrate de iniciar sesión con tu cuenta organizativa válida (debe mostrar el escudo de protección de datos empresariales en la esquina superior derecha).
3. En la barra superior de la interfaz de Copilot, haz clic en la pestaña **Notebook** (o Bloc de Notas). 
   *Nota: La interfaz de Notebook te permite ingresar hasta 18,000 caracteres, proporcionando un espacio ideal para colocar de manera explícita el contexto analítico y las instrucciones del prompt sin que se pierdan en el historial del chat.*
4. En el panel izquierdo de entrada de texto de Notebook, copia y pega el siguiente bloque de datos consolidados de la simulación:

```text
--- CONTEXTO DE EVALUACIÓN: EXPEDIENTE XYZ CORP & RÚBRICA ---

[DATOS DEL EXPEDIENTE DE XYZ CORP]
- Liquidez: La empresa presenta una Razón Corriente (Activo Circulante / Pasivo Circulante) de 1.15 para el cierre del ejercicio 2023. No se incluye en el expediente el desglose detallado de inventarios, por lo que no es posible calcular de forma precisa la Prueba Ácida (Quick Ratio).
- Apalancamiento: El ratio Deuda Total / EBITDA consolidado es de 4.8x al 31 de diciembre de 2023. El Estado de Situación Financiera Consolidado de 2023 (Sección Pasivos, Pág. 14) detalla que el 80% de la deuda está contratada a tasa variable referenciada a la tasa interbancaria local.
- Gobernanza: La minuta del Acta de Junta Directiva de Octubre de 2023 (Pág. 5) reporta el retiro programado del Director de Finanzas (CFO) en un plazo de 6 meses. El documento menciona que el plan de sucesión está en "fase de borrador preliminar y sujeto a validación del comité de nominaciones".

[REGLAS DE NEGOCIO - RÚBRICA DE RIESGO CORPORATIVO]
- Criterio de Liquidez:
  * Riesgo Bajo: Razón Corriente >= 1.5x y Prueba Ácida disponible > 1.0x.
  * Riesgo Medio: Razón Corriente entre 1.2x y 1.49x.
  * Riesgo Alto: Razón Corriente < 1.2x, o ausencia de datos clave para calcular la liquidez inmediata.
- Criterio de Apalancamiento:
  * Riesgo Bajo: Ratio Deuda/EBITDA < 3.0x.
  * Riesgo Medio: Ratio Deuda/EBITDA entre 3.0x y 4.5x.
  * Riesgo Alto: Ratio Deuda/EBITDA > 4.5x, o exposición a tasas variables sin coberturas declaradas superior al 50%.
- Criterio de Gobernanza y Sucesión:
  * Riesgo Bajo: Plan de sucesión formalizado, firmado y aprobado para posiciones críticas C-Suite.
  * Riesgo Medio: Plan de sucesión en desarrollo o interino anunciado con cronograma claro de transición.
  * Riesgo Alto: Ausencia de plan de sucesión estructurado para roles C-Suite clave con salidas programadas en un plazo menor a 12 meses.
--- FIN DEL CONTEXTO ---
```

**Resultado esperado:** El texto de contexto se encuentra cargado correctamente en el cuadro de entrada de Copilot Notebook. El contador de caracteres debe mostrar un consumo aproximado de 2,200 caracteres de los 18,000 disponibles.

**Verificación:** Asegúrate de que el bloque copiado no tiene líneas truncadas y que los límites `--- CONTEXTO DE EVALUACIÓN ---` y `--- FIN DEL CONTEXTO ---` son claramente visibles en el área de trabajo.

---

### Paso 2: Ejecutar el Prompt de Evaluación Multidimensional y Trazabilidad

**Objetivo:** Instruir a Copilot para que procese los datos de contexto utilizando técnicas de ingeniería de prompts avanzadas, generando una matriz de riesgo y un resumen ejecutivo enfocado en la toma de decisiones humana.

1. Posiciona el cursor en el panel de entrada de **Copilot Notebook** justo debajo de la línea `--- FIN DEL CONTEXTO ---`.
2. Introduce un salto de línea y copia el siguiente prompt especializado de análisis estructurado:

```text
Actúa como un Analista de Riesgo de Crédito Senior e Instructor Técnico de Finanzas. Procesa exclusivamente los datos del "CONTEXTO DE EVALUACIÓN" provisto arriba. No utilices información externa ni asumas datos que no estén explícitamente declarados (evita estrictamente la alucinación).

Realiza las siguientes tareas:

1. MATRIZ DE CLASIFICACIÓN DE RIESGO:
Genera una tabla en formato Markdown con las siguientes columnas exactas:
- [Criterio]: Nombre del parámetro evaluado.
- [Clasificación]: Escala de riesgo asignada (Bajo / Medio / Alto) según los parámetros específicos de la Rúbrica.
- [Regla Aplicada]: La regla de la Rúbrica de Riesgo que se activa con los datos de la empresa.
- [Evidencia]: Hechos específicos y números exactos del expediente de XYZ Corp.
- [Fuente]: Sección o página exacta indicada en el expediente.
- [Información Faltante]: Datos específicos ausentes en el expediente para este criterio.
- [Aspectos de Revisión Profesional]: Puntos críticos subjetivos o alertas que el analista de riesgo humano debe auditar físicamente o negociar directamente con el cliente.

2. SÍNTESIS EJECUTIVA ORIENTADA AL JUICIO HUMANO:
Redacta un informe ejecutivo breve (máximo de dos párrafos) que responda a la estructura:
- Veredictos Firmes (Hechos): Qué conclusiones analíticas son inapelables según los datos duros actuales.
- Áreas Grises (Límites de la IA): Qué decisiones de riesgo NO pueden ser tomadas de forma automatizada y requieren indispensablemente que el analista de riesgo humano aplique su criterio experto, defina condiciones especiales o solicite garantías colaterales.
```

3. Haz clic en el botón de **Enviar** (o presiona `Ctrl + Enter`) para iniciar la ejecución del prompt en Copilot Notebook.

**Resultado esperado:** Copilot procesa el prompt e inicia la generación de una respuesta estructurada en tiempo real en el panel derecho. La salida debe contener:
- Una tabla Markdown de 7 columnas que evalúa los criterios de **Liquidez**, **Apalancamiento** y **Gobernanza y Sucesión**.
- Un resumen ejecutivo redactado con precisión técnica que delimita claramente las fronteras de la inteligencia artificial frente a la responsabilidad humana en la toma de decisión crediticia.

[VISUAL: 06-01-0003 - Ejemplo de interfaz de Copilot Notebook mostrando la entrada de contexto en la izquierda y la matriz estructurada resultante en la derecha]

**Verificación:** Revisa la tabla de salida de Copilot y valida que:
- El criterio **Liquidez** se clasifique como **Riesgo Alto** (debido a la Razón Corriente < 1.2x e información faltante sobre la Prueba Ácida).
- El criterio **Apalancamiento** se clasifique como **Riesgo Alto** (debido al Ratio Deuda/EBITDA de 4.8x y alta proporción de tasa variable).
- El criterio **Gobernanza** se clasifique como **Riesgo Alto** (debido a la salida programada del CFO en 6 meses sin un plan aprobado, cumpliendo el umbral de menos de 12 meses).

---

## Validación y Pruebas

Para garantizar que el modelo está operando bajo reglas de *Grounding* estrictas (anclaje total a la información provista) y no está sufriendo de sesgos cognitivos o alucinaciones, realizarás una prueba adversarial.

### Prueba de Resistencia Analítica (Prueba Adversarial)
1. En la misma sesión del Notebook (o usando la barra de seguimiento de chat en el panel derecho), introduce la siguiente instrucción adicional:

```text
¿Cuál es la clasificación del criterio "Cumplimiento Ambiental" de XYZ Corp y en qué página de los estados financieros se encuentra documentada su fianza de remediación de suelos? Responde basándote estrictamente en el contexto previamente cargado.
```

2. Envía la consulta y analiza detenidamente la respuesta de Copilot.

#### Resultado Esperado de la Validación:
Copilot debe denegar la respuesta o responder indicando explícitamente que **no puede determinar la clasificación de "Cumplimiento Ambiental" ni la fianza de remediación de suelos**, ya que dicha información no se encuentra presente en el contexto de evaluación provisto.

*Si Copilot inventa un número de página o una calificación de riesgo ambiental, la validación habrá fallado, evidenciando una alucinación por falta de restricciones en la configuración de la instrucción.*

---

## Solución de Problemas

En caso de encontrar fallos o comportamientos anómalos durante el desarrollo del laboratorio, utiliza las siguientes soluciones estructuradas:

### Problema 1: Copilot interrumpe la respuesta antes de terminar la Matriz o el Resumen Ejecutivo
* **Síntoma:** La tabla Markdown se corta a la mitad o la síntesis ejecutiva aparece incompleta, mostrando el texto de forma trunca.
* **Causa raíz:** Exceso de carga de red o el tokenizador de salida alcanzó el límite de longitud de respuesta de una sola interacción (Response limit token capping).
* **Solución:** Escribe en la línea de chat del panel derecho el siguiente mensaje de continuación directa: 
  `"Continúa exactamente desde el punto donde te quedaste en la tabla de clasificación de riesgo, manteniendo el mismo formato de columnas."`

### Problema 2: Copilot ignora las reglas de la Rúbrica y clasifica de forma genérica
* **Síntoma:** El modelo clasifica el apalancamiento de XYZ Corp como "Riesgo Medio" a pesar de que el valor de 4.8x supera el límite estricto de 4.5x fijado en la rúbrica.
* **Causa raíz:** El prompt diluyó el peso de la rúbrica dentro del texto de contexto o la IA priorizó información preentrenada de analistas de riesgo externos.
* **Solución:** Fuerza un anclaje estricto enviando el siguiente prompt correctivo:
  `"Tu clasificación anterior del apalancamiento viola la regla explícita de mi rúbrica que define Riesgo Alto para valores superiores a 4.5x. Corrige inmediatamente la matriz aplicando de forma estrictamente literal la regla definida en el contexto."`

---

## Limpieza

Es fundamental mantener la higiene de datos y cumplir con los estándares corporativos de protección de información financiera antes de cerrar el entorno de aprendizaje.

1. Copia los resultados de la matriz y el resumen ejecutivo generados por Copilot. Pégalos localmente en un bloc de notas o documento de control en la ruta establecida para este fin: `C:\M365_Copilot_Labs\Salidas\Matriz_Riesgo_XYZ.txt` (si el directorio no existe, puedes crearlo desde el Explorador de Archivos o ignorar el guardado si solo trabajas en entorno web).
2. Haz clic en el botón **Limpiar bloc de notas** (o el icono de papelera / "Nuevo tema") en la parte superior del panel de Copilot Notebook para borrar completamente el contexto cargado.
3. Cierra la pestaña activa de Microsoft Edge.

---

## Resumen

### Puntos Clave del Aprendizaje
- **Trazabilidad Absoluta:** La estructuración de la información dentro de Copilot Notebook permite un proceso analítico transparente, vinculando de manera inequívoca las conclusiones cualitativas y cuantitativas con reglas de negocio corporativas duras.
- **Identificación de Brechas (Gaps):** Copilot actúa como un validador de integridad documental, mapeando no solo los datos disponibles, sino identificando proactivamente la información que hace falta (como la ausencia del desglose de inventarios para la liquidez).
- **Control Profesional Humano:** El uso de herramientas de IA de última generación optimiza los tiempos de procesamiento de datos, pero la responsabilidad del veredicto final recae siempre sobre el especialista de riesgo. La separación entre "Veredictos Firmes" y "Áreas Grises" ayuda al analista a priorizar su tiempo en decisiones complejas y mitigaciones de crédito.

### Recursos Adicionales de Consulta
- [Grounding de datos corporativos en Microsoft 365 Copilot](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-grounding)
- [Mejores prácticas para la redacción de prompts analíticos en entornos de finanzas de Microsoft](https://techcommunity.microsoft.com/t5/financial-services/ct-p/FinancialServices)

---

# Práctica: Validar la cobertura y suficiencia de evidencia antes de aceptar la clasificación de riesgo

## Metadatos
| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 6 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel de Bloom** | Analizar (Analyze) |

## Descripción General
En este laboratorio, asumirás el rol de un Auditor de Riesgo Financiero Senior. Utilizarás **Microsoft 365 Copilot** (ejecutando el agente especializado **Analista / Analyst**) para auditar una matriz de clasificación de riesgo financiero consolidada (`Matriz_Riesgo_Consolidada.xlsx`). El objetivo principal es identificar de forma automatizada y sistemática si las clasificaciones asignadas cuentan con el sustento documental adecuado, detectar contradicciones lógicas entre los datos numéricos y las reglas de negocio, y estructurar un reporte de brechas de información que determine qué casos deben ser aceptados y cuáles requieren escalamiento inmediato.

## Objetivos de Aprendizaje
Al finalizar este laboratorio, serás capaz de:
- [ ] Analizar la matriz de clasificación de riesgos utilizando el agente especializado **Analista (Analyst)** en Copilot para detectar brechas de información.
- [ ] Contrastar la evidencia disponible frente a las reglas de la rúbrica de riesgo financiero preestablecida.
- [ ] Generar un reporte de inconsistencias, contradicciones y fuentes pendientes para determinar si una clasificación debe ser aceptada o escalada al comité de riesgo.

## Prerrequisitos
- **Conocimientos:** Comprensión básica de métricas de riesgo de crédito (apalancamiento, liquidez, cobertura de intereses) y estructura de matrices de riesgo.
- **Licenciamiento:** Licencia activa de **Microsoft 365 Copilot Premium** (Copilot para Microsoft 365 con actualización de Septiembre de 2024).
- **Acceso a Aplicaciones:** Acceso a **Microsoft Excel Online** o **Microsoft Excel para Enterprise** con conexión a OneDrive corporativo.
- **Datos de Origen:** Disponer del archivo simulado `Matriz_Riesgo_Consolidada.xlsx` en tu espacio de trabajo de OneDrive.

## Entorno de Laboratorio

### Requisitos de Hardware y Conectividad
| Componente | Requisito Mínimo | Requisito Recomendado |
| :--- | :--- | :--- |
| **Resolución de Pantalla** | 1920x1080 píxeles (Panel dividido) | 1920x1080 píxeles o superior |
| **Conexión a Internet** | 10 Mbps de bajada y subida | 20 Mbps (Banda ancha sin restricciones) |
| **Memoria RAM** | 8 GB | 16 GB |

### Requisitos de Software y Versiones Oficiales
| Software / Servicio | Versión de Referencia | Proveedor / Origen Oficial |
| :--- | :--- | :--- |
| **Sistema Operativo** | Windows 11 Enterprise (Versión 23H2 o superior) | [Microsoft Windows](https://www.microsoft.com/es-es/windows) |
| **Navegador Web** | Microsoft Edge (Versión 128.0.2739.42 o superior) | [Microsoft Edge](https://www.microsoft.com/es-es/edge) |
| **Suite de Oficina** | Microsoft 365 Apps para Empresas (Canal Mensual Empresarial - Versión 2408, Compilación 17928.20114) | [Microsoft 365](https://www.microsoft.com/es-es/microsoft-365) |
| **Hoja de Cálculo** | Microsoft Excel para Enterprise (Versión 2402, Compilación 17328.20142) / Excel Online | [Microsoft Excel](https://www.microsoft.com/es-es/microsoft-365/excel) |

### Ruta del Directorio de Trabajo
- **Ruta local predefinida:** `C:\M365_Copilot_Labs\`
- **Ruta en la nube:** Raíz de tu **OneDrive para la Empresa** asociado a la cuenta organizativa.

---

## Instrucciones Paso a Paso

### Paso 1: Preparación del archivo simulado de matriz de riesgo
**Objetivo:** Crear y cargar el archivo de datos que servirá de fuente estructurada para la auditoría mediante Copilot.

1. Abre Microsoft Excel (local o web) y crea un nuevo libro en blanco.
2. Copia y pega la siguiente tabla de datos exactamente en el rango de celdas `A1:G5`:

| ID | Criterio | Clasificación Asignada | Regla Aplicable | Evidencia Registrada | Fuente de Soporte | Información Faltante Detectada |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Apalancamiento | Riesgo Alto | Ratio Deuda/Patrimonio > 2.0x | Ratio actual de 2.45x | Estado de Situación Financiera 2023, Pág. 12 | Ninguna |
| 2 | Liquidez | Riesgo Bajo | Ratio Circulante > 1.5x | Ratio actual de 1.10x | Estado de Situación Financiera 2023, Pág. 8 | Ninguna |
| 3 | Cobertura de Intereses | Riesgo Medio | EBITDA/Gastos Financieros de 2.0x a 3.0x | EBITDA/Gastos Financieros de 1.8x | [Sin fuente especificada] | Estado de Flujo de Efectivo detallado |
| 4 | Gobernanza | Riesgo Bajo | Plan de sucesión formalizado para el C-Suite | Plan en borrador preliminar | Acta de Junta Directiva, Octubre 2023 | Perfiles de candidatos definitivos |

3. Guarda el archivo con el nombre exacto de `Matriz_Riesgo_Consolidada.xlsx` en tu directorio local `C:\M365_Copilot_Labs\` y cárgalo en tu **OneDrive para la Empresa** (asegúrate de que el estado de sincronización sea "Sincronizado" o "En la nube").

**Resultado esperado:** El archivo se encuentra correctamente alojado en OneDrive y es accesible a través del ecosistema de Microsoft 365.
**Verificación:** Abre OneDrive en tu navegador Edge y confirma que el archivo `Matriz_Riesgo_Consolidada.xlsx` se visualiza en la sección "Mis Archivos".

---

### Paso 2: Iniciar Copilot Chat con el Agente Analista (Analyst)
**Objetivo:** Acceder a la interfaz de interacción correcta y habilitar el agente de análisis de datos para procesar la información del archivo de Excel.

1. Abre tu navegador web **Microsoft Edge (128.0.2739.42)**.
2. Navega al portal oficial de Copilot: [copilot.microsoft.com](https://copilot.microsoft.com) e inicia sesión con tu cuenta organizativa (la cual cuenta con la licencia activa de **Microsoft 365 Copilot Premium**).
3. En el menú lateral derecho de la interfaz o en la sección de agentes especializados, selecciona el agente **Analista** (o **Analyst**). Si no visualizas el agente independiente, utilizarás la interfaz de chat principal con anclaje de datos directo utilizando la funcionalidad de adjuntar archivos.

[VISUAL: Interfaz de chat de Microsoft 365 Copilot mostrando la opción de adjuntar archivo o referenciar datos de OneDrive corporativo]

**Resultado esperado:** El panel de chat muestra el indicador de que el sistema de anclaje de datos está listo para recibir referencias de archivos de tu organización.
**Verificación:** Escribe el carácter `/` en la caja de texto del prompt y confirma que se despliega la lista de archivos recientes de tu OneDrive, mostrando `Matriz_Riesgo_Consolidada.xlsx`.

---

### Paso 3: Ejecución del prompt de auditoría de cobertura
**Objetivo:** Ejecutar un prompt altamente estructurado que contraste las clasificaciones asignadas con las evidencias, detecte incoherencias lógicas y determine el estatus de aprobación o escalamiento.

1. En la caja de texto del chat de Copilot, ingresa y ejecuta con precisión el siguiente prompt estructurado:

```text
Actúa como un Auditor de Riesgo Financiero Senior. Tu objetivo es realizar un control de calidad y auditoría de consistencia de los datos en el archivo 'Matriz_Riesgo_Consolidada.xlsx' cargado en mi OneDrive.

Realiza las siguientes acciones analíticas de forma estricta:
1. Analiza cada fila del archivo contrastando la columna "Clasificación Asignada" contra la "Regla Aplicable" y la "Evidencia Registrada".
2. Identifica contradicciones lógicas (por ejemplo, si los números de la evidencia no cumplen la regla, pero aun así se asignó una clasificación favorable).
3. Detecta brechas de información crítica, como la falta de fuentes especificadas o información faltante declarada.
4. Genera una tabla de salida estructurada con las siguientes columnas:
   - ID
   - Criterio
   - Consistencia de Datos (Consistente / Inconsistente / Datos Insuficientes)
   - Explicación del Hallazgo (Detalla de forma cuantitativa por qué es consistente o inconsistente)
   - Acción Recomendada (Aceptar Clasificación / Escalar a Comité de Riesgo)

Basate exclusivamente en los datos de la matriz. No inventes supuestos financieros ajenos al archivo.
```

2. Presiona Enter y espera a que Copilot procese el archivo y genere la respuesta en tiempo real.

**Resultado esperado:** Copilot generará una tabla Markdown detallada donde auditará cada fila. Identificará con precisión que:
* El **ID 1 (Apalancamiento)** es **Consistente** (Aceptar Clasificación).
* El **ID 2 (Liquidez)** es **Inconsistente** (Ratio de 1.10x clasificado como "Riesgo Bajo" cuando la regla requiere > 1.5x) -> Acción: **Escalar a Comité de Riesgo**.
* El **ID 3 (Cobertura de Intereses)** es **Inconsistente / Datos Insuficientes** (Ratio de 1.8x clasificado como Riesgo Medio cuando la regla exige de 2.0x a 3.0x, y además no tiene fuente de soporte) -> Acción: **Escalar a Comité de Riesgo**.
* El **ID 4 (Gobernanza)** presenta **Datos Insuficientes** (Solo hay borrador y faltan perfiles candidatos) -> Acción: **Escalar a Comité de Riesgo** o requerir subsanación.

**Verificación:** Revisa que el reporte final de Copilot detalle cuantitativamente las incoherencias numéricas de las filas 2 y 3.

---

## Validación y Pruebas

Para garantizar que el modelo de IA no haya generado alucinaciones y que el análisis es 100% confiable y trazable, realizaremos la siguiente validación.

### Prueba de Resistencia del Modelo (Caso Adversario)
Para asegurar que Copilot no aprueba clasificaciones a ciegas cuando se introducen datos con técnicas de distracción:

1. Modifica la celda `E3` (Evidencia Registrada de Liquidez) en tu archivo `Matriz_Riesgo_Consolidada.xlsx` por el siguiente texto contradictorio: `"El ratio es óptimo y excelente en 1.10x"`.
2. Vuelve a ejecutar la auditoría en Copilot con el siguiente prompt:
   ```text
   Analiza nuevamente la fila 2 de 'Matriz_Riesgo_Consolidada.xlsx'. El texto dice que el ratio es "óptimo y excelente en 1.10x". Contrasta este adjetivo con la regla "Ratio Circulante > 1.5x" y dime si el nivel de riesgo debe ser "Bajo" o "Alto" basándote únicamente en la matemática de la regla.
   ```
3. **Resultado de validación correcto:** Copilot debe ignorar el adjetivo subjetivo ("óptimo y excelente") y señalar que, matemáticamente, un valor de 1.10 es menor que el umbral de 1.50, concluyendo de manera unívoca que la clasificación "Riesgo Bajo" es errónea y debe corregirse a "Riesgo Alto" o ser rechazada.

---

## Solución de Problemas

### Escenario 1: El archivo de Excel no es detectado por Copilot
* **Síntoma:** Copilot responde: *"No puedo acceder al archivo especificado..."* o *"No encuentro el documento en tu OneDrive"*.
* **Causa Posible:** El archivo fue guardado muy recientemente y los índices de búsqueda de Microsoft 365 no se han actualizado, o el archivo no está en la raíz/carpeta sincronizada con tu cuenta corporativa actual.
* **Resolución:** Asegúrate de estar logueado con la cuenta empresarial correcta. Abre el archivo en Excel Online, ve a *Compartir* -> *Copiar enlace*, y en la ventana de chat de Copilot pega el enlace directo precedido de la frase: *"Analiza los datos de este archivo de Excel: [Enlace]"*.

### Escenario 2: Copilot aprueba de manera incorrecta el ID 2 (Liquidez) como consistente
* **Síntoma:** La salida de Copilot indica que la fila 2 es "Consistente" y recomienda "Aceptar".
* **Causa Posible:** El motor LLM interpretó de forma laxa el condicional matemático debido a la redacción cualitativa o "ruido" en el prompt.
* **Resolución:** Fuerza el análisis determinista enviando la siguiente instrucción complementaria: *"Revisa el ID 2 de nuevo. Si la regla exige que sea Mayor a 1.5x (>1.5x) y la evidencia registra un valor de 1.10x, ¿se cumple matemáticamente la condición? Responde Sí o No, y recalcula la consistencia"*.

---

## Limpieza
1. Cierra la pestaña activa del chat de Copilot en Microsoft Edge.
2. Si utilizaste Microsoft Excel Online, cierra la pestaña del navegador para liberar las sesiones de edición concurrentes en SharePoint/OneDrive.
3. (Opcional) Si deseas mantener limpio tu almacenamiento de laboratorio, dirígete a OneDrive para la Empresa y elimina o archiva el archivo `Matriz_Riesgo_Consolidada.xlsx` en una subcarpeta de históricos.

---

## Resumen
En esta práctica, has implementado una auditoría automatizada y rigurosa sobre una matriz consolidada utilizando **Microsoft 365 Copilot**. A través de la interacción con el agente especializado, aprendiste a:
* Cruzar reglas lógicas de negocio (umbrales numéricos de riesgo) con datos reales ingresados como evidencia en hojas de cálculo.
* Detectar inconsistencias cualitativas y cuantitativas (como ratios por debajo del umbral clasificados erróneamente).
* Estructurar de manera inmediata un plan de acción para comités de riesgo, separando los elementos de cálculo lineal de aquellos que requieren de forma obligatoria el juicio profesional de un analista humano.

---

# Práctica: Consolidar una síntesis ejecutiva del análisis diferenciando evidencia, clasificación, incertidumbres e información pendiente

## Metadatos

| Parámetro | Detalle |
| :--- | :--- |
| **Duración** | 4 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar (Apply) |

---

## Descripción General

En este laboratorio, consolidará de manera estructurada los hallazgos de cobertura y riesgo obtenidos en el laboratorio anterior (06-00-02) utilizando la interfaz avanzada de **Copilot Notebooks**. Diseñará e implementará una instrucción (prompt) estructurada de alta longitud para generar una síntesis ejecutiva orientada a un comité de riesgos de alto nivel. El entregable final se estructurará rigurosamente bajo cinco pilares analíticos y se exportará a Microsoft Word, donde aplicará su juicio crítico como analista financiero senior para validar la salida generada por la Inteligencia Artificial.

---

## Objetivos de Aprendizaje

Al finalizar este laboratorio, usted será capaz de:
- [ ] Consolidar los hallazgos de validación de un expediente de crédito corporativo utilizando **Copilot Notebooks**.
- [ ] Estructurar una síntesis ejecutiva técnica diferenciando claramente: Evidencia disponible, Clasificación obtenida, Factores sustentadores, Incertidumbres e Información pendiente (Gaps).
- [ ] Refinar y exportar el entregable en formato de Microsoft Word (`Sintesis_Ejecutiva_Riesgos.docx`).
- [ ] Implementar un bloque estructurado de "Juicio Profesional" que resguarde y formalice el criterio del analista humano frente al output automatizado.

---

## Prerrequisitos

Para realizar este laboratorio de manera exitosa, usted requiere:
1. Haber completado satisfactoriamente el laboratorio anterior (06-00-02) y disponer de los hallazgos de auditoría (datos de cobertura financiera del cliente corporativo ficticio "XYZ Corp").
2. Acceso a una cuenta corporativa o educativa activa con licencia de **Microsoft 365 Copilot Premium**.
3. Navegador web moderno con acceso a la versión web de Copilot Notebooks ([https://copilot.microsoft.com](https://copilot.microsoft.com)).
4. **Microsoft Word para Enterprise** instalado localmente o acceso a Microsoft Word Online para el procesamiento del archivo final.

---

## Entorno de Laboratorio

Este laboratorio requiere del uso integrado de herramientas web y de escritorio dentro de un entorno controlado.

### Componentes de Software Utilizados

| Software / Servicio | Edición / Versión | Enlace de Descarga / Acceso Oficial |
| :--- | :--- | :--- |
| **Microsoft Edge** | Versión 128.0.2739.42 (o superior) | [https://www.microsoft.com/edge](https://www.microsoft.com/edge) |
| **Microsoft Word para Enterprise** | Versión 2402 (Build 17328.20142) | [https://apps.microsoft.com](https://apps.microsoft.com) |
| **Microsoft 365 Copilot Premium** | Service Update 2404 (Suscripción Activa) | [https://copilot.microsoft.com](https://copilot.microsoft.com) |

### Directorio de Trabajo Local
- **Ruta local establecida:** `C:\M365_Copilot_Labs\`
- **Archivo de entrada esperado:** `C:\M365_Copilot_Labs\Hallazgos_Cobertura_06-00-02.txt` (creado con los datos de balance, ratios de deuda de 2.45x, falta de plan formal de transición del CFO y proyecciones de flujo de caja).

---

## Instrucciones Paso a Paso

### Paso 1: Configurar Copilot Notebooks y preparar los hallazgos de origen

**Objetivo:** Inicializar el entorno interactivo de alta capacidad de Copilot Notebooks e importar la información consolidada.

1. Abra su navegador **Microsoft Edge** y diríjase al portal oficial de Copilot: [https://copilot.microsoft.com](https://copilot.microsoft.com).
2. Asegúrese de haber iniciado sesión con su cuenta organizacional que dispone de la licencia de **Microsoft 365 Copilot Premium** (busque el distintivo verde/azul de Copilot para empresas en la esquina superior derecha).
3. En el menú superior de la interfaz de Copilot, haga clic en la opción **Notebook** (o **Bloc de notas**). Esta interfaz le permite escribir prompts detallados de hasta 18,000 caracteres con paneles divididos de entrada y salida.

   [VISUAL: Interfaz web de Copilot con la opción "Notebook" seleccionada en la barra superior]

4. Abra con el Bloc de notas de Windows su archivo local de hallazgos situado en:
   `C:\M365_Copilot_Labs\Hallazgos_Cobertura_06-00-02.txt`
5. Seleccione todo el texto (que contiene la información cuantitativa de deuda/cobertura y la información cualitativa del CFO saliente de XYZ Corp) y cópielo en el portapapeles (`Ctrl + C`).

**Resultado esperado:** El texto de origen está cargado en el portapapeles y la interfaz web de Copilot Notebook está lista para recibir instrucciones complejas en la ventana de entrada de la izquierda.

**Verificación:** Confirme que el límite de caracteres que muestra el cuadro de texto de Copilot se ha extendido de los 4,000 habituales a un rango superior (normalmente hasta **18,000** caracteres).

---

### Paso 2: Ejecutar el prompt estructurado de consolidación en Copilot Notebooks

**Objetivo:** Procesar los hallazgos mediante una instrucción (prompt) técnica que exija la estructuración de la síntesis en los cinco pilares obligatorios de riesgo.

1. Sitúese en el panel de texto izquierdo de **Copilot Notebook**.
2. Escriba (o adapte utilizando los datos del portapapeles) la siguiente instrucción técnica estructurada:

```text
Actúa como un Analista de Riesgo Corporativo y Redactor Técnico Senior de Comités de Crédito. 

A partir de los siguientes datos consolidados del caso "XYZ Corp", genera un borrador de Síntesis Ejecutiva de Riesgos de alto nivel técnico.

---
DATOS DE ORIGEN DE XYZ CORP:
- Ratio Deuda Total / Patrimonio actual: 2.45x (Límite máximo según políticas de la organización: 2.0x).
- Estado de Situación Financiera: 2023, Pág. 12, Sección de Pasivos Financieros.
- Aspecto cualitativo: Retiro programado del actual CFO en 6 meses. Existe un plan de sucesión preliminar pero es informal e incompleto.
- Gaps identificados: Faltan proyecciones de flujo de caja para el cuarto trimestre (Q4) de 2024 y desglose detallado de las tasas de refinanciamiento vigentes.
---

Estructura el output de forma rigurosa bajo los siguientes cinco pilares en formato Markdown limpio (no uses introducciones informales):

1. **Evidencia Disponible**: Expón los hechos cuantitativos y cualitativos duros que se han verificado, indicando la fuente teórica si está disponible.
2. **Clasificación Obtenida**: Define la calificación técnica de riesgo aplicable según los ratios actuales de la empresa (Ej. "Riesgo Alto" en Apalancamiento, "Riesgo Medio" en Gobernanza).
3. **Factores Sustentadores**: Redacta el análisis técnico de por qué se asignó esa clasificación, relacionando directamente la evidencia con la desviación de las reglas de negocio.
4. **Incertidumbres**: Detalla los riesgos cualitativos latentes o eventos futuros no cuantificables (como el impacto operativo del cambio de CFO).
5. **Información Pendiente (Gaps)**: Enlista los documentos faltantes que impiden un cierre conclusivo del expediente.

Al final del documento, añade una sección titulada:
"### Juicio Profesional del Analista (Espacio Reservado para Revisión Humana)"
Bajo este título, incluye un párrafo instructivo que recuerde al analista humano evaluar el impacto cualitativo de la transición de liderazgo y las condiciones generales del mercado de tasas antes de presentar este caso al Comité.
```

3. Presione el botón **Enviar** (o el ícono del avión de papel en la esquina inferior derecha del bloque de entrada) para ejecutar la instrucción en Copilot.

**Resultado esperado:** Copilot genera en el panel de salida (derecho) una síntesis ejecutiva perfectamente estructurada en cinco secciones diferenciadas, con un tono analítico e institucional, libre de alucinaciones y con la sección final de juicio profesional.

**Verificación:** Revise visualmente que el panel de salida de Copilot contenga los encabezados Markdown `1. Evidencia Disponible`, `2. Clasificación Obtenida`, `3. Factores Sustentadores`, `4. Incertidumbres` e `5. Información Pendiente (Gaps)`, además de la sección para el analista humano.

---

### Paso 3: Exportar el borrador a Microsoft Word y aplicar el juicio profesional

**Objetivo:** Transferir la información analítica a un entorno local de edición formal para asegurar la trazabilidad del expediente.

1. En la parte inferior de la respuesta generada por Copilot Notebook, haga clic en el ícono de tres puntos **(...)** (Más acciones).
2. Seleccione la opción **Exportar a Word** (o copie todo el texto y péguelo en un documento en blanco de Microsoft Word si está trabajando en un entorno web integrado).
3. Una vez abierto el documento en Microsoft Word, guárdelo inmediatamente en su directorio local con el nombre del entregable normativo:
   - **Ruta:** `C:\M365_Copilot_Labs\Sintesis_Ejecutiva_Riesgos.docx`
4. Diríjase de forma manual a la última sección: `### Juicio Profesional del Analista`.
5. Reemplace el marcador de posición generado por la IA por su propia conclusión técnica profesional. Agregue el siguiente texto final al expediente:

```text
[Aprobación del Analista Senior]: Se determina que la clasificación de Riesgo Alto en apalancamiento (2.45x) requiere una mitigación contractual. Se recomienda condicionar cualquier extensión de línea de crédito a la presentación formalizada del plan de sucesión del CFO en un plazo no mayor a 45 días naturales y al envío de las proyecciones de flujo de caja mensuales auditadas del Q4.
```

6. Guarde los cambios ejecutando el comando de guardado de Word (`Ctrl + G`).

**Resultado esperado:** Un documento de Microsoft Word formalizado en la ruta `C:\M365_Copilot_Labs\Sintesis_Ejecutiva_Riesgos.docx` que incorpora perfectamente el análisis estructurado de Copilot y el juicio experto final del analista de riesgos.

**Verificación:** Abra el explorador de archivos en la ruta `C:\M365_Copilot_Labs\` y verifique que el peso del archivo sea superior a 0 KB y contenga los textos editados manualmente.

---

## Validación y Pruebas

Para garantizar que el proceso de consolidación de la síntesis ejecutiva cumple con las directrices de trazabilidad institucional, ejecute las siguientes verificaciones.

### Criterio de Aceptación Técnico
- El archivo `Sintesis_Ejecutiva_Riesgos.docx` debe existir en el directorio `C:\M365_Copilot_Labs\`.
- El documento debe contener de manera explícita la estructura de 5 pilares definidos en los objetivos.
- El ratio cuantitativo de **2.45x** debe estar referenciado bajo la sección de **Evidencia Disponible** vinculándose a la página 12 del balance de 2023.

### Prueba Adversaria de Consistencia (Control de Alucinación)
Con el fin de validar que Copilot no inventó datos bajo el principio de *grounding*, ejecute la siguiente prueba visual de contraste de datos:

1. Abra el documento `Sintesis_Ejecutiva_Riesgos.docx` en Word.
2. Busque dentro del texto del documento la palabra "EBITDA" o la tasa de interés promedio de XYZ Corp.
3. **Resultado Esperado de la Prueba:** Como dichos parámetros específicos (valores monetarios de EBITDA o porcentajes de tasas) no fueron provistos en los datos de origen del Paso 2, Copilot **no** debió inventar valores artificiales para esos campos. Si Copilot colocó un valor numérico ficticio (por ejemplo, "EBITDA de 15%"), elimine ese segmento del documento y marque una alerta de alucinación. Si el modelo los dejó como "Información pendiente" o "No disponible", el comportamiento del grounding de Copilot es correcto y seguro para producción.

---

## Solución de Problemas

A continuación, se describen los dos incidentes más comunes durante la ejecución de esta práctica de consolidación y sus métodos de solución.

### Incidente 1: La interfaz de Copilot Notebook no muestra la pestaña "Notebook" o el cuadro de texto está limitado a 4,000 caracteres
- **Causa:** El usuario ha iniciado sesión con una cuenta personal de Microsoft (MSA) o la licencia corporativa de Microsoft 365 Copilot Premium no está correctamente asignada o activa en la sesión web del navegador Edge.
- **Resolución:**
  1. Haga clic en el círculo de su perfil de usuario en la esquina superior derecha del navegador y valide que el correo corresponda a su dominio corporativo o de capacitación.
  2. Cierre sesión en `copilot.microsoft.com` e ingrese nuevamente utilizando la opción "Iniciar sesión con una cuenta profesional o educativa".
  3. Si la pestaña sigue sin aparecer, use el chat regular de Copilot pero divida el prompt largo en dos partes secuenciales para evitar límites de contexto de entrada.

### Incidente 2: Error al exportar el borrador a Microsoft Word o el formato se descarga como archivo plano
- **Causa:** Bloqueo de ventanas emergentes en Microsoft Edge que impide la generación dinámica del archivo `.docx` o la sincronización con OneDrive corporativo está deshabilitada.
- **Resolución:**
  1. Revise la barra de direcciones de Edge; si ve un ícono de ventana bloqueada con una cruz roja, haga clic sobre él y seleccione "Permitir siempre ventanas emergentes de https://copilot.microsoft.com".
  2. Como alternativa directa, seleccione de forma manual todo el texto del panel de salida en Copilot Notebooks (`Ctrl + A` dentro del cuadro, o arrastre con el mouse), presione `Ctrl + C`, abra la aplicación de escritorio de Microsoft Word local, pegue el texto con la opción de pegado especial "Mantener formato de origen" y guarde el archivo manualmente en `C:\M365_Copilot_Labs\Sintesis_Ejecutiva_Riesgos.docx`.

---

## Limpieza

Para mantener la integridad de su estación de trabajo y prepararla para futuros análisis de alta volumetría, realice las siguientes acciones de limpieza:

1. Cierre el documento `Sintesis_Ejecutiva_Riesgos.docx` en Microsoft Word para liberar los bloqueos de memoria de archivo.
2. Limpie el historial del panel interactivo de Copilot Notebook presionando el ícono de la papelera o el botón de "Nuevo tema" (New Topic) en la interfaz web para asegurar que ningún residuo de contexto financiero afecte futuras consultas.
3. Asegúrese de que el archivo final consolidado `Sintesis_Ejecutiva_Riesgos.docx` permanezca guardado únicamente en la carpeta de laboratorio local autorizada: `C:\M365_Copilot_Labs\`. No guarde copias en carpetas compartidas públicas si se trata de simulaciones con datos sensibles de negocio.

---

## Resumen

En este laboratorio, ha aprendido a utilizar la potencia de **Copilot Notebooks** para consolidar datos financieros de naturaleza heterogénea (cuantitativos e informales cualitativos) en una síntesis ejecutiva orientada a la toma de decisiones críticas de riesgo. 

### Conceptos Clave Consolidados:
- **Notebook vs. Chat Regular:** El uso del bloc de notas de Copilot con límites extendidos de entrada permite inyectar contextos de análisis mucho más densos para evitar omisiones de información.
- **Diferenciación de Pilares:** Una síntesis ejecutiva eficaz requiere separar nítidamente lo verificado (Evidencia) de lo que es especulación o brecha de información (Incertidumbre y Gaps).
- **Soberanía Humana del Analista:** El valor de la IA radica en acelerar la estructuración de la información del expediente, pero la decisión final siempre descansa sobre el bloque de "Juicio Profesional", el cual debe ser redactado, aprobado y firmado por un analista humano calificado.
