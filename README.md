
# An-lisis-de-sentimiento-de-noticias-sobre-Apple-y-su-relaci-n-con-el-precio-accionario-usando-Python# Análisis de sentimiento de noticias sobre Apple y su relación con el precio accionario usando Python

## 1. Introducción

El análisis de datos permite transformar información dispersa en evidencia útil para la toma de decisiones. En el ámbito financiero, las noticias pueden influir en la percepción de los inversionistas y, en algunos casos, coincidir con movimientos en el precio de las acciones. Por ello, este proyecto analiza noticias relacionadas con Apple Inc. mediante herramientas de Python, con el fin de identificar el sentimiento predominante de los titulares y observar su relación con el comportamiento accionario de la empresa.

Apple es una de las compañías tecnológicas con mayor presencia mediática a nivel internacional. Sus lanzamientos, resultados financieros, cambios regulatorios y decisiones estratégicas suelen generar amplia cobertura en medios especializados. Debido a ello, resulta pertinente analizar si el sentimiento expresado en las noticias puede aportar información útil para comprender la percepción del mercado.

## 2. Planteamiento del problema

Los precios de las acciones son afectados por múltiples factores, entre ellos resultados financieros, expectativas de crecimiento, condiciones macroeconómicas, decisiones de política monetaria, competencia y noticias corporativas. Sin embargo, no siempre es sencillo medir el efecto de la información publicada en medios. 

El problema que aborda este proyecto es determinar cómo se distribuye el sentimiento de noticias sobre Apple y si dicho sentimiento muestra algún patrón temporal relacionado con el precio de sus acciones. No se busca construir un sistema definitivo de predicción bursátil, sino explorar si el análisis de sentimiento puede complementar el análisis financiero tradicional.

## 3. Objetivo general

Analizar el sentimiento de noticias relacionadas con Apple Inc. mediante Python, clasificando los titulares como positivos, negativos o neutrales, con el fin de identificar patrones informativos y explorar su relación con el precio accionario de la empresa.

## 4. Objetivos específicos

- Organizar una base de datos de noticias sobre Apple en un DataFrame de pandas.
- Analizar la distribución de sentimientos positivos, negativos y neutrales.
- Identificar las principales fuentes informativas del conjunto de datos.
- Observar la evolución mensual y diaria del sentimiento.
- Comparar visualmente el sentimiento de las noticias con el precio de cierre de Apple.
- Implementar un modelo predictivo exploratorio para evaluar si el sentimiento puede anticipar la dirección del precio al día siguiente.

## 5. Descripción de los datos

El conjunto de datos utilizado corresponde a noticias sobre Apple. La base contiene titulares, fechas de publicación, fuente informativa, sentimiento clasificado, valor numérico del sentimiento y score de confianza del modelo.

| Variable | Descripción |
|---|---|
| id | Identificador de la noticia |
| title | Título de la noticia |
| date | Fecha de publicación |
| source | Fuente o sitio de origen |
| score | Nivel de confianza del modelo de sentimiento |
| sentiment | Etiqueta de sentimiento: positive, neutral o negative |
| sentiment_value | Valor numérico del sentimiento: 1, 0 o -1 |
| month | Mes de publicación |

## 6. Herramientas utilizadas

Para el desarrollo del proyecto se utilizaron las siguientes herramientas:

- Python, como lenguaje principal de análisis.
- pandas, para manipulación y limpieza de datos.
- matplotlib y seaborn, para visualización.
- FinBERT, para clasificación de sentimiento financiero.
- yfinance, para consultar precios históricos de Apple.
- scikit-learn, para el modelo predictivo exploratorio.

## 7. Limpieza y preparación de datos

El archivo principal utilizado fue `apple_cleaned.csv`. Primero se cargó el archivo con pandas, se convirtió la columna de fecha al formato datetime y se verificó que las variables numéricas, como `score` y `sentiment_value`, estuvieran en el tipo correcto.

La etiqueta de sentimiento se trabajó con tres categorías: positivo, neutral y negativo. Para facilitar el análisis estadístico, estas categorías se transformaron en valores numéricos: 1 para sentimiento positivo, 0 para neutral y -1 para negativo.

## 8. Análisis exploratorio

El análisis exploratorio permitió conocer la composición general de las noticias. Primero se calculó la cantidad total de registros, el rango de fechas y la distribución de sentimientos. Después se analizaron las principales fuentes informativas y el score promedio del modelo.

La gráfica de distribución de sentimientos permite identificar si la cobertura sobre Apple fue principalmente positiva, negativa o neutral. Este resultado es importante porque muestra la tendencia general del discurso mediático alrededor de la empresa.

## 9. Análisis temporal del sentimiento

Para estudiar el comportamiento del sentimiento a lo largo del tiempo, las noticias se agruparon por fecha y por mes. Esto permitió calcular el sentimiento promedio diario y mensual. Además, se aplicó un promedio móvil de 7 días para suavizar las variaciones diarias.

Este procedimiento permite observar si existieron periodos con mayor concentración de noticias negativas o positivas, así como posibles cambios en la percepción mediática sobre Apple durante el periodo analizado.

## 10. Relación entre sentimiento y precio accionario

Posteriormente, se descargaron los precios históricos de Apple mediante yfinance. Para facilitar la comparación visual, el precio de cierre se normalizó en una escala de 0 a 1. Después, se comparó con el sentimiento promedio suavizado.

Esta comparación permite observar si los cambios en el sentimiento coinciden con movimientos en el precio de la acción. Sin embargo, debe interpretarse con cautela, ya que el precio accionario depende de muchos otros factores además de las noticias.

## 11. Modelo predictivo exploratorio

Como ejercicio adicional, se construyó una variable objetivo llamada `sube_baja`, la cual indica si el precio de cierre de Apple subió al día siguiente. El valor 1 indica que el precio subió, mientras que el valor 0 indica que bajó o se mantuvo.

Se utilizó un modelo Random Forest para evaluar si el sentimiento promedio diario podía ayudar a anticipar la dirección del precio. La división entre entrenamiento y prueba se realizó sin mezclar los datos, respetando el orden temporal, para evitar el uso de información futura.

## 12. Resultados esperados

Con base en los análisis previos, se espera encontrar que la mayoría de las noticias sobre Apple se concentran en sentimiento neutral, seguido por noticias negativas y positivas. También se espera que el modelo predictivo tenga un desempeño limitado, ya que el sentimiento de noticias por sí solo no suele ser suficiente para explicar el comportamiento diario del mercado bursátil.

## 13. Conclusiones

El análisis de sentimiento aplicado a noticias sobre Apple permite comprender mejor la percepción mediática alrededor de la empresa. La transformación de titulares en variables cuantitativas facilita su análisis estadístico y su comparación con información financiera.

Los resultados muestran que el sentimiento puede ser útil como variable complementaria para analizar tendencias, pero no debe utilizarse de manera aislada para predecir el precio de una acción. El comportamiento bursátil depende de múltiples factores, como reportes financieros, expectativas de inversionistas, indicadores macroeconómicos, volumen de operaciones y eventos externos.

En conclusión, el análisis de sentimiento representa una herramienta valiosa dentro del análisis de datos financieros, pero su uso debe combinarse con otras variables para construir modelos más robustos y confiables.
