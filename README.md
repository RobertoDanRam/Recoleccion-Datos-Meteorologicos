# Recolección de Datos Meteorológicos (Big Data)

Este proyecto consiste en un Jupyter Notebook (`CollectWeather.ipynb`) desarrollado en Python para extraer, procesar y almacenar datos meteorológicos. Utiliza la API de OpenWeatherMap para obtener pronósticos y almacena la información estructurada en una base de datos MySQL local[cite: 7].

**Autor:** Roberto Daniel Ramos Flores

## Características Principales

*   **Extracción de Datos (API):** Realiza peticiones HTTP a la API de OpenWeatherMap para obtener el pronóstico del clima de una ciudad específica (en este caso, Aberdeen, GB)[cite: 7].
*   **Procesamiento de JSON:** Extrae información relevante del archivo JSON devuelto por la API, como fecha/hora, temperatura, humedad, estado del clima, velocidad del viento, y volumen de lluvia/nieve[cite: 7].
*   **Manipulación de Datos (Pandas):** Utiliza la librería Pandas para estructurar los datos extraídos en un DataFrame, facilitando su visualización y limpieza[cite: 7].
*   **Manejo de Valores Nulos:** Reemplaza los valores `NaN` (Not a Number) generados por Pandas con valores `None`, asegurando la compatibilidad al insertar los datos en la base de datos SQL[cite: 7].
*   **Almacenamiento en Base de Datos (MySQL):** Establece una conexión con una base de datos MySQL local (`gans`) utilizando `mysql.connector`. Itera sobre las filas del DataFrame e inserta los registros en la tabla `weather_data`[cite: 7].
*   **Manejo de Errores y Transacciones:** Implementa bloques `try-except` para capturar errores durante la inserción en la base de datos y activa el `autocommit` para evitar bloqueos por transacciones abiertas[cite: 7].
*   **Seguridad de Credenciales:** Importa las claves de la API desde un archivo separado (`keys.py`) para evitar exponer información sensible en el código principal[cite: 7].

## Tecnologías Utilizadas

*   **Lenguaje:** Python[cite: 7]
*   **Entorno:** Jupyter Notebook[cite: 7]
*   **Librerías Python:**
    *   `requests`: Para realizar peticiones HTTP a la API[cite: 7].
    *   `pandas`: Para la manipulación y análisis de datos en DataFrames[cite: 7].
    *   `numpy`: Para el manejo de valores nulos (`np.nan`)[cite: 7].
    *   `mysql-connector-python`: Para la conexión y ejecución de consultas en MySQL[cite: 7].
*   **Base de Datos:** MySQL[cite: 7]
*   **API:** OpenWeatherMap[cite: 7]

## Estructura del Proyecto

El repositorio `BigData`[cite: 7] contiene los siguientes archivos relevantes para este proceso:

*   `CollectWeather.ipynb`: Jupyter Notebook principal que contiene el script de extracción, transformación y carga (ETL) de los datos meteorológicos[cite: 7].
*   `keys.py`: Archivo (no incluido en el código mostrado por seguridad) que almacena la clave de la API (`OWM_key`)[cite: 7].
