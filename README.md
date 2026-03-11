##pasos para instalar TerrainExplorer

Crear entorno virtual:

-conda create -n mars python=3.11
  
Activar:

-venv\Scripts\activate
  
Instalar requirimientos:

-conda install -r requirements.txt
  
Correr TerrainExplorer con:

-streamlit main.py

##Cómo funciona 

-Carga datos planetarios

 Imagen hiperespectral (.img + .hdr) y Modelo de elevación DEM (.tif)

-Procesa los datos

-Limpia valores inválidos

-Reduce dimensionalidad (PCA) para trabajar sólo con bandas que concentran una mayor variedad de datos

-Detecta minerales (K-Means). Los minerales más asociados con agua són hematita, arcilla y minerales hidratados

-Calcula pendiente para calcular el riesgo para el rover (pendiente 
 menor significa que el camino está más seguro y zonas más bajas indican valles que aumentan
  la probabilidad de agua ahí antiguamente)

-Planifica una ruta donde construye un grafo del terreno

-Encuentra la ruta óptima evitando zonas peligrosas

##Los resultados se pueden visualizar con

-mapa 2D mineralógico

-modelo 3D del terreno

-ruta del rover trazada por los grafos

-indicador de riesgo

##🧪 Tecnologías utilizadas

-Python

-Streamlit

-NumPy

-Scikit-learn

-Plotly

-NetworkX

-GDAL / Rasterio
