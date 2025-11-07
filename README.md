# recopilacion_y_almacenamiento_de_datos_-SQL-
Proyecto de recopilación y almacenamiento de datos con SQL para la empresa Zuber en Chicago

# 🚖 Análisis de Viajes en Taxi — Proyecto Zuber (Chicago)

# 🧠 Descripción del Proyecto

Análisis de datos para Zuber, una nueva empresa de viajes compartidos que busca expandirse en Chicago.
El objetivo es analizar patrones en los viajes y entender cómo factores externos, como el clima, afectan la demanda.

A través de consultas SQL y análisis en Python, se explorarán datos reales de viajes, condiciones meteorológicas y empresas competidoras para responder preguntas de negocio y validar hipótesis sobre la relación entre el clima y la duración de los viajes.

# 🎯 Objetivos del Proyecto

Explorar la base de datos de Zuber para identificar patrones en los viajes de taxi.

Analizar la actividad de las diferentes empresas competidoras.

Evaluar el impacto de las condiciones climáticas (lluvia o tormenta) sobre la duración de los viajes.

Poner en práctica habilidades de SQL, análisis de datos con Python y pruebas estadísticas.

# 🗂️ Descripción de los Datos

El proyecto utiliza una base de datos relacional con cuatro tablas principales, además de tres archivos .csv exportados a partir de consultas SQL.

1. neighborhoods — Barrios de Chicago
Columna	Descripción
name	Nombre del barrio
neighborhood_id	Código del barrio
2. cabs — Vehículos registrados
Columna	Descripción
cab_id	Identificador único del vehículo
vehicle_id	ID técnico del vehículo
company_name	Empresa propietaria del taxi
3. trips — Viajes realizados
Columna	Descripción
trip_id	Identificador del viaje
cab_id	Identificador del vehículo
start_ts	Fecha y hora de inicio del viaje
end_ts	Fecha y hora de finalización del viaje
duration_seconds	Duración del viaje en segundos
distance_miles	Distancia recorrida en millas
pickup_location_id	ID del barrio de inicio
dropoff_location_id	ID del barrio de destino
4. weather_records — Condiciones meteorológicas
Columna	Descripción
record_id	Identificador del registro
ts	Fecha y hora del registro
temperature	Temperatura al momento del registro
description	Condiciones meteorológicas (ej. “light rain”, “scattered clouds”)

# 💡 Nota:
No existe una relación directa entre trips y weather_records, pero pueden vincularse usando la hora de inicio del viaje (start_ts) y la hora del registro meteorológico (ts).

# 💻 Conjuntos de Datos Exportados (CSV)

Durante el proyecto, se generan tres archivos CSV con los resultados de las consultas SQL:

project_sql_result_01.csv

Contiene el número de viajes (trips_amount) por compañía de taxis (company_name) del 15 al 16 de noviembre de 2017.

project_sql_result_04.csv

Muestra los barrios de destino (dropoff_location_name) y el promedio de viajes que finalizaron en cada uno durante noviembre de 2017.

project_sql_result_07.csv

Incluye información sobre los viajes desde Loop hasta O’Hare los sábados, junto con las condiciones meteorológicas y la duración del viaje.

Campos: start_ts, weather_conditions, duration_seconds.

# ⚙️ Etapas del Proyecto

1️⃣ Obtención de Datos Meteorológicos

Se analiza la información del clima en Chicago en noviembre de 2017 desde el sitio web:
Chicago Weather Data

2️⃣ Análisis Exploratorio en SQL

Consultas principales:

Número de viajes por empresa (15–16 noviembre).

Empresas con “Yellow” o “Blue” en su nombre (1–7 noviembre).

Agrupación de empresas más populares (Flash Cab, Taxi Affiliation Services y otras).

Resultados ordenados y agrupados por cantidad de viajes (trips_amount).

3️⃣ Análisis de la Hipótesis en SQL

Se identifican los barrios Loop (ID 50) y O’Hare (ID 63).

Se clasifican las condiciones climáticas en dos grupos:

"Bad" → si description contiene “rain” o “storm”.

"Good" → en caso contrario.

Se combinan los datos de viajes y clima usando las columnas de tiempo (start_ts = ts).

Se extraen los viajes de los sábados entre Loop y O’Hare junto con las condiciones climáticas y duración.

4️⃣ Análisis Exploratorio en Python

Importación y verificación de los archivos CSV.

Conversión de tipos de datos y revisión de valores ausentes.

Visualizaciones:

📊 Empresas de taxi vs número de viajes.

🗺️ Top 10 barrios por promedio de viajes finalizados.

Se extraen conclusiones descriptivas a partir de los gráficos.

5️⃣ Prueba de Hipótesis (Python)

Hipótesis estadística:

H₀: No hay diferencia en la duración media de los viajes entre días con “buen” y “mal” clima.

H₁: La duración media de los viajes desde Loop a O’Hare sí cambia los sábados lluviosos.

Se aplica una prueba t de muestras independientes (scipy.stats.ttest_ind) para comparar los grupos.

Se define el nivel de significación (α) y se interpretan los resultados.

6️⃣ Conclusiones

Se resumen los hallazgos clave sobre:

Las empresas más populares.

Los barrios con más llegadas.

El efecto del clima en la duración de los viajes.

Se formulan recomendaciones estratégicas para la empresa Zuber.

# 📈 Tecnologías Utilizadas

SQL — consultas, joins, agrupaciones y filtrado de datos.

Python

pandas

numpy

matplotlib / seaborn

scipy.stats

Jupyter Notebook — análisis, visualización y documentación del proceso.

# 🧾 Resultados Esperados

Identificación de las empresas con mayor número de viajes.

Reconocimiento de los barrios más transitados de Chicago.

Determinación de si el clima influye significativamente en la duración de los viajes entre Loop y O’Hare.

Demostración de habilidades combinadas en SQL + análisis estadístico en Python.

# ✍️ Autor

Lorena Urquijo N.
Analista de Datos — Proyecto Zuber
📅 Año: 2025
