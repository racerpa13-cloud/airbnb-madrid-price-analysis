# Análisis de precios de Airbnb en Madrid

Proyecto de análisis exploratorio de datos (EDA) en Python para estudiar cómo varían los precios anunciados de los alojamientos completos de Airbnb en Madrid según sus características, ubicación, valoraciones y atributos del anfitrión.

> **Enfoque:** análisis descriptivo para apoyar comparaciones de mercado. Los resultados muestran asociaciones, no efectos causales ni precios óptimos.

## Pregunta de negocio

**¿Qué características se asocian con las diferencias de precio y cómo pueden orientar comparaciones entre alojamientos similares?**

El trabajo parte de un escenario de análisis para una empresa del sector inmobiliario. No implica que se haya realizado para una empresa real ni que sus recomendaciones se hayan implementado.

## Resultados principales

Se parte de cinco tablas con **21.020 registros cada una**, relacionadas mediante `id`. El análisis se centra en **12.913 alojamientos completos** (`entire_home_apt`).

| Dimensión | Hallazgo |
|---|---|
| Dormitorios | La mediana del precio aumenta al comparar alojamientos de 1, 2 y 3 dormitorios. |
| Capacidad | Se observa un aumento general de la mediana entre alojamientos para 2–6 huéspedes. |
| Distancia a Sol | No se identifica una relación lineal clara con el precio. |
| Superhost | Mediana de **85 €** frente a **80 €** para no Superhost, mientras que la media es inferior para Superhost. |
| Valoraciones | Las medianas aumentan entre los grupos de valoración baja, media y alta; las medias no siguen una progresión uniforme. |
| Distritos | Existen diferencias de precio mediano, con grupos de tamaños muy desiguales. |
| Barrios | Entre barrios con al menos **50 viviendas**, Castellana registra **140 €** de mediana y Puente de Vallecas **50 €**. |
| Correlaciones | Las relaciones lineales de Pearson entre el precio y las variables numéricas examinadas son muy débiles. |

**Lectura empresarial:** las comparaciones de precios deben realizarse entre alojamientos de ubicación y características semejantes, utilizando indicadores robustos ante precios extremos y revisando el tamaño de los grupos.

## Metodología

1. **Exploración:** estructura, tipos, estadísticos descriptivos y distribución de las cinco tablas.
2. **Integración:** unión de los datos por `id` y selección de viviendas completas.
3. **Análisis de siete hipótesis:** dormitorios, capacidad, distancia a Sol, Superhost, valoraciones, distrito y barrio.
4. **Contraste descriptivo:** medias, medianas, distribución de precios, recuentos y matriz de correlación de Pearson.
5. **Conclusiones:** interpretación de hallazgos, implicaciones de negocio y limitaciones.

Para la clasificación de barrios se exige un mínimo exploratorio de 50 alojamientos por grupo; este umbral es una decisión metodológica práctica, no una garantía de representatividad estadística. Los gráficos pueden ocultar valores atípicos para facilitar la lectura, sin eliminarlos de los datos.

## Tecnologías

Python · pandas · NumPy · Matplotlib · seaborn · Jupyter Notebook

## Estructura del repositorio

```text
airbnb-madrid-portfolio/
├── README.md
├── analisis_airbnb_madrid.ipynb
├── requirements.txt
├── .gitignore
└── data/
    ├── airbnb_madrid_conditions.csv
    ├── airbnb_madrid_host.csv
    ├── airbnb_madrid_location.csv
    ├── airbnb_madrid_property.csv
    └── airbnb_madrid_reviews.csv
```

## Cómo reproducir el análisis

Se recomienda **Python 3.10 o superior**. Desde la carpeta raíz del repositorio:

```bash
python -m venv .venv
```

Activa el entorno virtual:

- **Windows (PowerShell):** `.venv\Scripts\Activate.ps1`
- **macOS / Linux:** `source .venv/bin/activate`

Instala las dependencias y abre Jupyter:

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

Abre `analisis_airbnb_madrid.ipynb` y ejecuta **Kernel → Restart & Run All**. Las rutas de lectura son relativas a la carpeta `data/`, por lo que el notebook debe abrirse con la carpeta raíz del repositorio como directorio de trabajo.

## Datos

Los cinco CSV suministrados para este proyecto contienen información de condiciones de alquiler, anfitriones, ubicación, características físicas y reseñas. Cada tabla utiliza `id` como clave de relación.

**Procedencia y licencia:** los archivos se recibieron como material del ejercicio. La fuente original exacta, su fecha de extracción y sus términos de redistribución **no están documentados aquí**. Conviene verificar que se permite publicarlos antes de subir el directorio `data/` a un repositorio público. Si no se dispone de esa autorización, se pueden excluir los CSV y proporcionar en su lugar las instrucciones oficiales para obtenerlos cuando se conozca la fuente.

## Limitaciones

- Es un análisis observacional y descriptivo: no permite inferir causalidad ni establecer la importancia relativa de todas las variables.
- La distribución del precio presenta valores extremos y las muestras difieren considerablemente por ubicación.
- Hay alojamientos sin puntuación de valoración; los análisis que usan esa columna se realizan sobre registros disponibles.
- No se dispone de ocupación, costes, rentabilidad ni información temporal suficiente para estimar un precio óptimo.
- Los resultados corresponden a la muestra facilitada, no necesariamente al mercado actual de Madrid.

## Estado del proyecto

Análisis exploratorio completado, con siete hipótesis y comprobación complementaria de correlaciones. Proyecto adaptado desde un ejercicio de formación al formato de portfolio profesional.
