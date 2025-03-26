# Mentoría Diplodatos: Algoritmos de ML para Predicción de TSH y Patologías Tiroideas

## Descripción del Dataset

El archivo `df_tiroides_mentoria_diplodatos.csv` contiene información clínica y de laboratorio de **1.950 pacientes**, con el objetivo de desarrollar modelos de Machine Learning que permitan estimar niveles de TSH y clasificar el estado tiroideo de los pacientes.

---

### Estructura del Dataset

- Cada fila del archivo representa un paciente único. 
- Las columnas contienen variables demográficas, antecedentes médicos y resultados de laboratorio obtenidos mediante análisis clínicos.

- **Total de registros:** 1.950 pacientes  
- **Total de columnas:** 13 variables  
- **Tipos de datos:** numéricos, categóricos, booleanos y de texto

El dataset incluye:
- **3 clases** en la columna `diagnostico` (estado tiroideo general).
- **6 clases** en la columna `diagnostico_especifico` (diagnóstico clínico detallado).

###  Variables objetivo

- `tsh`: valor numérico continuo que representa el nivel de hormona estimulante de la tiroides.
- `diagnostico`: etiqueta binaria.
- `diagnostico_especifico`: etiqueta multiclase.

---

### Descripción  de variables

| Columna                    | Tipo       | Descripción |
|----------------------------|------------|-------------|
| `edad`                     | Numérica   | Edad del paciente en años. |
| `sexo`                     | Categórica | Sexo biológico (`F`, `M`). |
| `embarazo`                 | Booleana   | Indica si la paciente está embarazada. |
| `etnia`                    | Categórica | Grupo étnico autorreportado. |
| `imc`                      | Numérica   | Índice de masa corporal (IMC). |
| `antecedentes_familiares` | Categórica | Antecedentes familiares de enfermedades tiroideas (`Sí`/`No`). |
| `t3t`                      | Numérica   | Triyodotironina total (T3). |
| `t4l`                      | Numérica   | Tiroxina libre (T4L). |
| `t4t`                      | Numérica   | Tiroxina total (T4T). |
| `atpo`                     | Numérica   | Niveles de anticuerpos antiperoxidasa tiroidea. |
| `tsh`                      | Numérica   | Nivel de hormona TSH. |
| `diagnostico`             | Categórica | Clasificación clínica general del estado tiroideo (`Normal`, `Hipotiroideo`, `Hipertiroideo`.). <sup>*1</sup>|
| `diagnostico_especifico`  | Categórica | Diagnóstico clínico detallado del estado tiroideo.  <sup>*3</sup> |

---

### Clases en `diagnostico` <sup>*1</sup>

| Clase           | Interpretación clínica | 
|----------------|------------------------|
| `Normal`       | El paciente no presenta alteraciones tiroideas. Los valores de TSH, T3 y T4 se encuentran dentro de los rangos clínicamente aceptados. <sup>*2</sup> |
| `Hipotiroideo` | El paciente presenta signos de hipofunción tiroidea: TSH elevada y T3/T4 bajos o normales. <sup>*2</sup>  |
| `Hipertiroideo`| El paciente presenta signos de hiperfunción tiroidea: TSH suprimida y T3/T4 elevados. |

---
#### Valores de Referencia de Estudios Tiroideos <sup>*2</sup>  
Los valores para las hormonas tiroideas pueden variar ligeramente según el laboratorio, la zona demográfica y la metodología utilizada.  
Como estándar para este caso vamos a utilizar los siguientes rangos de referencia:

| Estudio                           | Unidad   | Valores de Referencia                                                                                     |
|-----------------------------------|----------|------------------------------------------------------------------------------------------------------------|
| Anticuerpos Antiperoxidasa (ATPO) | UI/mL    | Hasta 5,6                                                                                                   |
| Tiroxina Total (T4T)              | µg/dL    | 7 días a 1 año: 5,9 – 13,7 <br> 1 a 14 años: 5,0 – 10,3 <br> Mujeres 14-19: 5,5 – 13,0 <br> Varones 14-19: 4,7 – 8,6 <br> Mayores de 19 años: 4,9 – 11,7 |
| Tiroxina Libre (T4L)              | ng/dL    | 5 a 14 días: 1,05 – 3,21 <br> 15 a 29 días: 0,68 – 2,53 <br> 30 días a 1 año: 0,89 – 1,7 <br> 1 a 19 años: 0,89 – 1,37 <br> Mayores de 19 años: 0,70 – 1,48 |
| Tirotrofina (TSH)                 | μUI/mL   | 0–2 meses: 1,12 – 6,31 <br> 3–12 meses: 0,96 – 4,90 <br> 13–23 meses: 0,93 – 4,79 <br> 2–12 años: 0,64 – 6,27 <br> 13–18 años: 0,51 – 4,94 <br> Mayores de 18 años: 0,35 – 4,94 |
| Triyodotironina Total (T3T)       | ng/dL    | 0 a 3 días: 96 – 292 <br> 4 a 30 días: 62 – 243 <br> 31 días a 12 meses: 81 – 281 <br> 13 meses a 5 años: 83 – 252 <br> 6 a 10 años: 92 – 219 <br> 11 a 15 años: 80 – 215 <br> 16 a 20 años: 80 – 210 <br> Mayores de 21 años: 60 – 181 |


---

### Clases en `diagnostico_especifico` <sup>*3</sup>

| Clase                        | Interpretación clínica |
|-----------------------------|------------------------|
| `Hipertiroidismo`           | Exceso de producción de hormonas tiroideas, generalmente con TSH baja y T3/T4 elevados. |
| `Hipotiroidismo compensado` | T3 y T4 en valores normales o bajos, pero con TSH elevada: la glándula está siendo sobreestimulada para mantener niveles normales. |
| `Hipotiroidismo primario`   | T3 y T4 bajos junto con TSH elevada: la glándula tiroides falla directamente en producir hormonas. |
| `Hipotiroidismo secundario` | TSH baja con T3 y T4 también bajos: el problema no está en la tiroides sino en la hipófisis o el hipotálamo. |
| `Negativo`                  | No se detecta ninguna alteración tiroidea: niveles hormonales dentro de los rangos clínicos normales. |
| `Tóxico T3`                 | Variante de hipertiroidismo donde T3 está elevada, T4 es normal y la TSH se encuentra suprimida. |

---


---

## ⚠️ Sobre el origen y uso de los datos ⚠️

Este dataset fue obtenido a partir de **fuentes públicas** y se utiliza **exclusivamente con fines educativos**.

Se realizó un **proceso detallado de filtrado y curado** para seleccionar unicamente los registros que:

- Contaran con datos clínicos completos  
- Tuvieran valores hormonales disponibles  
- Incluyeran un diagnóstico tiroideo

Esto permitió construir un conjunto de datos orientado al entrenamiento de modelos de **predicción de TSH** y **clasificación de patologías tiroideas**, con **etiquetas verificables** para evaluar el rendimiento del modelo.

> **Importante:** Este proyecto no tiene fines diagnósticos. Los resultados no deben ser utilizados en contextos clínicos reales.



