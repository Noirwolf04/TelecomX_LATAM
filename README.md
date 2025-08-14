# TelecomX_LATAM
# Proyecto de Análisis de Churn de Clientes - Telecom X

## Descripción del Proyecto

Este proyecto tiene como objetivo principal analizar los datos de clientes de la empresa de telecomunicaciones Telecom X para comprender los factores que influyen en la tasa de evasión de clientes (Churn). El análisis exploratorio de datos (EDA) realizado busca identificar patrones y características de los clientes que abandonan para proporcionar insights valiosos que ayuden al equipo de ciencia de datos en la construcción de modelos predictivos y en la definición de estrategias de retención más efectivas.

## Fuente de Datos

Los datos utilizados en este análisis provienen de un archivo JSON alojado en un repositorio de GitHub:
`https://raw.githubusercontent.com/alura-cursos/challenge2-data-science-LATAM/main/TelecomX_Data.json`

El dataset contiene información detallada sobre los clientes, incluyendo datos demográficos, servicios contratados, información de facturación y el estado de abandono (Churn).

## Metodología

La metodología del proyecto se basó en un flujo de trabajo estándar de análisis de datos, que incluyó las siguientes fases:

1.  **Extracción de Datos:** Carga del archivo JSON desde la URL proporcionada en un DataFrame de pandas.
2.  **Transformación de Datos:**
    *   Normalización de columnas anidadas (`customer`, `phone`, `internet`, `account`).
    *   Conversión de la columna `Charges.Total` a formato numérico, manejando valores no numéricos.
    *   Imputación de valores nulos resultantes en `Charges.Total` con 0.
    *   Creación de la columna `Cuentas_Diarias` (cargos diarios promedio).
    *   Renombramiento de columnas para mejorar la legibilidad.
    *   Conversión de columnas binarias ('Yes'/'No', 'No service') a tipo booleano.
    *   Eliminación de filas con valores nulos en la variable objetivo `Abandono`.
3.  **Análisis Exploratorio de Datos (EDA):**
    *   Análisis descriptivo de variables numéricas y categóricas.
    *   Visualización de la distribución de la variable objetivo (`Abandono`).
    *   Exploración de la relación entre variables categóricas (`Genero`, `Servicio_internet`, `Contrato`, `Metodo_pago`, etc.) y el abandono mediante gráficos comparativos (histogramas, gráficos de barras agrupadas).
    *   Análisis de la distribución de variables numéricas (`Antiguedad_meses`, `Cargos_mensuales`, `Cargos_totales`, `Cuentas_Diarias`) para clientes que abandonan y no abandonan (histogramas comparativos).
4.  **Documentación de Hallazgos:** Elaboración de un informe resumen con las conclusiones clave y recomendaciones estratégicas basadas en el EDA.

## Hallazgos Clave del Análisis Exploratorio

Los principales insights identificados incluyen:

*   Los clientes con baja antigüedad y altos cargos mensuales (a menudo asociados a fibra óptica) son más propensos al abandono.
*   El tipo de servicio de internet (fibra óptica), los contratos mes a mes y el método de pago electrónico están fuertemente asociados con una mayor tasa de churn.
*   La ausencia de servicios adicionales de seguridad y soporte técnico también se relaciona con un mayor abandono.
*   Factores como ser ciudadano mayor o no tener pareja/dependientes muestran una ligera asociación con el churn.

Estos hallazgos sugieren que las estrategias de retención deberían enfocarse en los clientes nuevos, mejorar la experiencia con el servicio de fibra óptica y promover servicios adicionales y contratos a largo plazo.

## Estructura del Notebook

El notebook está organizado en secciones que siguen el flujo del análisis:

*   **Extracción:** Carga de datos.
*   **Transformación:** Pasos de limpieza, tratamiento y creación de nuevas variables.
*   **Carga y Análisis:** Realización del análisis exploratorio de datos con visualizaciones.
*   **Informe Final:** Presentación del resumen del análisis, conclusiones y recomendaciones (estructurado con secciones de texto en Markdown seguidas por las celdas de código que muestran los gráficos correspondientes).

Para ejecutar el análisis y visualizar los resultados, simplemente ejecuta cada celda del notebook en orden. Las visualizaciones interactivas de Plotly aparecerán en la salida de las celdas de código
