# Proyecto de Machine Learning: Estimación de TSH y Clasificación del Estado Tiroideo

### **Breve descripción del proyecto**
Desarrollar un modelo de Machine Learning que permita predecir los niveles de TSH y clasificar el estado tiroideo (normal o patológico) a partir de variables clínicas y de laboratorio.

## **Presentación detallada del proyecto**

El proyecto busca presentarse mediante un caso aplicado, que permita contextualizar de forma práctica y real la utilidad del modelo.

Supongamos el caso de un laboratorio de análisis bioquímico que, debido a una migración de sistema, perdió en su base de datos las categorías clínicas de TSH correspondientes a los últimos estudios realizados.

Dado que la cantidad de personas afectadas es muy grande, no es posible repetir todos los análisis de sangre correspondientes. Por este motivo, y para identificar rápidamente a las personas que podrían presentar un estado patológico y que requieren una derivación clínica, el laboratorio conforma un equipo interdisciplinario para desarrollar un modelo de MLque permita:

- **Estimar los valores de TSH faltantes**.
- **Recuperar la clasificación de cada paciente como normal o patológico**, de forma tal que los médicos puedan decidir el tratamiento o seguimiento adecuado según el estadio clínico de cada caso.

---

### **Etapas del proyecto:**

1. **Análisis exploratorio de los datos.**
2. **Curado del dataset.**
3. **Desarrollo del algoritmo de Machine Learning.**
    
    Dentro de esta tercera etapa, la propuesta del proyecto se estructura de la siguiente manera:
    
    1. **Etapa 1: Estimación numérica de los valores de TSH** El objetivo inicial es estimar los valores de TSH y evaluar la precisión del modelo. 
        
        Luego, como la TSH se mide en miliunidades por litro (mIU/L) y su clasificación clínica es muy sensible, las estimaciones se agruparán en tres categorías: Bajo/Normal/Alto.
        
    2. **Clasificación según estado tiroideo (Normal/Patológico):** Con las categorías ya establecidas, se desarrollará un modelo de clasificación para determinar si cada paciente se encuentra en un estado normal o presenta una alteración tiroidea.
    3. **Propuesta adicional:**
        1. Clasificación del tipo de patología tiroidea (Hipotiroidismo/Hipertiroidismo).
        2. Subclasificación de cada estado patológico según su grado de severidad (Clínico/Subclínico)

---

---

###  Problemas asociados al dataset

En esta etapa, el dataframe se encuentra **procesado y curado** para ser utilizado como ejemplo. Sin embargo, aún con la data limpia, persisten las siguientes **complicaciones inherentes a su estructura**:

- Los valores de **TSH no siguen una distribución normal**, lo que puede afectar el desempeño de modelos lineales.
- Existen **datos faltantes** en variables hormonales clave (`t3t`, `t4l`, `t4t`, `tsh`), representados por símbolos como `'?'`.
- Se observan **relaciones no lineales** entre variables clínicas (edad, IMC, ATPO, T3, T4) y los niveles de TSH.
- El **margen de error es clínicamente sensible**, debido a los **órdenes de magnitud** en los valores de TSH.
- Las **variables categóricas requieren codificación adecuada** para ser utilizadas por los algoritmos de Machine Learning.
- Existe **desbalance de clases** entre pacientes sin alteraciones tiroideas y aquellos con disfunciones diagnosticadas.

### Estrategia para simular escenarios reales

Para incrementar la complejidad del ejercicio y simular problemas comunes en datasets clínicos, la idea es aplicarán las siguientes modificaciones al momento de entregar el dataset:

| **Estrategia**                        | **Descripción**                                                             |
|--------------------------------------|-----------------------------------------------------------------------------|
| **Introducir valores nulos aleatorios** | Quitar valores en columnas clave.                        |
| **Agregar errores de tipeo**         | Introducir variantes como `"Muer"` o `"Hombe"` en la columna `sexo`.         |
| **Agregar columnas duplicadas**      | Crear duplicados como `tsh2 = tsh` para simular errores de carga.           |
| **Introducir _outliers_ artificiales** | Ejemplo: `TSH = 999`, `T4L = -10`.                                          |
| **Desordenar categorías**            | Variar etiquetas similares como `"hipotiroid"` vs `"hipotiroidismo"`.       |
| **Mezclar etiquetas de diagnóstico** | Alterar casos entre `"Negativo"` y `"Sin alteración"`.                      |
| **Agregar columnas irrelevantes**    | Incorporar columnas como `ID_paciente`, `comentarios`.                      |

