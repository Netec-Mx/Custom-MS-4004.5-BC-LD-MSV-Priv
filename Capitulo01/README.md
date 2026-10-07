# Práctica: Diseñar una estrategia de análisis para un expediente ficticio de alta volumetría con Copilot

## Metadatos

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 9 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar |

## Descripción General

En esta práctica de laboratorio, actuarás como un Analista Senior de Riesgos Financieros en un entorno corporativo. Utilizarás **Microsoft 365 Copilot Premium** en Microsoft Edge para diseñar una estrategia estructurada de análisis (denominada "Playbook de Prompts") para evaluar el expediente de un cliente corporativo ficticio de alta volumetría ("Soluciones Logísticas Mundiales S.A."). El objetivo principal es establecer una metodología reproducible que fragmente el análisis en bloques lógicos y asegure la trazabilidad estricta entre la fuente original, el hallazgo financiero y las reglas de negocio, previniendo la pérdida de contexto antes de realizar operaciones de cálculo masivo en las siguientes fases.

## Objetivos de Aprendizaje

Al finalizar este laboratorio, serás capaz de:
- [ ] Definir criterios de segmentación lógica para un expediente financiero de alta volumetría utilizando inteligencia artificial.
- [ ] Formular un "Playbook de Prompts" altamente estructurado, parametrizado y dividido por bloques documentales (cuantitativo, contractual y cumplimiento).
- [ ] Implementar instrucciones y restricciones dentro de los prompts para garantizar la trazabilidad tridimensional (Fuente-Hallazgo-Regla) y la detección automática de vacíos de información.

## Prerrequisitos

Para realizar este laboratorio, necesitas contar con:
- **Conocimientos teóricos**: Comprensión básica del framework de prompting para finanzas (Contexto, Instrucción, Restricciones y Formato de Salida).
- **Acceso a Entorno**: Una cuenta organizacional de Microsoft 365 activa con licencia asignada de **Microsoft 365 Copilot Premium**.
- **Navegador Web**: Microsoft Edge configurado con el perfil de trabajo correspondiente a la licencia.

## Entorno de Laboratorio

### Requisitos de Hardware y Software

| Componente | Especificación Técnica | Fuente Oficial |
| :--- | :--- | :--- |
| **Sistema Operativo** | Windows 11 Enterprise (Versión 23H2 o superior, 64-bit) o macOS Sonoma (v14.4 o superior) | [ENLACE OFICIAL](https://www.microsoft.com/software-download) |
| **Navegador** | Microsoft Edge (Versión 128.0.2739.42 o superior, 64-bit) | [ENLACE OFICIAL](https://www.microsoft.com/edge) |
| **Licenciamiento** | Licencia activa de Microsoft 365 Copilot Premium (M365 E3/E5 + Copilot Add-On) | [ENLACE OFICIAL](https://admin.microsoft.com/) |
| **Conexión Red** | Conexión a Internet de banda ancha (mínimo 10 Mbps de bajada/subida) | N/A |
| **Resolución** | Pantalla con resolución mínima de 1920x1080 píxeles | N/A |

### Configuración del Directorio de Trabajo

Durante este laboratorio, guardarás los artefactos generados en la siguiente ruta de tu sistema local:
- `C:\Capacitacion-Copilot\Casos-Finanzas\Modulos_1_4\` (Si utilizas macOS, utiliza una ruta equivalente en tu directorio de usuario, como `/Users/shared/Capacitacion-Copilot/Casos-Finanzas/Modulos_1_4/`).

## Instrucciones Paso a Paso

### Paso 1: Configurar el Entorno y Acceso a Copilot

**Objetivo**: Asegurar el acceso correcto al canal de datos protegido y empresarial de Microsoft 365 Copilot para garantizar la confidencialidad de la información ficticia que se simulará.

1. Abre tu navegador **Microsoft Edge** (Versión 128.0.2739.42 o superior).
2. Asegúrate de que has iniciado sesión con tu cuenta de trabajo u organización que tiene asignada la licencia de **Microsoft 365 Copilot Premium** (comprobando el avatar de la cuenta en la esquina superior izquierda del navegador).
3. Navega a la dirección oficial de chat de Copilot: [https://copilot.microsoft.com](https://copilot.microsoft.com).
4. Verifica que en la parte superior de la interfaz de chat aparezca el indicador de protección de datos empresariales (el candado verde o el rótulo **"Protegido" / "Protected"**), lo cual certifica el uso de la versión empresarial bajo el cumplimiento de privacidad de Microsoft 365 Copilot.

**Resultado Esperado**: Interfaz de chat de Microsoft 365 Copilot cargada, mostrando la marca de protección de datos empresariales en la esquina superior o dentro del cajón de chat.

**Verificación**: Toma nota visual de que el escudo de seguridad está activo antes de ingresar cualquier dato.

---

### Paso 2: Diseñar la Estrategia de Segmentación y Clasificación Documental

**Objetivo**: Utilizar Copilot para conceptualizar la fragmentación del expediente de alta volumetría de "Soluciones Logísticas Mundiales S.A." en tres bloques clave de análisis.

1. En el cuadro de texto de Copilot, escribe la siguiente instrucción diseñada para establecer el contexto y la estrategia de segmentación de la empresa ficticia:

   ```text
   Actúa como un Consultor de Riesgos Financieros Senior. Tengo un expediente de alta volumetría de un cliente ficticio llamado 'Soluciones Logísticas Mundiales S.A.'. El expediente contiene:
   - Balances Generales y Estados de Resultados de los últimos 3 años (PDF).
   - Informes de Auditoría de firmas externas (PDF).
   - Contratos de crédito vigentes con 3 bancos diferentes (PDF).
   - Opiniones de cumplimiento fiscal y actas de asambleas de socios (Word/PDF).

   Para evitar sobrecargar la ventana de contexto de análisis en sesiones futuras y prevenir alucinaciones, diseña una propuesta de segmentación que clasifique esta documentación en 3 bloques lógicos distintos. Explica el propósito analítico de cada bloque y qué tipo de datos o riesgos buscaremos mitigar en cada uno. Presenta la propuesta en una tabla estructurada.
   ```

2. Presiona `Enter` o haz clic en el botón de enviar.

**Resultado Esperado**: Copilot generará una estructura de segmentación con tres bloques lógicos diferenciados (por ejemplo: Bloque Financiero-Cuantitativo, Bloque Legal-Contractual, Bloque de Cumplimiento y Control), con sus propósitos y riesgos asociados detallados de forma clara en formato de tabla.

**Verificación**: Confirma que la tabla entregada divida los archivos ficticios propuestos y justifique la fragmentación basada en la optimización del procesamiento de datos de IA.

---

### Paso 3: Estructurar el Playbook de Prompts con Criterios de Trazabilidad

**Objetivo**: Crear la biblioteca o plantilla de instrucciones predefinidas que se aplicarán a cada bloque documental para asegurar que Copilot siempre cite el origen del hallazgo y evalúe la regla de negocio correspondiente.

1. Envía el siguiente prompt de seguimiento en la misma conversación de Copilot:

   ```text
   Basándote en los 3 bloques lógicos definidos para 'Soluciones Logísticas Mundiales S.A.', necesito que escribas 3 prompts altamente detallados y parametrizados (uno para cada bloque). 
   Cada prompt debe obligar a Copilot a:
   1. Actuar bajo un rol financiero especializado para ese bloque.
   2. Extraer datos limitándose estrictamente a los documentos de ese bloque, indicando 'DATO NO DISPONIBLE' si falta algo.
   3. Formatear la salida en tablas de Markdown que incluyan de manera explícita las columnas: [Concepto/Métrica], [Hallazgo/Valor], [Documento de Origen y Página Exacta] y [Regla de Negocio Evaluada].
   4. Detectar de forma activa e identificar en una sección final cualquier vacío documental o contradicción de datos entre los archivos del bloque.

   Por favor, escribe el texto de los 3 prompts listos para copiar y pegar, utilizando marcadores de posición tipo [RUTA_DEL_ARCHIVO] donde corresponda.
   ```

2. Analiza detenidamente la salida generada por Copilot. Debes asegurarte de que los prompts propuestos por la IA tengan las restricciones necesarias para evitar alucinaciones.

**Resultado Esperado**: Copilot redactará tres plantillas de prompts robustas y parametrizadas, diseñadas bajo las mejores prácticas de ingeniería de prompts financieros, listas para su reutilización en futuros análisis de expedientes reales.

**Verificación**: Comprueba que cada uno de los tres prompts generados exija explícitamente la columna de "Documento de Origen y Página Exacta" y cuente con una instrucción clara de control para reportar vacíos documentales mediante la etiqueta "DATO NO DISPONIBLE".

---

### Paso 4: Exportar y Consolidar el Playbook en Markdown

**Objetivo**: Guardar de forma persistente la estrategia diseñada para que sirva de punto de partida ("input lógico") en las fases prácticas subsiguientes.

1. En la respuesta de Copilot, busca el bloque o bloques de código Markdown que contienen los prompts y la propuesta de segmentación estructurada.
2. Haz clic en el botón **"Copiar" (Copy)** ubicado en la esquina superior derecha del bloque de respuesta de Copilot.
3. Abre un editor de texto plano (como el Bloc de notas / Notepad en Windows o TextEdit en macOS).
4. Pega el contenido copiado de la conversación.
5. Crea el directorio local si aún no existe. En Windows, abre la consola de comandos (`cmd`) y ejecuta:
   ```cmd
   mkdir C:\Capacitacion-Copilot\Casos-Finanzas\Modulos_1_4\
   ```
6. Guarda el archivo en tu editor de texto con el nombre `Estrategia_Analisis_Playbook.md` en la ruta:
   `C:\Capacitacion-Copilot\Casos-Finanzas\Modulos_1_4\Estrategia_Analisis_Playbook.md`

**Resultado Esperado**: Un archivo físico con extensión `.md` (Markdown) guardado en el directorio local predefinido, consolidando la planificación estratégica, la segmentación del expediente y las plantillas de prompts de auditoría.

**Verificación**: Navega mediante el Explorador de archivos de Windows a la ruta `C:\Capacitacion-Copilot\Casos-Finanzas\Modulos_1_4\` y valida que el archivo se haya creado correctamente y contenga los datos y tablas generadas en el paso 3.

## Validación y Pruebas

Para garantizar que el Playbook de Prompts cumple con las exigencias metodológicas y los estándares de control financiero establecidos en el curso, realiza la siguiente prueba de estrés de lógica analítica directamente con Copilot.

### Prueba de Estrés: Caso Adversario (Simulación de Contradicción y Vacío de Información)

Ejecuta una consulta de control para evaluar cómo reacciona tu estrategia ante información inconsistente. Introduce el siguiente prompt en tu chat activo de Copilot:

```text
Imagina que aplico tu prompt diseñado para el 'Bloque Financiero' en un expediente real. 
El Balance General de 2023 provisto por el cliente muestra un 'Pasivo Circulante' de $4,500,000 USD, pero el Informe de Auditoría Externa firmado de la misma fecha indica que el 'Pasivo Circulante' real consolidado asciende a $5,200,000 USD debido a deudas no registradas en la contabilidad interna.
Adicionalmente, el cliente omitió incluir el desglose de inventarios de 2023.

Simula cuál sería la salida exacta en formato de tabla de tu prompt del Bloque Financiero ante esta situación. Asegúrate de reflejar la discrepancia numérica de forma explícita en la columna de trazabilidad y de reportar el inventario omitido bajo la regla de control definida.
```

#### Salida Esperada en la Validación

Copilot debe responder con una simulación en formato tabla Markdown similar a la siguiente:

| Métrica / Concepto | Valor Encontrado | Documento de Origen y Página | Regla de Negocio / Alerta de Consistencia |
| :--- | :--- | :--- | :--- |
| **Pasivo Circulante (Contable)** | $4,500,000 USD | `Balance_General_2023.pdf`, Pág. 3. | **CONTRADICCIÓN DETECTADA**: Discrepa del informe de auditoría. |
| **Pasivo Circulante (Auditado)** | $5,200,000 USD | `Informe_Auditoría_2023.pdf`, Pág. 8. | **VALOR DE CONTROL**: Debe usarse este valor para el cálculo de solvencia por principio de prudencia. |
| **Desglose de Inventarios** | **DATO NO DISPONIBLE** | No incluido en el expediente. | **VACÍO DOCUMENTAL**: Impide el cálculo de la Prueba Ácida. Requiere requerimiento urgente al cliente. |

**Verificación de Éxito**: Si Copilot estructuró la discrepancia sin mezclar los datos o inventar valores (alucinación) y aplicó correctamente la etiqueta de "DATO NO DISPONIBLE", la estrategia analítica de tu Playbook se considera **Aprobada para Producción**.

## Solución de Problemas

A continuación, se describen dos posibles inconvenientes durante el desarrollo del laboratorio y cómo resolverlos de manera efectiva:

### Problema 1: Copilot genera prompts muy genéricos que no obligan a citar fuentes o páginas
- **Síntoma**: Los prompts que Copilot redacta en el Paso 3 solo extraen resúmenes de texto y omiten las columnas obligatorias de "Documento de Origen" y "Regla de Negocio Evaluada".
- **Causa**: El modelo interpretó de forma laxa las instrucciones de formato debido a la longitud de las mismas.
- **Resolución**: Envía una instrucción correctiva específica en el chat:
  ```text
  Reescribe los prompts anteriores. Es obligatorio que el formato de salida de cada prompt incluya una estructura rígida de tabla Markdown donde la columna 'Origen y Página Exacta' sea un campo requerido. Añade una restricción que penalice al modelo si inventa la fuente.
  ```

### Problema 2: Error de acceso o desconexión del indicador empresarial ("Protegido") en la esquina del chat
- **Síntoma**: El escudo verde o el aviso de protección de datos empresariales desaparece o aparece en color gris.
- **Causa**: Sesión de usuario cerrada por inactividad o inicio de sesión con una cuenta personal `@outlook.com` o `@hotmail.com` en Microsoft Edge.
- **Resolución**:
  1. Haz clic en el perfil del navegador (esquina superior izquierda de Edge).
  2. Cierra la sesión activa actual de la cuenta personal.
  3. Haz clic en "Agregar perfil de trabajo" e inicia sesión con las credenciales organizacionales autorizadas para Microsoft 365 Copilot Premium.
  4. Recarga la página [https://copilot.microsoft.com](https://copilot.microsoft.com) y vuelve a iniciar el proceso.

## Limpieza

Para mantener el orden de tu estación de trabajo y proteger la consistencia de los datos para los laboratorios futuros:

1. Cierra la pestaña de chat de Copilot en tu navegador Microsoft Edge.
2. Asegúrate de que el archivo `Estrategia_Analisis_Playbook.md` esté correctamente guardado en la ruta local `C:\Capacitacion-Copilot\Casos-Finanzas\Modulos_1_4\`. No elimines este archivo, ya que será la base de análisis estratégico y metodológico que consultarás o procesarás en el siguiente laboratorio del curso.
3. Cierra tu editor de texto plano (Notepad o TextEdit).

## Resumen

En este laboratorio, has completado el diseño metodológico de la estrategia de análisis financiero para un expediente ficticio de alta volumetría ("Soluciones Logísticas Mundiales S.A."). A través de **Microsoft 365 Copilot Premium**, lograste:
1. **Segmentar de manera estructurada** un expediente complejo en tres bloques independientes para optimizar el rendimiento de la ventana de contexto de los LLMs.
2. **Crear un Playbook de Prompts parametrizado** que exige consistencia, manejo de vacíos informativos mediante la regla de "DATO NO DISPONIBLE" y un formato estricto de tablas en Markdown.
3. **Preservar la trazabilidad tridimensional (Fuente-Hallazgo-Regla)** y validar la resiliencia del modelo de IA ante casos adversarios de contradicción documental.

### Recursos Adicionales de Microsoft
- [Guía de inicio rápido para Microsoft 365 Copilot](https://learn.microsoft.com/copilot/microsoft-365/)
- [Estrategias de prompts efectivos para Copilot](https://learn.microsoft.com/copilot/microsoft-365/microsoft-365-copilot-prompts)
- [Privacidad y seguridad de datos en Copilot para empresas](https://learn.microsoft.com/copilot/microsoft-365/microsoft-365-copilot-privacy)
