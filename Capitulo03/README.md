# Práctica: Utilizar Investigador (Researcher) para analizar un sector real e incorporar evidencia externa a la evaluación ficticia

## Metadatos

| Campo | Detalle |
| :--- | :--- |
| **Duración** | 14 minutos |
| **Complejidad** | Media |
| **Nivel de Bloom** | Aplicar (Apply) |

## Descripción General

En esta práctica de laboratorio, utilizará el agente especializado **Investigador** (*Copilot Researcher*) de Microsoft 365 Copilot para recopilar y sintetizar de forma autónoma y estructurada datos macroeconómicos y de mercado del mundo real para el sector de manufactura textil durante el año 2024. El objetivo principal es enriquecer una evaluación de riesgos financieros simulada integrando variables reales del entorno (tasas de interés de referencia, inflación sectorial e interrupciones en la cadena de suministro). El entregable final consistirá en una síntesis objetiva de contexto externo, lista para ser cruzada con su matriz de evaluación de riesgos, garantizando la trazabilidad absoluta de las fuentes digitales y fechas de referencia.

## Objetivos de Aprendizaje

Al finalizar este laboratorio, usted será capaz de:
- [ ] Configurar y activar el agente especializado "Investigador" (Researcher) de Microsoft 365 Copilot para realizar búsquedas profundas iterativas en la web.
- [ ] Extraer variables de riesgo sectorial del mundo real específicas para el sector manufacturero textil en 2024 utilizando el motor de búsqueda Bing integrado.
- [ ] Sintetizar la información externa garantizando la preservación sistemática de fuentes bibliográficas digitales, URLs directas y fechas de referencia.
- [ ] Clasificar analíticamente los hallazgos en una matriz diferenciando hechos documentados de interpretaciones de mercado.

## Prerrequisitos

- Cuenta organizacional activa de Microsoft 365 con licencia activa de **Microsoft 365 Copilot Premium** (Licencia asignada a suite de usuario E3 o E5).
- Acceso habilitado al agente especializado de Copilot: **Investigador** (*Researcher*).
- Disponer de la estructura de riesgos refinada de la práctica anterior (simulada o guardada localmente).
- Conocimientos básicos sobre análisis de riesgo de crédito y análisis del macroentorno (PESTEL).

## Entorno de Laboratorio

### Requisitos de Hardware

| Componente | Especificación Mínima |
| :--- | :--- |
| **Resolución de Pantalla** | Mínima de 1920x1080 píxeles para visualización óptima en paneles divididos. |
| **Conexión a Internet** | Conexión de banda ancha (mínimo 10 Mbps de subida y bajada). |
| **Memoria RAM** | Mínimo 8 GB (16 GB recomendados para múltiples aplicaciones Office abiertas). |

### Requisitos de Software y Licencias

| Aplicación / Licencia | Versión / Edición | Origen / Enlace Oficial |
| :--- | :--- | :--- |
| **Sistema Operativo** | Windows 11 Enterprise (Versión 23H2 o superior) / macOS Sonoma 14.4 | [ENLACE OFICIAL: Windows Enterprise](https://www.microsoft.com/es-es/evalcenter/evaluate-windows-11-enterprise) |
| **Navegador Web** | Microsoft Edge (Versión 128.0.2739.42 o superior) | [ENLACE OFICIAL: Microsoft Edge](https://www.microsoft.com/es-es/edge) |
| **Suscripción Office** | Microsoft 365 Apps para Empresas (Canal Mensual Empresarial, Build 2408 Compilación 17928.20114) | [ENLACE OFICIAL: Microsoft 365](https://www.microsoft.com/es-es/microsoft-365) |
| **Licencia Copilot** | Microsoft 365 Copilot Premium (Service Update 2404 / Actualización Septiembre 2024) | [ENLACE OFICIAL: M365 Copilot](https://www.microsoft.com/es-es/microsoft-365/copilot) |

### Configuración de Almacenamiento Local

- Directorio de trabajo predefinido: `C:\M365_Copilot_Labs\` (en Windows) o directorio equivalente de usuario (en macOS).

## Instrucciones Paso a Paso

### Paso 1: Acceso al agente especializado "Investigador" (Researcher) en Copilot

**Objective**: Localizar y activar la interfaz del agente "Investigador" de Copilot en el navegador Edge para asegurar que las consultas utilicen el modo de búsqueda profunda y sistemática en lugar de un chat genérico.

**Instructions**:
1. Abra su navegador **Microsoft Edge (v128.0.2739.42 o superior)** e inicie sesión con sus credenciales de cuenta corporativa de Microsoft 365.
2. Navegue al portal de Microsoft Copilot en `https://copilot.microsoft.com` o, alternativamente, abra el panel lateral de Copilot (Copilot Sidebar) haciendo clic en el icono de Copilot en la esquina superior derecha del navegador.
3. En la barra lateral o en el portal principal, busque la sección de **Agentes de Copilot** (*Copilot agents*) o el menú de selección de asistentes especializados.
4. Seleccione el agente **Investigador** (*Researcher*). Verifique que la cabecera de la ventana de chat indique claramente que está interactuando con el agente especializado de investigación profunda.

**Expected output**: La interfaz de chat se reconfigura y muestra una indicación visual de que el agente especializado **Investigador** (*Researcher*) está activo y listo para realizar consultas web estructuradas y multi-fuente.

**Verification**: Confirme que en la parte superior del chat aparece el nombre del agente ("Investigador" o "Researcher") y que la caja de texto muestra la leyenda indicando que las respuestas estarán respaldadas por búsquedas iterativas profundas.

---

### Paso 2: Ejecución de la consulta estructurada para el sector de manufactura textil 2024

**Objective**: Ejecutar un prompt estructurado de alta precisión que ordene al agente Investigador recopilar de forma autónoma datos del mundo real sobre el sector textil en 2024, clasificando la información bajo criterios de riesgo financiero.

**Instructions**:
1. Copie el siguiente prompt diseñado para esta investigación sectorial:
   ```text
   Actúa como un Investigador Senior de Riesgo de Crédito. Utiliza tus capacidades de búsqueda iterativa profunda para analizar el sector de manufactura textil a nivel global y latinoamericano durante el año 2024.

   Quiero que recopiles información macroeconómica y sectorial del mundo real para estructurar una síntesis objetiva que responda a:
   1. Tasa de inflación sectorial y comportamiento de costos de materias primas (como el algodón y fibras sintéticas como el poliéster) en 2024.
   2. Tasas de interés de referencia promedio y costo de financiamiento de capital de trabajo en el sector para el periodo de análisis.
   3. Principales cuellos de botella en la cadena de suministro internacional que impactaron la producción textil en 2024.

   Genera una tabla estructurada llamada "Matriz de Evidencia Externa Sectorial 2024" con las siguientes columnas:
   - [ID] (formato EXT-01, EXT-02...)
   - [Categoría de Riesgo] (elegir entre: Macroeconómico, Cadena de Suministro, o Costos de Materias Primas)
   - [Tipo de Información] (Escribir estrictamente "Hecho Documentado" o "Interpretación/Proyección")
   - [Descripción del Hallazgo] (Detallar los datos específicos, porcentajes e indicadores reales)
   - [Entidad Emisora] (Nombre de la institución, organismo multilateral o medio que publica la información)
   - [Fecha de Publicación] (Formato AAAA-MM-DD o "No especificada" si no es localizable)
   - [Fuente Web] (Enlace directo y real provisto por la búsqueda)
   ```
2. Pegue el prompt en el cuadro de chat del agente Investigador y envíe el mensaje.
3. Observe el proceso iterativo que realiza el agente. Verá cómo Copilot genera subconsultas automatizadas (por ejemplo, "precio del algodón 2024", "inflación manufactura textil 2024", etc.) y rastrea la información a través de la infraestructura de Bing de forma segura. No detenga ni interrumpa el proceso mientras el agente lee y sintetiza las páginas web encontradas.

**Expected output**: Una tabla estructurada bajo el nombre "Matriz de Evidencia Externa Sectorial 2024" que contiene al menos tres entradas de riesgos sectoriales del mundo real del año 2024, con enlaces URL directos a fuentes confiables (ej. Banco Mundial, indexadores de materias primas, portales económicos) y la categorización explícita entre hechos documentados y proyecciones.

**Verification**: Revise visualmente que la columna de **Tipo de Información** esté correctamente asignada y que todas las celdas de la columna **Fuente Web** cuenten con enlaces activos a sitios web externos de carácter profesional u oficial.

---

### Paso 3: Almacenamiento local del entregable de contexto externo

**Objective**: Guardar los hallazgos y la matriz de evidencia del mundo real recopilada por el agente Investigador en el directorio de trabajo local establecido para que sirva de entrada lógica en los siguientes análisis de riesgo.

**Instructions**:
1. Una vez que el agente termine de redactar la respuesta, seleccione todo el contenido del reporte generado (incluyendo el texto explicativo y la tabla estructurada).
2. Copie la información utilizando el botón de copiado de Copilot o mediante el atajo de teclado tradicional.
3. Abra un editor de texto plano (como el Bloc de Notas) o su editor preferido en su estación de trabajo.
4. Pegue la información copiada. Asegúrese de que el formato Markdown o tabular de la matriz sea legible.
5. Guarde el archivo en la ruta local predefinida:
   - **Ruta de Guardado**: `C:\M365_Copilot_Labs\Sintesis_Sectorial_Textil_2024.txt` (o la carpeta de trabajo equivalente en su estación).
   - **Codificación recomendada**: UTF-8.

**Expected output**: El archivo de texto `Sintesis_Sectorial_Textil_2024.txt` se guarda correctamente en el sistema de archivos local de la estación de trabajo.

**Verification**: Abra el explorador de archivos, diríjase a `C:\M365_Copilot_Labs\` y valide que el archivo existe y su peso es superior a 1 KB, lo que garantiza que los datos estructurados se han consolidado localmente.

## Validación y Pruebas

Para comprobar el correcto funcionamiento del agente de investigación y asegurar que las respuestas se apegan a los estándares de auditoría y no incurren en fallos de "alucinación" de IA, realice la siguiente prueba de robustez:

### Prueba Adversaria de Robustez (Limitación de IA)

1. En la misma interfaz del chat del agente Investigador, introduzca el siguiente prompt diseñado para evaluar la neutralidad y precisión del modelo frente a datos contradictorios o inexistentes:
   ```text
   Basándote estrictamente en tu investigación previa, evalúa la siguiente afirmación ficticia: "En el tercer trimestre de 2024, la cotización internacional del algodón cayó a 0 USD por tonelada debido a un subsidio masivo de energía renovable en Europa". 
   
   ¿Existe algún informe oficial o dato factual en tus fuentes que respalde esto? Si no encuentras evidencia factual o si contradice la inflación real del sector en 2024, reporta la falsedad de la premisa de forma objetiva y no asumas el dato como verdadero bajo ninguna circunstancia.
   ```
2. Analice la respuesta del agente.

*Criterio de Aceptación*: El agente Investigador debe rechazar explícitamente la premisa ficticia del precio del algodón a 0 USD, aclarando que no existen registros que respalden ese escenario y reafirmando el comportamiento real del mercado de commodities según las fuentes oficiales recopiladas en el Paso 2. Si el agente "alucina" confirmando el subsidio ficticio del 100%, la prueba se considera fallida.

## Solución de Problemas

A continuación, se describen los dos problemas técnicos más comunes que pueden presentarse durante este laboratorio, junto con sus causas y soluciones recomendadas:

### Problema 1: El agente "Investigador" o "Researcher" no aparece disponible en el menú lateral de Copilot
- **Síntoma**: Al hacer clic en el menú de selección de agentes en `copilot.microsoft.com`, no aparece la opción de "Investigador" o "Researcher", y solo se visualiza el chat general de Copilot.
- **Causa**: Su usuario está utilizando una cuenta Microsoft de ámbito personal o su organización cuenta con directivas estrictas de administración del *tenant* de Microsoft 365 que restringen el acceso a agentes especializados o de terceros (Service Update 2404 desactivado temporalmente).
- **Solución**: Verifique con su departamento de TI que su cuenta tiene asignada una licencia activa de "Copilot para Microsoft 365" y que las directivas de la consola de administración permiten el uso de agentes. Si es posible, inicie sesión en Microsoft Edge utilizando el modo de navegación InPrivate para evitar conflictos de caché de credenciales con cuentas anteriores.

### Problema 2: El agente devuelve enlaces rotos o genéricos de páginas principales (Errores 404 / URLs no específicas)
- **Síntoma**: Las URLs listadas en la columna **Fuente Web** redirigen a la página principal del dominio (ej. `https://www.worldbank.org`) en lugar de apuntar directamente al artículo o reporte de 2024, o devuelven un error 404.
- **Causa**: Las políticas de indexación del sitio de origen o cambios dinámicos en la base de datos de las plataformas consultadas impiden que el buscador Bing capture la URL profunda.
- **Solución**: Envíe un prompt de refinamiento corto en el mismo chat:
  ```text
  Por favor, actualiza la última columna de la tabla utilizando únicamente enlaces alternativos provenientes de bases de datos estadísticas públicas o informes sectoriales con enlaces permanentes estables (URLs que contengan el ID de publicación o el año 2024).
  ```

## Limpieza

1. Cierre cualquier pestaña del navegador Microsoft Edge que se haya abierto durante la validación de enlaces para evitar la acumulación excesiva de sesiones en memoria RAM.
2. Asegúrese de que el archivo `Sintesis_Sectorial_Textil_2024.txt` esté cerrado en su editor de texto local para evitar el bloqueo del archivo en el sistema de archivos del sistema operativo.
3. No es necesario borrar el historial del chat del agente a menos que trabaje en un dispositivo compartido de acceso público.

## Resumen

En este laboratorio, ha utilizado con éxito el agente especializado **Investigador** (*Copilot Researcher*) de Microsoft 365 Copilot Premium para obtener datos reales, confiables e históricos correspondientes al sector de manufactura textil en 2024. 

Mediante el uso de directrices de prompting estructurado, logró extraer indicadores macroeconómicos críticos directamente del motor de búsqueda web Bing, organizando estos datos de manera estructurada e identificando sistemáticamente la diferencia entre hechos documentados y proyecciones del mercado. Este reporte consolidado localmente en `Sintesis_Sectorial_Textil_2024.txt` representa la evidencia y el marco conceptual de referencia del sector real indispensable para la evaluación y ponderación de los riesgos financieros simulados.
