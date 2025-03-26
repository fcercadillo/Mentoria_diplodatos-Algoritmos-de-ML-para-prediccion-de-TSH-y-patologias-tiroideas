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
