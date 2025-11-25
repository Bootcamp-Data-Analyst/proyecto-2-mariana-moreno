

1. Descripción del proyecto
Este proyecto se enfoca en el Análisis Exploratorio de Datos (EDA) de micropréstamos otorgados por la plataforma Kiva. El objetivo principal fue comprender la distribución, tendencias y patrones clave dentro del ecosistema global de microfinanzas.

Se abordó la necesidad de categorizar los préstamos por su cuantía para un análisis segmentado más preciso. El proyecto resuelve el problema de la falta de una visión clara sobre la composición de la cartera de préstamos en términos de montos, actividades y su evolución temporal.

El trabajo consistió en la limpieza, transformación y categorización del dataset de Kiva, culminando con un análisis de valores atípicos segmentado y la visualización de la tendencia de los montos financiados a lo largo del tiempo.

2. Herramientas utilizadas
El análisis fue desarrollado en un entorno Jupyter Notebook (compatible con Google Colab) para garantizar la reproducibilidad del código.

Las librerías y tecnologías principales empleadas son:

Python: Lenguaje de programación base.

pandas (pd): Esencial para la manipulación, limpieza y estructuración del dataset.

numpy (np): Utilizado para operaciones numéricas eficientes, especialmente en cálculos estadísticos y manejo de arrays.

missingno (msno): Instalada para la visualización y el análisis inicial de la matriz de datos faltantes, un paso clave en la curación de datos.

matplotlib / seaborn: Empleadas para la generación de gráficos estadísticos y la visualización de series temporales.

3. Dataset utilizado
El proyecto se basa en el archivo kiva_loans.csv, que contiene datos de préstamos de la organización Kiva.

Origen de los datos: Plataforma Kiva, dedicada a conectar prestamistas con emprendedores en regiones en desarrollo.

Composición: El dataset está compuesto por 671,205 registros.

Columnas Clave: Incluye funded_amount, loan_amount (con un rango entre 25.0 y 100,000.0), sector, country (59 valores únicos), currency (48 valores únicos) y repayment_interval.

Curación Inicial:

Se realizaron dos transformaciones principales durante la fase de curación:

Transformación a minúsculas: Las columnas categóricas como activity y sector fueron uniformadas a minúsculas para evitar inconsistencias en el conteo de categorías (p. ej., 'Food' vs. 'food').

Creación de Categoría: Se implementó una estandarización del monto del préstamo (loan_amount) en una nueva columna, loan_amount_category, para clasificar los préstamos en rangos de microfinanzas.

4. Metodología / Proceso realizado
El análisis siguió un flujo de trabajo estructurado en tres fases: carga, estandarización y análisis segmentado.

4.1. Estandarización de loan_amount
Se aplicó una transformación categórica a la variable loan_amount para facilitar el análisis de microfinanzas.

Decisión Justificada: La categorización permite evaluar la distribución y los patrones estadísticos (como los outliers) de forma independiente para cada escala de préstamo.

Rangos Definidos: Los préstamos se segmentaron en cuatro categorías utilizando límites claros, basados en el monto real (mín: 25.0, máx: 100,000.0):

micro: [25.0 a < 500)

small: [500 a < 2500)

medium: [2500 a < 10000)

large: [10000 a 100000.0]

4.2. Análisis de Valores Atípicos (Outliers)
Se calculó el Rango Intercuartil (IQR) y sus límites (Q1, Q3) de forma independiente para cada loan_amount_category.

Flujo del Análisis: El proceso verificó la cantidad de outliers en las variables numéricas, segmentando por la nueva categoría de monto.

Decisión Justificada: Segmentar el análisis de outliers es una buena práctica técnica. Permite identificar valores atípicos específicos en préstamos pequeños sin ser sesgado por los préstamos grandes, manteniendo la integridad de las distribuciones internas.

4.3. Análisis Temporal
Se realizó un análisis de series de tiempo para identificar la tendencia en el volumen de financiamiento.

Agregación: Se agrupó la suma de funded_amount por mes (freq='M') utilizando la columna posted_time.

Visualización: El resultado se graficó mediante un diagrama de línea para ilustrar la evolución mensual del capital financiado.

5. Conclusión técnica
El análisis de la estructura del préstamo en Kiva confirma el enfoque en la financiación de bajo monto y valida las decisiones de modelado.

Concentración de Microcréditos: El análisis de la distribución de loan_amount_category reveló que más del 93% de los registros se concentran en las categorías 'micro' (330,534) y 'small' (299,111). Esto confirma que Kiva cumple su objetivo principal como plataforma de microfinanzas.

Patrón en Outliers: La decisión de segmentar el análisis de outliers fue adecuada.

La categoría 'micro' mostró una notable ausencia de valores atípicos según el método IQR (Q1: 200.0, Q3: 350.0). Esto indica que el monto de los micropréstamos es extremadamente consistente.

Las categorías 'small' y 'medium' sí presentaron outliers significativos (10,203 y 1,863 respectivamente). Esto sugiere mayor variabilidad en los préstamos de montos intermedios.

Validación de Decisiones: La creación de la variable loan_amount_category fue fundamental. Permitió transformar una variable continua (loan_amount) con una distribución altamente sesgada en una variable discreta, lo que facilitó un análisis estadístico y de negocio más interpretativo y robusto.

6. Accesibilidad aplicada
La accesibilidad es un eje central en la generación de este informe técnico para asegurar que los hallazgos sean comprensibles por cualquier usuario, independientemente de sus capacidades.

Estructura Semántica Clara: Se utiliza una estructura de encabezados jerárquica (títulos numerados con Markdown) para permitir una navegación sencilla y coherente del documento.

Legibilidad y Contraste: Se utiliza Markdown limpio y ordenado, priorizando párrafos cortos y listas claras, lo que mejora la legibilidad general.

Gráficos Simples y Coherencia de Color: Se prioriza el uso de visualizaciones de tipo Serie Temporal (Línea) y distribuciones de frecuencia (conteo) para comunicar patrones de forma directa. Se asume el uso de paletas de color con alto contraste y compatibilidad para daltónicos (color-blind friendly) en la generación de figuras.

Énfasis Textual Controlado: Se limita el uso de negritas únicamente a términos clave o hallazgos técnicos (como Análisis Exploratorio de Datos, IQR, o ausencia de valores atípicos) para dirigir la atención sin sobrecargar visualmente.

7. Estructura del repositorio
La organización del proyecto se presenta en una estructura de repositorio estándar para la ciencia de datos, asegurando la trazabilidad de los datos y el código.

Directorio / Archivo	Propósito
README.md	Documentación completa y accesible del proyecto (el presente archivo).
kiva_loans.ipynb	Contiene el código fuente completo del análisis: carga de datos, limpieza, estandarización, análisis de outliers y generación de visualizaciones.
data/	Carpeta destinada a alojar el dataset original kiva_loans.csv y cualquier fuente de datos adicional utilizada.
visualizations/	Carpeta para almacenar las figuras, gráficos y outputs visuales generados durante el análisis (p. ej., el gráfico de serie temporal).
8. Puntos fuertes del proyecto
Reproducibilidad: El proyecto se documenta en un único notebook (Jupyter) y este README, facilitando su ejecución y validación por terceros.

Modelado de Características: Creación justificada de la columna loan_amount_category para transformar datos continuos en segmentos de negocio interpretables.

Análisis Segmentado Robusto: Aplicación del análisis de outliers de manera segmentada, lo cual es técnicamente superior para datasets con distribuciones sesgadas, como es común en microfinanzas.

Documentación Accesible: Adopción de un estilo de informe técnico que prioriza la claridad, el lenguaje técnico conciso y la accesibilidad visual.

Uso de Librerías Esenciales: Implementación de librerías estándar de la industria (pandas, numpy, missingno) para un procesamiento de datos eficiente.

9. Autor/a
Mariana Moreno Henao




