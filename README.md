# Proyecto_DS_Smart_Energy_Forecasting
📊 Pronóstico de Demanda Eléctrica con Skforecast

Este proyecto implementa un flujo completo de pronóstico de series temporales para la demanda eléctrica en Perú, utilizando la librería Skforecast. Se aplican técnicas de análisis exploratorio de datos, feature engineering y modelos de machine learning para predecir el consumo eléctrico en intervalos de 30 minutos, con especial atención en patrones diarios, semanales y estacionales.

📑 Descripción del Proyecto

El objetivo principal es predecir la demanda eléctrica (MW) de la última semana de la serie, entrenando un modelo en datos históricos de 2023 y 2024.
Se exploran los patrones de consumo, se identifican factores que afectan la demanda (día de la semana, feriados, estacionalidad), y se construye un modelo autoregresivo basado en XGBRegressor para generar pronósticos confiables.

🛠️ Tecnologías Utilizadas

Python 3.12

Pandas
 para manipulación de datos

Matplotlib
 y Seaborn
 para visualizaciones

Skforecast
 para modelado y backtesting

XGBoost
 como algoritmo de machine learning

Scikit-learn
 para métricas y utilidades

holidays
 para identificar días feriados en Perú
