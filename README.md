# GBM Learning Repo

## Objetivo

Este repositorio registra mi aprendizaje de **Gradient Boosting Models (GBM)** en Python, con foco en aplicaciones de **pricing / seguros** (retención, frecuencia, severidad, etc.).

## Alcance

- Entender la intuición de los modelos tipo GBM (árboles secuenciales).
- Implementar modelos con:
  - `sklearn.GradientBoostingRegressor` / `GradientBoostingClassifier`
  - `XGBoost`
  - `LightGBM`
- Practicar:
  - Preparación de datos
  - Tuning básico de hiperparámetros
  - Evaluación de modelos
  - Documentación de experimentos

## Estructura del repositorio

- `notebooks/`: notebooks de práctica (Colab / Jupyter).
- `data/`: datos crudos y procesados.
- `src/`: funciones reutilizables (data prep, modelos).
- `experiments/`: notas y resultados de experimentos.
- `reports/`: figuras y reportes generados.

## Plan (borrador)

- Semana 1–2:  
  - GBM básico con `sklearn` sobre dataset simple.
- Semana 3–4:  
  - XGBoost: baseline + tuning básico.
- Semana 5–6:  
  - LightGBM: datasets más grandes / más features.
- Luego:  
  - Aplicar la lógica a datos más cercanos a seguros/pricing.

## Cómo correr los notebooks

1. Abrir el notebook en Google Colab.
2. Instalar dependencias si hace falta (`xgboost`, `lightgbm`).
3. Ejecutar todas las celdas.

## Notas

Este repo está pensado como registro personal de aprendizaje.
