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
| `diagnostico`             | Categórica | Clasificación clínica general del estado tiroideo (`Normal`, `Hipotiroideo`, `Hipertiroideo`.). |
| `diagnostico_especifico`  | Categórica | Diagnóstico clínico detallado del estado tiroideo. |

---

### Clases en `diagnostico`

| Clase           | Interpretación clínica |
|----------------|------------------------|
| `Normal`       | El paciente no presenta alteraciones tiroideas. Los valores de TSH, T3 y T4 se encuentran dentro de los rangos clínicamente aceptados. |
| `Hipotiroideo` | El paciente presenta signos de hipofunción tiroidea: TSH elevada y T3/T4 bajos o normales. |
| `Hipertiroideo`| El paciente presenta signos de hiperfunción tiroidea: TSH suprimida y T3/T4 elevados. |


---

### Clases en `diagnostico_especifico`

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

Este dataset fue obtenido a partir de **fuentes públicas** y se utiliza **solo con fines educativos y de investigación**.

Se aplicó un **filtro curado** para conservar únicamente los registros con:
- Datos clínicos completos
- Valores hormonales disponibles
- Diagnóstico tiroideo real asociado

Esto permite entrenar modelos de **predicción de TSH** y **clasificación de patologías tiroideas**, con etiquetas verificables.

