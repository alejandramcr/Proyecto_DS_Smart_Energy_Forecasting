# Proyecto_DS_Smart_Energy_Forecasting
📊 Pronóstico de Demanda Eléctrica con Skforecast

- Este proyecto implementa un flujo completo de **pronóstico de series temporales para la demanda eléctrica en Perú**, utilizando la librería Skforecast. Se aplican técnicas de análisis exploratorio de datos, feature engineering y modelos de machine learning para predecir el consumo eléctrico en intervalos de 30 minutos, con especial atención en patrones diarios, semanales y estacionales.
---

## 📑 Descripción del Proyecto 

- El objetivo principal es predecir la **demanda eléctrica (MW)** de la última semana de la serie, entrenando un modelo en datos históricos de 2023 y 2024.
Se exploran los patrones de consumo, se identifican factores que afectan la demanda (día de la semana, feriados, estacionalidad), y se construye un modelo autoregresivo basado en XGBRegressor para generar pronósticos confiables.
---

## 🛠️ Tecnologías Utilizadas

- **Python 3.12**
- [Pandas](https://pandas.pydata.org/) para manipulación de datos  
- [Matplotlib](https://matplotlib.org/) y [Seaborn](https://seaborn.pydata.org/) para visualizaciones  
- [Skforecast](https://joaquinamatrodrigo.github.io/skforecast/) para modelado y backtesting  
- [XGBoost](https://xgboost.readthedocs.io/) como algoritmo de machine learning  
- [Scikit-learn](https://scikit-learn.org/stable/) para métricas y utilidades  
- [holidays](https://pypi.org/project/holidays/) para identificar días feriados en Perú  

---


 ## 🔍 Análisis Exploratorio

- Conversión de fechas a formato datetime y ajuste de frecuencia a 30 min

- Visualización de patrones diarios y estacionales

- Identificación de días feriados y su impacto en la demanda

## 🤖 Modelado y Validación

Se utiliza un ForecasterRecursive con XGBRegressor:

Grid Search para optimizar hiperparámetros (max_depth, n_estimators) y número de lags.

Backtesting con 7 folds (última semana), evaluando la métrica MSE.

El mejor modelo usa:

- 96 lags (captura dependencias de 2 días)

- max_depth = 8, n_estimators = 250

- Backtesting MSE: ≈ 10 590

## 📈 Resultados

El modelo captura bien los patrones diarios y semanales.

Las predicciones siguen de cerca los picos y valles de la demanda, aunque tienden a subestimar picos máximos y sobreestimar valles mínimos.

**Métricas finales:** 

- MSE test: 9 958.18 (error significativamente más bajo que el modelo inicial univariado)

- Backtesting MSE: 10 589.76

Ejemplo de resultado (última semana):

## ✅ Interpretación: 
- El modelo es capaz de capturar la estacionalidad intradía y semanal de la demanda eléctrica, ofreciendo pronósticos ajustados a la realidad con un error medio reducido.

## 🚀 Próximos Pasos

- Incluir variables exógenas (temperatura, indicadores económicos).

- Probar modelos adicionales (LightGBM, RandomForest).

- Evaluar métricas complementarias como RMSE y MAPE.

- Desplegar el modelo como API o dashboard de visualización.

## 📜 Autor

Proyecto desarrollado por Alejandra Cruz R.
Bootcamp Xperience – Septiembre 2025
