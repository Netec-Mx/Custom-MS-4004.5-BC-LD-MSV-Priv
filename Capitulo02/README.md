# Práctica: Construir una rúbrica de clasificación de riesgo a partir de reglas de negocio ficticias con Copilot

## Metadatos

| Métrica | Detalle |
| :--- | :--- |
| **Duración** | 9 minutos |
| **Complejidad** | Media |
| **Nivel de Bloom** | Aplicar |

---

## Descripción General

En este laboratorio, aplicarás técnicas de ingeniería de prompts en Microsoft 365 Copilot para convertir políticas cualitativas abstractas y reglas de negocio desestructuradas en una rúbrica de clasificación de riesgo de crédito corporativo formalizada. Utilizando una serie de directrices y excepciones ficticias provistas directamente en el laboratorio, instruirás a Copilot para diseñar una matriz estructurada en formato tabular Markdown. Esta matriz servirá como motor de decisiones unificado, garantizando la trazabilidad, objetividad y la erradicación de zonas grises interpretativas durante los análisis financieros posteriores.

---

## Objetivos de Aprendizaje

Al finalizar este laboratorio, serás capaz de:
*   **Identificar y extraer** de forma estructurada variables cuantitativas, condiciones operativas y excepciones lógicas desde un texto narrativo de políticas de negocio.
*   **Diseñar un prompt estructurado** en Copilot que prevenga la superposición de umbrales numéricos mediante la lógica MECE (Mutuamente Excluyentes y Colectivamente Exhaustivos).
*   **Construir una rúbrica multidimensional** (niveles Bajo, Medio, Alto) que asocie directamente disparadores numéricos, mitigantes y la evidencia documental requerida para la verificación.

---

## Prerrequisitos

*   **Conocimientos teóricos:** Comprensión básica de indicadores de liquidez (Ratio Corriente), endeudamiento (Deuda/Patrimonio), ciclo operativo (Días de Cuentas por Pagar o DPO) y el concepto de mitigantes financieros.
*   **Acceso tecnológico:** Cuenta organizacional activa con licencia de **Microsoft 365 Copilot Premium** asignada.
*   **Entorno de navegación:** Acceso a la interfaz web de Microsoft Copilot desde un navegador compatible.

---

## Entorno de Laboratorio

### Requisitos de Hardware y Conectividad

| Componente | Especificación Mínima Requerida |
| :--- | :--- |
| **Estación de Trabajo** | Windows 11 Enterprise (Versión 23H2 o superior) o macOS Sonoma (14.4 o superior). |
| **Resolución de Pantalla** | Mínima de 1920x1080 píxeles para visualización cómoda en pantalla dividida. |
| **Conectividad** | Conexión a Internet de banda ancha (mínimo 10 Mbps de subida y bajada). |

### Componentes de Software y Licenciamiento

| Software / Servicio | Edición / Versión | Origen / URL de Referencia |
| :--- | :--- | :--- |
| **Microsoft Edge** | Versión 128.0.2739.42 (o superior) | [Descargar Microsoft Edge](https://www.microsoft.com/es-es/edge) |
| **Microsoft 365 Copilot** | Premium (Service Update 2404) | [Portal de Microsoft 365](https://portal.office.com) |
| **Directorio de Trabajo** | Local: `C:\M365_Copilot_Labs\` | Creado manualmente por el estudiante |

---

## Instrucciones Paso a Paso

### Paso 1: Inicializar la sesión de Copilot y preparar el entorno de trabajo

**Objetivo:** Configurar el canal de interacción con Microsoft 365 Copilot bajo el contexto laboral adecuado para garantizar el procesamiento seguro de datos corporativos simulados.

1. Abre tu navegador **Microsoft Edge** (Versión 128.0.2739.42 o superior).
2. Dirígete al portal oficial de Copilot Web: [copilot.microsoft.com](https://copilot.microsoft.com).
3. Asegúrate de iniciar sesión con tus credenciales de cuenta de organización (E3 o E5 con el Add-on de Copilot activo). Sabrás que la sesión está protegida si visualizas el escudo de protección de datos comerciales ("Protección de datos comerciales" o "Protected") en la esquina superior derecha de la interfaz.
4. Si el navegador lo solicita, establece el modo de conversación en **Creativo** o utiliza la vista de chat estándar para procesamiento de texto estructurado.
5. Abre el Explorador de Archivos de Windows y confirma la existencia del directorio local `C:\M365_Copilot_Labs`. Si no existe, créalo ejecutando la siguiente instrucción en PowerShell:
   ```powershell
   New-Item -ItemType Directory -Path "C:\M365_Copilot_Labs" -Force
   ```

*Resultado esperado:* Interfaz de Copilot lista para interactuar, con inicio de sesión organizacional activo, y la carpeta de almacenamiento de salida local configurada en el sistema de archivos.

*Verificación:* Observa el indicador verde de privacidad o el escudo de protección de datos de Microsoft junto a tu perfil de usuario en la interfaz web de Copilot.

---

### Paso 2: Ejecutar el prompt de extracción y consolidación de la rúbrica

**Objetivo:** Traducir un conjunto desordenado de reglas de negocio en una rúbrica estructurada de tres niveles (Bajo, Medio, Alto) utilizando una instrucción optimizada que elimine solapamientos de umbrales cuantitativos.

1. Copia íntegramente el siguiente bloque de texto que contiene las reglas de negocio ficticias del departamento de crédito de la empresa simulada *FinanzCorp*:

   ```text
   REGLAS DE NEGOCIO - FINANZCORP CREDIT DEPT:
   - Se considera que una empresa tiene una salud óptima si su ratio de liquidez corriente es superior o igual a 1.60 y sus días de cuentas por pagar (DPO) no superan los 35 días. Deben presentar estados financieros auditados completos.
   - En situaciones donde la liquidez corriente caiga por debajo de 1.60 pero se mantenga arriba o igual de 1.15, se le considera en observación. No obstante, si sus DPO están entre 36 y 60 días, se clasifica en esta zona de atención intermedia. Se requiere balance firmado por contador y el último reporte tributario.
   - Si la liquidez corriente es inferior a 1.15, o sus DPO rebasan los 60 días, pasa de inmediato a categoría crítica.
   - Excepciones al nivel crítico: Si la empresa deudora cuenta con un aval corporativo incondicional firmado por una casa matriz con calificación grado de inversión (BBB- o superior), se le puede reclasificar a nivel intermedio, siempre y cuando se adjunte el contrato de fianza legalizado y el reporte de calificación de la matriz con menos de 60 días de antigüedad.
   - Excepciones al nivel intermedio: Empresas estratégicas de infraestructura que cuenten con contratos públicos vigentes por más de 5 años pueden exceptuarse del ratio de liquidez si adjuntan el acta de adjudicación oficial del contrato.
   ```

2. Introduce la siguiente instrucción estructurada (**prompt**) en la caja de diálogo de Copilot, integrando las reglas anteriores:

   ```text
   Actúa como un Diseñador de Metodologías de Riesgo Financiero y Auditor Senior. Tu objetivo es procesar las reglas de negocio provistas de FinanzCorp y estructurarlas en una rúbrica de clasificación de riesgo de crédito multidimensional. 

   Debes garantizar el cumplimiento estricto del principio MECE (Mutuamente Excluyentes y Colectivamente Exhaustivos) para que no existan superposiciones numéricas en los rangos.

   Aplica la siguiente estructura para el output final:
   - Presenta los resultados únicamente en una tabla estructurada de Markdown.
   - Las columnas de la tabla deben ser exactamente: 
     1. "Nivel de Riesgo"
     2. "Rango de Liquidez Corriente" (usa notación matemática clara como >= o < para evitar vacíos)
     3. "Condición de Cuentas por Pagar (DPO)"
     4. "Excepciones / Mitigantes Admitidos"
     5. "Soporte y Evidencia Documental Obligatoria"

   Aquí tienes las reglas de negocio de entrada que debes procesar:
   [REGLAS DE NEGOCIO]
   - Se considera que una empresa tiene una salud óptima si su ratio de liquidez corriente es superior o igual a 1.60 y sus días de cuentas por pagar (DPO) no superan los 35 días. Deben presentar estados financieros auditados completos.
   - En situaciones donde la liquidez corriente caiga por debajo de 1.60 pero se mantenga arriba o igual de 1.15, se le considera en observación. No obstante, si sus DPO están entre 36 y 60 días, se clasifica en esta zona de atención intermedia. Se requiere balance firmado por contador y el último reporte tributario.
   - Si la liquidez corriente es inferior a 1.15, o sus DPO rebasan los 60 días, pasa de inmediato a categoría crítica.
   - Excepciones al nivel crítico: Si la empresa deudora cuenta con un aval corporativo incondicional firmado por una casa matriz con calificación grado de inversión (BBB- o superior), se le puede reclasificar a nivel intermedio, siempre y cuando se adjunte el contrato de fianza legalizado y el reporte de calificación de la matriz con menos de 60 días de antigüedad.
   - Excepciones al nivel intermedio: Empresas estratégicas de infraestructura que cuenten con contratos públicos vigentes por más de 5 años pueden exceptuarse del ratio de liquidez si adjuntan el acta de adjudicación oficial del contrato.
   [/REGLAS DE NEGOCIO]

   Asegúrate de deducir de forma lógica los nombres lógicos de las tres categorías de riesgo (Bajo, Medio, Alto) basados en las descripciones (óptima, observación, crítica).
   ```

3. Envía el prompt y espera a que Copilot procese la información y genere el bloque de código Markdown correspondiente.

*Resultado esperado:* Una tabla estructurada en Markdown que contiene tres filas perfectamente delimitadas (Riesgo Bajo, Riesgo Medio, Riesgo Alto), con rangos matemáticos limpios (por ejemplo: `Ratio >= 1.60`, `1.15 <= Ratio < 1.60`, `Ratio < 1.15`) y con sus excepciones y evidencias claramente asignadas a la fila correspondiente.

*Verificación:* Revisa visualmente que no existan intersecciones numéricas inválidas (como decir que 1.15 cae simultáneamente en dos filas distintas).

---

### Paso 3: Almacenamiento local de la matriz de rúbrica generada

**Objetivo:** Persistir el entregable del análisis en un formato de archivo portable dentro de tu directorio de trabajo local establecido en los prerrequisitos.

1. En la respuesta de Copilot, busca el bloque de texto con formato de tabla. Copilot suele proporcionar un botón rápido de "Copiar" (icono de doble hoja) en la parte superior o inferior del bloque de respuesta. Haz clic en él.
2. Abre tu editor de texto preferido (por ejemplo, Bloc de notas, VS Code o Notepad++).
3. Pega el contenido de la tabla copiada.
4. Guarda el archivo con el nombre `Rubrica_Riesgo.md` en la ruta absoluta:
   `C:\M365_Copilot_Labs\Rubrica_Riesgo.md`
5. (Opcional) Si deseas visualizar la tabla con formato enriquecido en Microsoft Word:
   * Selecciona el texto de la tabla pegado en tu editor de texto.
   * Abre un documento en blanco en Microsoft Word para Enterprise.
   * Pega el contenido. Word interpretará automáticamente la estructura Markdown y dibujará una tabla de Office nativa.
   * Guarda este archivo como `Rubrica_Riesgo.docx` en el mismo directorio.

*Resultado esperado:* Archivo de salida `Rubrica_Riesgo.md` o `Rubrica_Riesgo.docx` almacenado correctamente en el disco duro local.

*Verificación:* Abre la consola de PowerShell y ejecuta el siguiente comando de verificación para validar la presencia física y peso del archivo:
```powershell
Get-Item -Path "C:\M365_Copilot_Labs\Rubrica_Riesgo.md"
```

---

## Validación y Pruebas

Para garantizar la robustez metodológica de la rúbrica generada y descartar alucinaciones de la inteligencia artificial, realizaremos una prueba de validación utilizando un caso de prueba de límite y un escenario de datos contradictorios (caso adversarial).

### Prueba 1: Evaluación de Caso Límite
Envía el siguiente prompt a la misma sesión de Copilot para comprobar si aplica la rúbrica de forma consistente y unívoca:

```text
Caso de Prueba 1:
- Empresa: Constructora Alfa S.A.
- Ratio de Liquidez Corriente: 1.15
- DPO: 35 días
- Documentación presentada: Balance firmado por contador público, declaración de impuestos reciente. Sin contratos públicos adicionales.

Según la rúbrica que acabas de diseñar, ¿en qué nivel exacto de riesgo debe clasificarse a Constructora Alfa S.A.? Justifica brevemente tu respuesta analizando los límites de cada condición.
```

**Resultado Esperado de la Prueba 1:**
Copilot debe clasificar a la Constructora Alfa S.A. en **Riesgo Medio** (u "Observación"). 
*Justificación técnica:* Aunque sus DPO de 35 días corresponden a un nivel de riesgo Bajo, su ratio de liquidez está en el límite exacto inferior de la categoría de Riesgo Medio ($\ge 1.15$ y $< 1.60$). Dado que en metodologías de riesgos prima el principio de prudencia (el riesgo se define por el factor más débil a menos que exista un mitigante explícito), la clasificación general es Medio.

---

### Prueba 2: Caso Adversarial (Falta de Evidencia y Datos Contradictorios)
Envía este segundo escenario diseñado para desafiar la lógica de Copilot:

```text
Caso de Prueba 2 (Adversarial):
- Empresa: Logística Omega S.A.
- Ratio de Liquidez Corriente: 0.95 (Nivel Crítico)
- DPO: 28 días
- Situación de excepción: Alegan tener un aval verbal de su casa matriz "Holding Internacional S.A." (Calificación A+), pero no han adjuntado ningún documento legalizado de fianza en el expediente, argumentando que se encuentra en trámite de firmas.

Determina el nivel de riesgo final para Logística Omega S.A. indicando el impacto de la falta de evidencia formal de soporte de acuerdo con las reglas de la rúbrica.
```

**Resultado Esperado de la Prueba 2:**
Copilot debe clasificar de manera categórica a Logística Omega S.A. en **Riesgo Alto (Crítico)**.
*Justificación técnica:* A pesar del argumento del aval y sus óptimos días de pago (28 días), la liquidez corriente se encuentra muy por debajo del umbral de seguridad ($0.95 < 1.15$). La excepción de reclasificación no puede ser aplicada porque no existe soporte físico del "contrato de fianza legalizado" en el expediente de crédito. La rúbrica exige de forma obligatoria la presencia de la evidencia documental para activar cualquier mitigante.

---

## Solución de Problemas

Aquí encontrarás soluciones a los dos problemas comunes más frecuentes durante la ejecución de este laboratorio:

### Problema 1: Copilot genera la rúbrica en formato de lista de texto continuo en lugar de una tabla de Markdown
*   **Síntoma:** El asistente devuelve la información estructurada en secciones con viñetas u oraciones narrativas compactas, lo que dificulta su exportación directa a hojas de cálculo.
*   **Causa:** Sesgo en la interpretación del prompt debido a una carga previa en el contexto de la conversación o una variación interna de los pesos de generación del modelo.
*   **Solución:** Introduce una instrucción correctiva directa en el chat activo:
    ```text
    "Modifica tu última respuesta. Es obligatorio que conviertas toda la información extraída a un formato de tabla Markdown. No uses texto plano para describir los niveles. Utiliza las columnas especificadas en el prompt inicial."
    ```

### Problema 2: El ratio de liquidez límite (ej. 1.15 o 1.60) se asigna simultáneamente a dos niveles de riesgo
*   **Síntoma:** Copilot redacta los rangos con descripciones ambiguas como "Riesgo Medio: de 1.15 a 1.60" y "Riesgo Bajo: de 1.60 a más", dejando el valor exacto de 1.60 en una zona de indefinición lógica.
*   **Causa:** Incumplimiento parcial de la restricción lógica MECE por parte del motor lingüístico.
*   **Solución:** Solicita el ajuste matemático inmediato con el siguiente prompt correctivo:
    ```text
    "Corrige la tabla de la rúbrica. Asegúrate de que los rangos numéricos de liquidez utilicen corchetes, paréntesis o signos de desigualdad estrictos (ej. >= 1.60 para Bajo, y >= 1.15 y < 1.60 para Medio). Ningún número debe poder clasificarse en dos categorías a la vez."
    ```

---

## Limpieza

1. Si utilizaste un editor de texto o Microsoft Word local para dar formato, asegúrate de guardar los cambios finales en el archivo `C:\M365_Copilot_Labs\Rubrica_Riesgo.md` y cierra la aplicación.
2. Limpia el historial de la sesión del chat de Copilot haciendo clic en el botón de "Nuevo tema" (icono de escoba o pincel en la parte inferior izquierda de la caja de diálogo) para evitar que este contexto de reglas financieras afecte tus próximas tareas de análisis en el navegador.
3. Cierra la pestaña de Microsoft Edge en caso de haber finalizado tus actividades del día.

---

## Resumen

En este laboratorio, has transformado exitosamente declaraciones narrativas de políticas operativas dispersas en una herramienta metodológica de toma de decisiones financieras robusta y estandarizada. Mediante el uso de directrices estructuradas en Microsoft 365 Copilot, lograste:
*   Extraer variables financieras clave (como el Ratio de Liquidez Corriente y el DPO) asociándolas a categorías específicas de riesgo.
*   Diseñar una matriz de decisión lógica aplicando reglas de exclusión mutua para evitar vacíos regulatorios internos.
*   Asignar mitigantes, excepciones operativas y sus respectivos soportes documentales obligatorios dentro de un formato tabular altamente portable (Markdown).
*   Someter la rúbrica a pruebas de estrés lógico mediante casos límites y escenarios adversariales que validan el rigor metodológico del modelo obtenido.

Este entregable (`Rubrica_Riesgo.md`) servirá de base estructurada en los siguientes módulos para la evaluación automatizada de expedientes de crédito reales e interacciones avanzadas de auditoría corporativa.

---

# Práctica: Probar y refinar la rúbrica con escenarios ficticios para identificar inconsistencias y proponer ajustes

## Metadatos

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 10 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel Bloom** | Analizar (Analyze) |

## Descripción General

Este laboratorio práctico tiene como finalidad someter a una rigurosa prueba de esfuerzo ("stress test") la rúbrica de clasificación de riesgo de liquidez y solvencia corporativa desarrollada en la sesión previa. Utilizando el asistente de inteligencia artificial Microsoft 365 Copilot, simularás escenarios financieros ficticios que presentan contradicciones inherentes y ambigüedades en sus métricas. A través de un análisis iterativo guiado por prompts avanzados, identificarás zonas grises de decisión y vacíos normativos en la rúbrica original para luego instrumentar a Copilot en el blindaje y refinamiento lógico de la matriz de decisión, asegurando que sea matemáticamente precisa y de aplicación unívoca.

## Objetivos de Aprendizaje

Al finalizar este laboratorio, serás capaz de:
- [ ] Someter una rúbrica de clasificación de riesgos financieros a pruebas de estrés lógicas empleando simulaciones de escenarios extremos en Copilot.
- [ ] Diagnosticar inconsistencias, superposiciones métricas y vacíos documentales mediante prompts de análisis crítico de datos.
- [ ] Refinar y blindar de forma iterativa los umbrales de decisión y reglas de negocio de una matriz sin alterar las políticas fundamentales de la organización.

## Prerrequisitos

Para completar con éxito este laboratorio, debes cumplir con los siguientes requisitos:
- **Conocimientos teóricos:** Comprensión del diseño de rúbricas de riesgo, operadores lógicos y ratios de liquidez/solvencia.
- **Acceso a tecnologías:** 
  - Cuenta de usuario organizacional activa con licenciamiento para **Microsoft 365 Copilot Premium**.
  - Acceso a la interfaz web de Copilot Chat a través de un navegador moderno compatible.

## Entorno de Laboratorio

Este laboratorio se ejecuta directamente en el entorno de chat de Microsoft 365 Copilot y de manera complementaria en el editor de texto Word.

| Componente | Versión / Edición | Configuración / Licencia | Enlace de Descarga / Oficial |
| :--- | :--- | :--- | :--- |
| **Sistema Operativo** | Windows 11 Enterprise (64-bit) / macOS Sonoma 14.4 (o superior) | Estándar corporativo | [ENLACE OFICIAL] |
| **Navegador Web** | Microsoft Edge (Versión 128.0.2739.42 o superior) | Con sesión corporativa iniciada | [ENLACE OFICIAL] |
| **Asistente de IA** | Microsoft 365 Copilot Premium (Chat de Copilot) | Licencia Add-on M365 activa | [ENLACE OFICIAL] |
| **Procesador de Textos** | Microsoft Word para Enterprise (Versión 2408, Compilación 17928.20114) | Canal Mensual Empresarial | [ENLACE OFICIAL] |

> **Nota de Configuración**: No se requiere de la descarga de ningún set de datos externo previo. Los datos de la rúbrica base y los casos sintéticos de estrés se suministran de manera directa y autocontenida en las instrucciones de este laboratorio para asegurar el cumplimiento regulatorio de protección de datos.

## Instrucciones Paso a Paso

### Paso 1: Configurar la sesión de Copilot e ingresar la rúbrica base

**Objetivo**: Cargar en el contexto de memoria temporal de Microsoft 365 Copilot la estructura y condiciones de la rúbrica base que se va a someter a evaluación.

**Instrucciones**:

1. Abre tu navegador web Microsoft Edge y navega hacia el portal oficial de chat corporativo protegido de Microsoft 365 Copilot: [https://copilot.microsoft.com](https://copilot.microsoft.com).
2. Asegúrate de haber iniciado sesión con las credenciales de tu cuenta de la organización para habilitar la protección de datos comerciales integrada.
3. Copia textualmente la siguiente instrucción estructurada (prompt) que define la rúbrica base y pégala en el cuadro de entrada de chat de Copilot:

```text
Actúa como un Auditor de Riesgos Senior y Especialista en Control de Calidad Financiera. A continuación, te presento la rúbrica de clasificación de riesgo de liquidez y solvencia corporativa que construimos en la sesión anterior. Léela con atención, memoriza sus variables, umbrales y excepciones, pero NO generes una nueva rúbrica aún. Confirma que la has comprendido y que estás listo para someterla a pruebas de esfuerzo lógico.

--- RÚBRICA BASE ---
| Nivel de Riesgo | Umbral de Liquidez Corriente | Condición de DPO (Días Cuentas por Pagar) | Excepciones | Evidencia Requerida |
| :--- | :--- | :--- | :--- | :--- |
| **Riesgo Bajo (Aceptable)** | >= 1.50 | <= 45 días | Ninguna. Es el estándar operativo mínimo requerido. | Balance General Auditado del último periodo y Reporte de Antigüedad de Cuentas por Pagar. |
| **Riesgo Medio (Alerta)** | >= 1.10 y < 1.50 | De 46 a 75 días | Proveedores estratégicos con contratos plurianuales firmados y aprobados por la Dirección de Compras. | Balance General interino firmado por Contador Público y Copia del Contrato de Suministro vigente. |
| **Riesgo Alto (Crítico)** | < 1.10 | > 75 días | Proveedores que cuenten con una Carta de Garantía Corporativa incondicional emitida por una matriz calificada como Grado de Inversión. | Balance General del periodo actual, Reporte de Buró de Crédito comercial con antigüedad no mayor a 30 días, y Carta de Garantía original si aplica. |
--- FIN DE RÚBRICA ---
```

4. Presiona la tecla `Enter` o haz clic en el botón de enviar mensaje.

**Resultado esperado**: Copilot debe procesar el mensaje y responder confirmando la asimilación de las tres categorías de riesgo (Bajo, Medio, Alto) y sus correspondientes variables cuantitativas y cualitativas de soporte. El tono de la respuesta debe denotar preparación para iniciar las pruebas lógicas.

**Verificación**: Revisa el mensaje de salida de Copilot y confirma que enumere de forma sucinta los límites de Liquidez Corriente y DPO establecidos para validar que leyó la información correctamente.

---

### Paso 2: Ejecutar la prueba de esfuerzo con escenarios financieros extremos y ambiguos

**Objetivo**: Someter la rúbrica a un conjunto de casos sintéticos complejos y contradictorios para mapear vacíos de control, solapamiento de umbrales y deficiencias normativas en la toma de decisiones.

**Instrucciones**:

1. En el mismo chat activo de Copilot, ingresa la siguiente instrucción de análisis crítico para evaluar tres escenarios sintéticos extremos de estrés:

```text
Ahora, procesa y clasifica los siguientes tres escenarios sintéticos extremos utilizando estrictamente la rúbrica anterior. Tu objetivo es evaluar si la rúbrica genera contradicciones, zonas grises (donde un caso podría caer en dos categorías a la vez o en ninguna) o fallas de cobertura de riesgo.

- Escenario A (Conflicto de Ratios): Un proveedor clave tiene un Ratio de Liquidez Corriente de 1.85 (Riesgo Bajo), pero sus días de cuentas por pagar (DPO) son de 82 días (Riesgo Alto).
- Escenario B (Excepción sin Evidencia): Un proveedor estratégico tiene un Ratio de Liquidez de 1.05 (Riesgo Alto), un DPO de 50 días (Riesgo Medio), cuenta con un contrato plurianual firmado por Compras (Excepción de Riesgo Medio), pero no ha entregado el Balance General auditado ni interino debido a que está en proceso de reestructuración corporativa.
- Escenario C (El Vacío del Umbral Exacto): Un proveedor tiene una Liquidez Corriente exactamente igual a 1.10 y un DPO de 45 días. ¿Cae de manera unívoca y exacta en un solo nivel, o hay ambigüedad matemática en los límites declarados?

Analiza cada caso detalladamente. Identifica qué vacíos de control, solapamientos de clasificación o ambigüedades documentales expone cada escenario.
```

2. Haz clic en el botón de enviar mensaje y aguarda a que Copilot complete el diagnóstico deductivo.

**Resultado esperado**: El asistente entregará un análisis estruturado caso por caso. Debe apuntar que el *Escenario A* sufre de "parálisis por análisis" debido a la falta de una regla de desempate o priorización entre variables; que el *Escenario B* muestra una evasión de controles ya que se aprovecha una excepción operativa sin validar la documentación contable; y que el *Escenario C* puede evidenciar un vacío de cobertura si los intervalos matemáticos no son mutuamente excluyentes (por ejemplo, si DPO=45 cae exactamente en la frontera difusa entre Bajo y Medio).

**Verificación**: Confirma que el análisis de Copilot plantee las fallas de coherencia interna y sugiera explícitamente la necesidad de actualizar la lógica de la rúbrica antes de que sea implementada.

---

### Paso 3: Optimizar y blindar la rúbrica mediante refinamiento iterativo

**Objetivo**: Aplicar ajustes lógicos a la rúbrica empleando Copilot para blindar su arquitectura decisional mediante reglas de desempate claras, penalizaciones documentales y precisión matemática sin alterar las bases del negocio.

**Instrucciones**:

1. Copia y envía el siguiente prompt interactivo en la misma ventana de conversación para actualizar y blindar estructuralmente la rúbrica:

```text
Excelente análisis de vulnerabilidades. Ahora, vamos a blindar estructuralmente la rúbrica para que sea completamente MECE (Mutuamente Excluyente y Colectivamente Exhaustiva) y libre de inconsistencias lógicas. Genera una nueva tabla de rúbrica optimizada que implemente las siguientes mejoras:

1. Regla de Desempate (Priorización): Si un proveedor presenta métricas financieras clasificadas en diferentes niveles de riesgo, se le asignará de forma obligatoria la clasificación de riesgo MÁS ALTA detectada (Principio de Prudencia Conservadora).
2. Control de Evidencia Estricto (Penalización): Si no se presenta la totalidad de la evidencia documental obligatoria correspondiente a su nivel, el caso se reclasifica automáticamente un nivel arriba (Riesgo superior).
3. Precisión Matemática Absoluta: Asegúrate de que los rangos de liquidez y DPO utilicen operadores lógicos que eviten solapamientos (ejemplo: Liquidez >= 1.50 es Riesgo Bajo; >= 1.10 y < 1.50 es Riesgo Medio; < 1.10 es Riesgo Alto).
4. Condición para Excepciones: Las excepciones operativas aprobadas solo serán válidas si se acompaña con el 100% de la evidencia de soporte requerida para esa excepción específica en un plazo de auditoría.

Presenta la rúbrica final en una tabla de Markdown estructurada y clara, seguida de una sección titulada "Reglas de Oro de Aplicación" para el analista de riesgos.
```

2. Ejecuta el envío de la instrucción en Copilot.

**Resultado esperado**: Copilot debe devolver una rúbrica en formato de tabla de Markdown con los rangos numéricos matemáticamente acotados (sin zonas de superposición ni vacíos en los límites decimales). Adicionalmente, incorporará las directrices de desempate basadas en el Principio de Prudencia Conservadora y la penalización inmediata por ausencia de evidencias documentales físicas en la sección final.

**Verificación**: Compara la tabla generada con la inicial y comprueba que las restricciones lógicas y los operadores de comparación matemáticos resuelvan de manera infalible la asignación para cualquier combinación de datos.

---

## Validación y Pruebas

Para comprobar el blindaje absoluto y la precisión matemática de la rúbrica generada, es preciso someterla a una prueba automatizada en Copilot frente a un escenario de conflicto deliberado (adversarial) que combine información contradictoria y omisiones intencionadas de documentación:

### Caso de Prueba Adversarial (Información en Conflicto y Evidencia Faltante)
*   **Proveedor a Evaluar:** *Distribuidora Industrial Alianza S.A.* (Proveedor Estratégico con Contrato Plurianual en regla).
*   **Métrica 1 (Liquidez Corriente):** 1.25 (Ubicación teórica: Riesgo Medio).
*   **Métrica 2 (DPO):** 40 días (Ubicación teórica: Riesgo Bajo).
*   **Evidencia de soporte entregada:** Únicamente Reporte de Antigüedad de Cuentas por Pagar. No se entregó el "Balance General interino firmado por Contador Público".

### Ejecución de la Validación:
1. Copia y pega el siguiente prompt en el chat activo con Copilot para validar la consistencia:

```text
Aplica la NUEVA RÚBRICA OPTIMIZADA que acabas de generar al siguiente caso de prueba adversarial para validar la resiliencia del modelo:

- Proveedor: Distribuidora Industrial Alianza S.A. (Catalogado como Proveedor Estratégico con Contrato Plurianual aprobado por la Dirección).
- Liquidez Corriente: 1.25
- DPO (Días Cuentas por Pagar): 40 días
- Evidencia entregada: Solo adjunta el "Reporte de Antigüedad de Cuentas por Pagar". NO entrega el Balance General interino ni firmado debido a retrasos administrativos.

Deduce la clasificación de riesgo final aplicando rigurosamente:
1. La clasificación inicial de cada indicador.
2. La regla de desempate (priorización).
3. El impacto de la omisión documental obligatoria (penalización).

Detalla los pasos analíticos de tu deducción y concluye con la clasificación definitiva del proveedor.
```

2. Ejecuta la validación y analiza la respuesta detallada de Copilot.

### Resultado de Validación Esperado:
Copilot debe clasificar de manera inequívoca al proveedor en **Riesgo Alto (Crítico)**, justificando paso a paso de la siguiente forma:
*   **Análisis de métricas inicial:** Su DPO (40 días) apunta a Riesgo Bajo, pero su Liquidez (1.25) lo ubica en Riesgo Medio.
*   **Aplicación de Desempate:** La regla de priorización indica que prevalece el riesgo más alto, asignándole preliminarmente la categoría de **Riesgo Medio**.
*   **Evaluación Documental (Excepción y Penalización):** Aunque califica para la excepción de proveedor estratégico (contrato plurianual), no entregó el Balance General interino firmado (evidencia obligatoria para el nivel Medio). De acuerdo con la regla de control documental estricto, la omisión de la evidencia obligatoria provoca una penalización de reclasificación automática de un nivel hacia arriba.
*   **Clasificación Final Definitiva:** **Riesgo Alto (Crítico)**.

Esta validación demuestra que la rúbrica ha sido blindada con éxito ante fallas de documentación interna y conflictos métricos.

---

## Solución de Problemas

A continuación, se describen dos incidencias comunes identificadas durante el proceso de refinamiento de rúbricas con inteligencia artificial y sus respectivas soluciones operativas:

1. **Sintoma:** *Copilot realiza un "promedio" aritmético o suaviza el nivel de riesgo en lugar de aplicar la regla de desempate estricta de máxima prudencia.*
   * **Causa:** Por defecto, los modelos de lenguaje tienden a buscar consensos equilibrados o soluciones "suaves" para evitar penalizaciones drásticas de manera intuitiva.
   * **Solución:** Envía un prompt correctivo (instrucción directa) que anule esta flexibilidad interpretativa: 
     `"Atención: En análisis financiero no está permitido realizar promedios ni interpolaciones de riesgo. Aplica de manera absoluta el Principio de Prudencia Conservadora: un solo parámetro fuera del rango aceptable arrastra irrevocablemente a toda la entidad a la categoría de riesgo más alta detectada."`

2. **Síntoma:** *Copilot pierde el formato de tabla de Markdown estructurada o los operadores lógicos durante la discusión de las excepciones.*
   * **Causa:** En chats prolongados o de alta densidad conceptual, la memoria de formato del chat puede degradarse, priorizando el texto plano o viñetas conversacionales.
   * **Solución:** Reorganiza el formato solicitando específicamente la reconstrucción de la tabla mediante la siguiente instrucción directa: 
     `"Reescribe la rúbrica optimizada resultante y muéstrala exclusivamente en una tabla de Markdown bien estructurada, asegurando que las columnas de 'Nivel de Riesgo', 'Umbral de Liquidez Corriente' y 'DPO' mantengan de forma explícita los operadores lógicos '<', '>', '<=' y '>='."`

---

## Limpieza

Dado que la totalidad de este laboratorio de 10 minutos se desarrolla en la interfaz interactiva de Microsoft 365 Copilot, no se generan consumos de recursos virtuales ni cargos recurrentes de computación en la nube pública. Para mantener los estándares de higiene digital corporativa, sigue estos pasos:

1. Selecciona la tabla de la rúbrica blindada generada por Copilot en el Paso 3. Copia el texto y pégalo en un documento de Microsoft Word para Enterprise limpio.
2. Guarda el documento de forma local en la estación de trabajo bajo la ruta del directorio predefinido: `C:\M365_Copilot_Labs\Rubrica_Optimizada_Sometida_a_Prueba.docx`. Esto servirá como insumo analítico para futuros módulos incrementales de la capacitación.
3. Haz clic en el botón de **"Nuevo tema"** (representado generalmente por un icono de escoba o una burbuja de diálogo limpia) ubicado al costado izquierdo de la barra de prompts en `copilot.microsoft.com` para limpiar el contexto conversacional. Esto evitará que las variables y penalizaciones de esta simulación afecten la precisión de las respuestas en tareas de análisis posteriores.

---

## Resumen

En este laboratorio práctico de alta complejidad, has ejecutado con éxito las siguientes tareas:
*   **Prueba de Esfuerzo de Rúbrica:** Sometiste una matriz clásica de clasificación a tres escenarios sintéticos extremos, exponiendo vacíos operacionales de decisión, falta de jerarquía entre variables (liquidez vs. DPO) y vulnerabilidad documental ante excepciones.
*   **Blindaje Semántico y Lógico:** Empleaste directrices estructuradas en Copilot para forzar que la matriz cumpla rigurosamente las normas MECE (Mutuamente Excluyentes y Colectivamente Exhaustivas), delimitando de forma precisa los umbrales numéricos.
*   **Implementación de Reglas de Control:** Estableciste prioridades de máxima prudencia para desempates lógicos y penalizaciones de clasificación automáticas en ausencia de evidencias, garantizando que el motor de evaluación de riesgos sea robusto, auditable y completamente trazable.
