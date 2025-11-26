# README — Análisis Exploratorio y Limpieza de Datos Kiva Loans

## 1. Descripción del Proyecto

Este proyecto tiene como objetivo realizar una **Limpieza, Categorización y Análisis Exploratorio de Datos (EDA)** del dataset de préstamos de Kiva.  

El análisis se desarrolló en un entorno de notebook (**Google Colab**) para garantizar la **trazabilidad** y **reproducibilidad** del código.  

El objetivo principal fue preparar los datos y obtener **insights relevantes** sobre:  
- La distribución de los montos de préstamos (`loan_amount`).  
- Las categorías de actividad (`activity`).  
- La creación de categorías de préstamo (`loan_category`) basadas en el monto.  

---

## 2. Herramientas Utilizadas

El proyecto se realizó utilizando **Python** y las siguientes librerías:  

- **pandas**: Manipulación y análisis de estructuras de datos tabulares.  
- **numpy**: Operaciones numéricas y manejo eficiente de arrays.  
- **missingno**: Visualización y análisis de valores nulos en el dataset.  
- **seaborn**: Visualizaciones estadísticas y gráficos avanzados.  
- **matplotlib**: Creación de gráficos y visualizaciones personalizadas.  
- **plotly**: Visualizaciones interactivas para explorar datos de manera dinámica.  

**Entorno de desarrollo:** Google Colab.  

---

## 3. Dataset Utilizado

- Archivo principal: `kiva_loans.csv`  
- Tamaño aproximado: **671,000 filas** y **17 columnas**  
- Estructura de carpetas (recomendado para reproducibilidad):

01_raw_data/kiva_loans.csv
02_clean_data/ # Carpeta opcional para datasets procesados

markdown
Copiar código

**Resultado final esperado:** Un dataframe limpio, con las columnas categorizadas y listo para análisis exploratorio y modelado posterior.  

---

## 4. Conclusión Técnica y Hallazgos Clave

### Proceso de Limpieza
- Conversión de formatos de fecha a tipo datetime.  
- Tratamiento de valores nulos, especialmente en columnas críticas como `repayment_term`.  
- Revisión y corrección de tipos de datos incorrectos.  

### Enfoque Principal del Análisis
- Creación de la columna `loan_category` basada en `loan_amount`:  
  - Micro, Small, Medium, Large (según rangos definidos de préstamo).  

### Detección de Outliers
- Se aplicó el **método IQR (Rango Intercuartílico)** para detectar valores atípicos en cada categoría de préstamo.  
- Se decidió **mantener o eliminar los outliers** según su impacto en el análisis y su representatividad dentro de la categoría.  

### Insights de EDA
- Distribución de préstamos por `loan_category`, mostrando que la mayoría corresponden a préstamos **micro** y **small**.  
- Actividades (`activity`) más comunes: se identificaron patrones de préstamo según sectores productivos.  
- Visualizaciones clave:
  - **Histogramas** para examinar la distribución de `loan_amount`.  
  - **Boxplots** para identificar outliers y rangos de valores.  
  - **Gráficos de barras** para analizar la frecuencia de préstamos por categoría y actividad.  

Las visualizaciones permitieron una **comprensión clara de la distribución de los datos** y facilitaron la toma de decisiones sobre la limpieza y categorización.  

---

## 5. Estructura del Repositorio

01_raw_data/
└── kiva_loans.csv
P2_kiva_loans_analysis.ipynb
README.md

markdown
Copiar código

- `01_raw_data/`: Contiene el dataset original sin modificaciones.  
- `P2_kiva_loans_analysis.ipynb`: Notebook con todo el análisis, limpieza y visualizaciones.  
- `README.md`: Documentación del proyecto y hallazgos clave.  

---

## 6. Puntos Fuertes

- **Justificación clara del tratamiento de outliers**, manteniendo la integridad de los datos.  
- **Categorización lógica** de los montos de préstamo para análisis más significativo.  
- **Limpieza rigurosa** y estandarización de los tipos de datos y fechas.  
- Visualizaciones **claras y accesibles**, que facilitan la comprensión de patrones y distribuciones.  
- Reproducibilidad completa gracias al uso de **Google Colab** y estructura de carpetas organizada.  

---

**Nota:** El dataset procesado puede ser guardado en `02_clean_data/` para análisis futuros.  
# README — Análisis Exploratorio y Limpieza de Datos Kiva Loans

## 1. Descripción del Proyecto

Este proyecto tiene como objetivo realizar una **Limpieza, Categorización y Análisis Exploratorio de Datos (EDA)** del dataset de préstamos de Kiva.  

El análisis se desarrolló en un entorno de notebook (**Google Colab**) para garantizar la **trazabilidad** y **reproducibilidad** del código.  

El objetivo principal fue preparar los datos y obtener **insights relevantes** sobre:  
- La distribución de los montos de préstamos (`loan_amount`).  
- Las categorías de actividad (`activity`).  
- La creación de categorías de préstamo (`loan_category`) basadas en el monto.  

---

## 2. Herramientas Utilizadas

El proyecto se realizó utilizando **Python** y las siguientes librerías:  

- **pandas**: Manipulación y análisis de estructuras de datos tabulares.  
- **numpy**: Operaciones numéricas y manejo eficiente de arrays.  
- **missingno**: Visualización y análisis de valores nulos en el dataset.  
- **seaborn**: Visualizaciones estadísticas y gráficos avanzados.  
- **matplotlib**: Creación de gráficos y visualizaciones personalizadas.  
- **plotly**: Visualizaciones interactivas para explorar datos de manera dinámica.  

**Entorno de desarrollo:** Google Colab.  

---

## 3. Dataset Utilizado

- Archivo principal: `kiva_loans.csv`  
- Tamaño aproximado: **671,000 filas** y **17 columnas**  
- Estructura de carpetas (recomendado para reproducibilidad):

01_raw_data/kiva_loans.csv
02_clean_data/ # Carpeta opcional para datasets procesados

markdown
Copiar código

**Resultado final esperado:** Un dataframe limpio, con las columnas categorizadas y listo para análisis exploratorio y modelado posterior.  

---

## 4. Conclusión Técnica y Hallazgos Clave

### Proceso de Limpieza
- Conversión de formatos de fecha a tipo datetime.  
- Tratamiento de valores nulos, especialmente en columnas críticas como `repayment_term`.  
- Revisión y corrección de tipos de datos incorrectos.  

### Enfoque Principal del Análisis
- Creación de la columna `loan_category` basada en `loan_amount`:  
  - Micro, Small, Medium, Large (según rangos definidos de préstamo).  

### Detección de Outliers
- Se aplicó el **método IQR (Rango Intercuartílico)** para detectar valores atípicos en cada categoría de préstamo.  
- Se decidió **mantener o eliminar los outliers** según su impacto en el análisis y su representatividad dentro de la categoría.  

### Insights de EDA
- Distribución de préstamos por `loan_category`, mostrando que la mayoría corresponden a préstamos **micro** y **small**.  
- Actividades (`activity`) más comunes: se identificaron patrones de préstamo según sectores productivos.  
- Visualizaciones clave:
  - **Histogramas** para examinar la distribución de `loan_amount`.  
  - **Boxplots** para identificar outliers y rangos de valores.  
  - **Gráficos de barras** para analizar la frecuencia de préstamos por categoría y actividad.  

Las visualizaciones permitieron una **comprensión clara de la distribución de los datos** y facilitaron la toma de decisiones sobre la limpieza y categorización.  

---

## 5. Estructura del Repositorio

01_raw_data/
└── kiva_loans.csv
P2_kiva_loans_analysis.ipynb
README.md

markdown
Copiar código

- `01_raw_data/`: Contiene el dataset original sin modificaciones.  
- `P2_kiva_loans_analysis.ipynb`: Notebook con todo el análisis, limpieza y visualizaciones.  
- `README.md`: Documentación del proyecto y hallazgos clave.  

---

## 6. Puntos Fuertes

- **Justificación clara del tratamiento de outliers**, manteniendo la integridad de los datos.  
- **Categorización lógica** de los montos de préstamo para análisis más significativo.  
- **Limpieza rigurosa** y estandarización de los tipos de datos y fechas.  
- Visualizaciones **claras y accesibles**, que facilitan la comprensión de patrones y distribuciones.  
- Reproducibilidad completa gracias al uso de **Google Colab** y estructura de carpetas organizada.  

---

**Nota:** El dataset procesado puede ser guardado en `02_clean_data/` para análisis futuros.  





