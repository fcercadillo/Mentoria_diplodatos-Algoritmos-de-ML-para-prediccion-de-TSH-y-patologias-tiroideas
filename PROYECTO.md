# Proyecto de Machine Learning: Estimación de TSH y Clasificación del Estado Tiroideo

## Breve descripción del proyecto

Este proyecto busca desarrollar un modelo de Machine Learning que permita:

- Predecir los niveles de TSH.
- Clasificar el estado tiroideo como **normal** o **patológico**.

La predicción se basa en variables clínicas y de laboratorio disponibles, con el objetivo de asistir en contextos clínicos donde los datos categóricos se han perdido o no están disponibles.

---

## Reseña del dataset

El dataset está compuesto por una cohorte de aproximadamente **1.000 pacientes** e incluye las siguientes variables:

- T3
- T4L
- ATPO
- IMC
- Edad
- Etnicidad
- Valores reales de TSH
- Clasificación clínica del estado tiroideo (normal o patológico)

Este conjunto de datos permite entrenar y validar modelos tanto de regresión como de clasificación.

---

##  Problemas asociados

- Los valores de TSH no siguen una distribución normal.
- Presencia de **datos faltantes**.
- **Relaciones no lineales** entre variables clínicas y TSH.
- La TSH tiene un **orden de magnitud crítico** para el diagnóstico, por lo que pequeños errores impactan clínicamente.
- La **clasificación se realizará a partir de valores estimados**, no reales.

---

## Presentación detallada del caso aplicado

Imaginemos un laboratorio de análisis clínico que, tras una migración de sistema, **pierde las categorías clínicas de TSH** de muchos pacientes.

Como **no es viable repetir todos los análisis**, el laboratorio convoca a un equipo interdisciplinario para desarrollar un modelo de ML que permita:

1. **Estimar los valores de TSH perdidos**.
2. **Recuperar la clasificación de los pacientes como normales o patológicos**, facilitando la toma de decisiones médicas.

---

## Etapas del proyecto

1. **Análisis exploratorio de los datos (EDA)**
2. **Curado del dataset**
3. **Desarrollo del modelo de Machine Learning**, dividido en:

### Etapa 1: Estimación numérica de valores de TSH

- Entrenamiento de modelos de regresión.
- Validación mediante métricas adecuadas (MAE, RMSE, R²).
- Agrupación de los valores estimados en tres categorías:  
  - **Bajo**
  - **Normal**
  - **Alto**

### Etapa 2: Clasificación del estado tiroideo

- Clasificación binaria: **Normal** / **Patológico**  
- Entrenamiento sobre las categorías derivadas del paso anterior.

### Propuesta adicional (extensión del proyecto)

1. Clasificación del **tipo de patología tiroidea**:  
   - Hipotiroidismo  
   - Hipertiroidismo  

2. Subclasificación de severidad:  
   - **Clínico**  
   - **Subclínico**

---
