Documentación del Proyecto: Predicción de Riesgo Crediticio

Descripción General
Este proyecto desarrolla modelos de machine learning para predecir:

Clasificación: Riesgo de impago (default.payment.next.month).

Regresión: Monto de pago esperado (PAY_AMT4).

Objetivo:

Identificar clientes con alta probabilidad de incumplimiento.

Estimar pagos futuros para optimizar estrategias de cobranza.

📊 Dataset
Origen: UCI Machine Learning Repository
Variables relevantes:

Demográficas: LIMIT_BAL, EDUCATION, AGE.

Historial de pagos: PAY_0 a PAY_6 (retrasos).

Montos: BILL_AMT1-6, PAY_AMT1-6.

Target: default.payment.next.month (binario).

Problemas identificados:

Desbalance de clases (22% defaulters).

Outliers en montos de pago.

Categorías mal documentadas (ej: EDUCATION = 0,5,6).

🚀 Métodología
1. Preprocesamiento
Limpieza de categorías inválidas.

Tratamiento de outliers (imputación por medianas grupales).

Balanceo con SMOTE (solo para clasificación).

2. Feature Engineering
Variables creadas:

TOTAL_DELAY: Suma de meses con retraso.

DEBT_RATIO: Deuda relativa al límite de crédito.


3. Modelado
Tarea	Modelo Elegido	Métricas
Clasificación	XGBoost	AUC-ROC: 0.77, Recall: 0.37
Regresión	XGBoost	RMSE: 3,750, R²: 0.11
