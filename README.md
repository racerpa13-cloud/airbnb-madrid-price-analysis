# Análisis de precios de Airbnb en Madrid

Proyecto de análisis exploratorio de datos (EDA) desarrollado en Python para estudiar cómo varían los precios anunciados de los alojamientos completos de Airbnb en Madrid según sus características, ubicación, valoraciones y atributos del anfitrión.

El objetivo es identificar patrones y diferencias de precios que puedan apoyar la comparación de alojamientos y la toma de decisiones comerciales.

> **Enfoque:** análisis descriptivo orientado al negocio. Los resultados muestran asociaciones entre variables, pero no permiten establecer relaciones causales ni determinar precios óptimos.

## 1. Pregunta de negocio

**¿Qué características se asocian con las diferencias de precio de los alojamientos Airbnb en Madrid y cómo pueden orientar las comparaciones entre viviendas similares?**

El proyecto plantea un escenario de análisis para una empresa del sector inmobiliario, con el objetivo de identificar factores relevantes para la comparación de precios.

Se trata de un ejercicio formativo adaptado a un portfolio profesional, no de un proyecto desarrollado para una empresa real.

## 2. Datos utilizados

El análisis parte de cinco datasets con **21.020 registros cada uno**, relacionados mediante el identificador `id`.

Las tablas contienen información sobre:

- **Condiciones de alquiler:** precios y condiciones de los alojamientos.
- **Anfitriones:** características y atributos de los propietarios.
- **Ubicación:** barrios, distritos y distancias a puntos de referencia.
- **Viviendas:** tipología, dormitorios, baños y capacidad de huéspedes.
- **Valoraciones:** puntuaciones y número de reseñas recibidas.

Tras integrar las tablas y seleccionar exclusivamente los alojamientos completos (`entire_home_apt`), se obtiene una muestra de **12.913 viviendas**.

Los archivos originales se facilitaron en formato Parquet y posteriormente se convirtieron a CSV para trabajar con ellos.

## 3. Metodología

El proyecto se desarrolla en las siguientes fases:

1. **Exploración inicial:** revisión de la estructura, tipos de datos, variables y principales estadísticos descriptivos de las cinco tablas.
2. **Integración de datos:** unión de las tablas mediante el identificador `id` y selección de alojamientos completos.
3. **Análisis exploratorio:** estudio de siete factores relacionados con el precio mediante agrupaciones, estadísticos descriptivos y visualizaciones.
4. **Análisis de correlaciones:** cálculo de correlaciones de Pearson entre el precio y determinadas variables numéricas.
5. **Conclusiones:** interpretación de resultados, identificación de implicaciones empresariales y exposición de limitaciones.

Para el análisis se utilizan medias, medianas, recuentos, diagramas de caja, gráficos de barras y diagramas de dispersión.

Se presta especial atención a los precios extremos, las diferencias en los tamaños muestrales y la interpretación de las relaciones entre variables.

## 4. Resultados principales

El análisis identifica los siguientes hallazgos:

| Factor analizado | Resultado principal |
|---|---|
| **Número de dormitorios** | Los precios medianos aumentan entre las viviendas de 1, 2 y 3 dormitorios, junto con una mayor dispersión. |
| **Capacidad de huéspedes** | Se observa un aumento general del precio mediano entre alojamientos de 2 a 6 huéspedes. |
| **Distancia a Sol** | No se identifica una relación lineal clara con el precio. |
| **Condición de Superhost** | Los Superhost presentan una mediana ligeramente superior (85 € frente a 80 €), pero una media inferior. |
| **Valoraciones de huéspedes** | Los precios medianos aumentan entre los grupos de valoración baja, media y alta, aunque las medias no siguen la misma progresión. |
| **Distrito** | Existen diferencias en los precios medianos entre distritos, con tamaños muestrales desiguales. |
| **Barrio** | Entre los barrios con al menos 50 viviendas, Castellana presenta la mayor mediana (140 €) y Puente de Vallecas la menor (50 €). |
| **Correlaciones** | Las variables numéricas analizadas presentan correlaciones lineales muy débiles con el precio. Destaca la correlación entre dormitorios y capacidad de huéspedes (0,751). |

El análisis muestra que las diferencias de precios observadas entre grupos no se traducen necesariamente en relaciones lineales fuertes.

En la comparación por barrios se establece un mínimo exploratorio de 50 viviendas por grupo, con el objetivo de reducir la influencia de grupos con pocas observaciones. Este umbral no garantiza representatividad estadística.

## 5. Implicaciones para el negocio

Los resultados permiten extraer algunas consideraciones para el análisis comercial de alojamientos turísticos:

- **Comparación de viviendas similares:** resulta más adecuado comparar alojamientos con características y ubicaciones semejantes que utilizar un único precio medio para todo Madrid.
- **Selección de indicadores:** la presencia de precios extremos hace recomendable complementar las medias con medianas y medidas de dispersión.
- **Segmentación geográfica:** las diferencias entre barrios y distritos justifican realizar comparaciones por zonas, teniendo en cuenta el número de alojamientos disponibles.
- **Evaluación de características:** dormitorios, capacidad y valoraciones pueden utilizarse para organizar grupos de comparación, sin asumir que determinan individualmente el precio.

Estas observaciones pueden servir como punto de partida para estudios posteriores de posicionamiento de precios, siempre que se disponga de información adicional sobre ocupación, costes y rentabilidad.

## 6. Limitaciones

El análisis presenta las siguientes limitaciones:

- **Carácter descriptivo:** los resultados permiten identificar asociaciones, pero no establecer causalidad ni determinar la importancia relativa de todos los factores.
- **Precios extremos:** la distribución de los precios puede influir en las medias y en determinados indicadores estadísticos.
- **Tamaños muestrales:** existen diferencias importantes en el número de alojamientos entre barrios y distritos.
- **Valoraciones incompletas:** algunos alojamientos carecen de puntuaciones y quedan excluidos de los cálculos que utilizan esta variable.
- **Información económica:** no se dispone de datos sobre ocupación, costes o rentabilidad que permitan estimar el precio óptimo de cada alojamiento.
- **Actualidad de los datos:** los resultados describen la muestra analizada y no necesariamente representan la situación actual del mercado turístico de Madrid.

