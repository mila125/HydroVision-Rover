🛰️ TerrainExplorer – Mars Terrain Intelligence System

TerrainExplorer es una aplicación interactiva para análisis de terreno marciano que combina datos hiperespectrales, modelos de elevación y algoritmos de aprendizaje automático para:

detectar minerales asociados con agua

analizar el riesgo del terreno para rovers

calcular rutas óptimas de exploración

visualizar el terreno en 2D y 3D

⚙️ Instalación
1. Crear entorno de Conda
conda create -n mars python=3.11
2. Activar el entorno
conda activate mars
3. Instalar dependencias
pip install -r requirements.txt

Si el proyecto usa librerías geoespaciales:

conda install -c conda-forge gdal rasterio
▶️ Ejecutar TerrainExplorer
streamlit run main.py

Luego abre en tu navegador:

http://localhost:8501
🛰️ Cómo funciona el sistema

El sistema realiza varias etapas para analizar el terreno marciano.

1. Carga de datos planetarios

El sistema trabaja con dos tipos de datos científicos:

Imagen hiperespectral (.img + .hdr)
Contiene información espectral que permite identificar minerales.

Modelo Digital de Elevación (DEM) (.tif)
Describe la topografía del terreno marciano.

2. Procesamiento de datos

Se realiza una etapa de preprocesamiento para preparar los datos:

limpieza de valores inválidos

normalización de datos

reducción de dimensionalidad mediante PCA (Principal Component Analysis)

Esto permite trabajar con las bandas espectrales que contienen mayor variabilidad de información.

3. Detección de minerales

Se aplica clustering no supervisado (K-Means) sobre los datos espectrales para identificar distintos tipos de minerales.

Algunos minerales detectados pueden estar asociados con la presencia histórica de agua, como:

Hematita

Arcillas

Minerales hidratados

4. Análisis del terreno y riesgo

A partir del DEM se calcula la pendiente del terreno, lo que permite estimar el riesgo para la navegación de un rover:

pendientes altas → mayor riesgo

pendientes bajas → terreno más seguro

Las zonas más bajas o valles pueden indicar lugares donde el agua pudo acumularse en el pasado.

5. Planificación de rutas

El sistema construye un grafo del terreno, donde:

cada píxel representa un nodo

las conexiones representan posibles movimientos del rover

Luego se calcula la ruta óptima, evitando zonas peligrosas y priorizando áreas científicamente interesantes.

📊 Visualización de resultados

TerrainExplorer permite explorar los resultados mediante:

🗺️ Mapa mineralógico 2D

Visualización de los minerales detectados a partir del clustering espectral.

🌄 Modelo 3D del terreno

Representación interactiva del DEM con la distribución mineralógica.

🚗 Ruta óptima del rover

Ruta calculada sobre el terreno mediante algoritmos de grafos.

⚠️ Indicador de riesgo

Estimación del riesgo operativo para el rover.

🧪 Tecnologías utilizadas

Python

Streamlit

NumPy

Scikit-learn

Plotly

NetworkX

GDAL

Rasterio
