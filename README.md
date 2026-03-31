# 🛡️ Fraud Detection Pipeline (Data Lake + Spark)

## 📌 Descripción del proyecto

Este proyecto forma parte de un caso práctico de Big Data aplicado en el contexto de una empresa de eCommerce ficticia llamada **ElectroShop**, cuyo principal problema es la detección de **transacciones fraudulentas**.

El objetivo es construir un pipeline completo de datos que permita:

- Integrar múltiples fuentes de datos heterogéneas
- Limpiar y estructurar la información
- Generar features relevantes
- Analizar el comportamiento de los usuarios
- Detectar patrones asociados al fraude

---

## 🧱 Arquitectura del sistema

El proyecto se divide en dos fases principales (a la espera de ir desarrollando más):

### 🔹 1. Construcción del Data Lake (ETL)

Se realiza un proceso de ingesta, limpieza y transformación de datos provenientes de:

- `transacciones.csv` → datos de pagos  
- `tickets_soporte.json` → incidencias y reportes de fraude  
- `logs_web.txt` → actividad web de los usuarios  

El resultado es un **Data Lake unificado y estructurado en formato Parquet**.

---

### 🔹 2. Procesamiento distribuido con Apache Spark

A partir del Data Lake:

- Se procesan grandes volúmenes de logs  
- Se calculan métricas de comportamiento por usuario  
- Se cruzan datos de navegación y transacciones  
- Se analiza la diferencia entre usuarios fraudulentos y legítimos  

---

## 📂 Estructura del repositorio

```bash
fraud-detection-pipeline/
│
├── notebooks/
│   ├── 01_etl_pipeline.ipynb
│   ├── 02_spark_processing.ipynb
│
├── data_sample/   # (opcional)
│   ├── logs_web_sample.txt
│   ├── transacciones_sample.csv
│   ├── tickets_soporte_sample.json
│
├── docs/
│   └── arquitectura.png
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

## ▶️ Cómo ejecutar el proyecto

1. Clonar el repositorio:

```bash
git clone <url-del-repo>
cd fraud-detection-pipeline
```

2. Instalar dependencias:

```bash
pip install -r requirements.txt
```

3. Ejecutar los notebooks en orden:

* 01_etl_pipeline.ipynb
* 02_spark_processing.ipynb

## ⚠️ Sobre los datos

Los datasets originales **no se incluyen en el repositorio debido a su tamaño**.

Para ejecutar el proyecto, se requiere disponer de los siguientes ficheros:

- `transacciones.csv`
- `tickets_soporte.json`
- `logs_web.txt`

Opcionalmente, se incluyen muestras reducidas en la carpeta `data_sample/`.

---

## 🧪 Núcleo Formativo 1: ETL y Data Lake

En este notebook se implementa:

- Ingesta de datos desde múltiples formatos (CSV, JSON, logs)
- Parsing de logs mediante expresiones regulares
- Limpieza y transformación de datos:
  - Normalización de estados
  - Conversión de tipos de datos
  - Gestión de valores nulos
- Feature engineering:
  - Unión de datasets
  - Creación de variables como `hora_transaccion`
- Almacenamiento en formato **Parquet** en un Data Lake

---

## ⚡ Núcleo Formativo 2: Procesamiento con Spark

En esta fase se utiliza **Apache Spark** para:

- Procesar grandes volúmenes de datos de logs
- Calcular métricas de comportamiento:
  - Número de acciones previas
  - URLs distintas visitadas
- Filtrar eventos en una ventana temporal de 15 minutos
- Generar un dataset enriquecido para análisis de fraude

---

## 📊 Análisis de comportamiento

Se analiza la hipótesis:

> Los usuarios fraudulentos se comportan de forma diferente a los usuarios legítimos

Para ello:

- Se agrupan las transacciones por tipo (fraude vs no fraude)
- Se comparan métricas como:
  - Número de acciones previas
  - Monto de la transacción
- Se generan visualizaciones comparativas

---

## 🧠 Conclusiones

- Se ha identificado un patrón de comportamiento diferenciado en usuarios fraudulentos  
- La combinación de múltiples fuentes de datos es clave para detectar anomalías  
- El uso de Spark permite procesar grandes volúmenes de información de forma eficiente  
- El Data Lake unificado facilita el análisis y la generación de insights  

---

## 🚀 Tecnologías utilizadas

- Python  
- Pandas  
- Apache Spark  
- Jupyter Notebooks  
- Parquet  

---

## 💡 Aprendizajes clave

- Construcción de pipelines ETL completos  
- Procesamiento de datos semi-estructurados  
- Feature engineering aplicado a fraude  
- Procesamiento distribuido con Spark  
- Diseño de Data Lakes  
- Análisis de comportamiento de usuarios  

---

## 🧭 Próximos pasos

- Crear un pipeline de validación para estudiar el comportamiento del dataset
- Implementar modelos de Machine Learning para detección de fraude  
- Automatizar el pipeline
- Escalar el sistema a producción  

---

## 📌 Notas

- Proyecto académico  
- Datos generados artificialmente
- Enfoque en diseño de pipeline y análisis de datos