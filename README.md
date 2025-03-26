# Mentoria_diplodatos-Algoritmos-de-ML-para-prediccion-de-TSH-y-patologias-tiroideas

### Descripción del Dataset
  El archivo `df_tiroides_mentoria_diplodatos.csv` contiene información clínica y de laboratorio de 1.950 pacientes. 

### Estructura del dataset
  Cada fila representa un paciente. 
  Las columnas incluyen variables demográficas, antecedentes médicos y resultados de laboratorio

  | Columna                   | Tipo      | Descripción |
  |---------------------------|-----------|-------------|
  | `edad`                    | Numérica  | Edad del paciente en años. |
  | `sexo`                    | Categórica| Sexo biológico (`F`, `M`). |
  | `embarazo`                | Booleana  | Indica si la paciente está embarazada. |
  | `etnia`                   | Categórica| Grupo étnico autorreportado. |
  | `imc`                     | Numérica  | Índice de masa corporal (IMC). |
  | `antecedentes_familiares`| Categórica| Antecedentes familiares de enfermedades tiroideas (`Sí`/`No`). |
  | `t3t`                     | Numérica | Triyodotironina total (T3). Requiere conversión de texto a número. |
  | `t4l`                     | Numérica | Tiroxina libre (T4L). Requiere conversión de texto a número. |
  | `t4t`                     | Numérica | Tiroxina total (T4T). Requiere conversión de texto a número. |
  | `atpo`                    | Numérica  | Niveles de anticuerpos antiperoxidasa tiroidea. |
  | `tsh`                     | Numérica | Valor de TSH (en mIU/L). Requiere conversión de texto a número. |
  | `diagnostico`             | Categórica| Diagnóstico clínico general (`Normal`, `Hipotiroideo`, etc.). |
  | `diagnostico_especifico`  | Categórica| Diagnóstico detallado (`Hipotiroidismo primario`, `Negativo`, etc.). |
