Telecom X Parte 2 – Predicción de Cancelación (Churn)
===================================================================

## 📝 Objetivo
--------

Desarrollar modelos predictivos para identificar clientes con alta probabilidad de cancelar sus servicios en Telecom X, utilizando técnicas de machine learning. El proyecto incluye preparación de datos, análisis exploratorio, modelado y evaluación de desempeño.

## 🛠 Metodología
-----------

### 1\. Preparación de Datos

*   **Limpieza y Codificación**: Se eliminaron columnas irrelevantes (`id_cliente`, `cuentas_diarias`) y se aplicó One-Hot Encoding a variables categóricas (`genero`, `serv_internet`, `contrato`, `metodo_pago`).
    
*   **Balanceo de Clases**: Se evaluó el desbalance entre clases (25.7% cancelaciones vs. 74.3% no cancelaciones) y se probaron técnicas como SMOTE (oversampling) y NearMiss (undersampling).
    
*   **Normalización**: Se estandarizaron los datos para modelos sensibles a la escala (Regresión Logística) usando `StandardScaler` y `RobustScaler`.
    

### 2\. Análisis Exploratorio (EDA)

*   **Correlaciones**: Se identificaron variables con mayor correlación con el churn:
    
    *   **Directa**: `contrato_Mensual` (0.396), `serv_internet_Fibra optica` (0.301).
        
    *   **Inversa**: `antiguedad` (-0.344), `contrato_Bi-anual` (-0.295).
        
*   **Multicolinealidad**: Se calculó el VIF para detectar redundancias. Se eliminaron variables con VIF infinito (ej: `serv_internet_DSL`) y se corrigió la alta colinealidad entre `pago_mensual` y `pago_total`.
    

### 3\. Modelado

Se evaluaron tres modelos:

1.  **Árbol de Decisión**:
    
    *   Precisión: 77%        
    *   AUC-ROC: 75%
        
2.  **Regresión Logística**:
    
    *   Precisión: 80%        
    *   AUC-ROC: 83%
        
3.  **Random Forest**:
    
    *   Precisión: 78%        
    *   AUC-ROC: 79%
        

### 4\. Evaluación de Modelos

*   **Métricas Clave**:
    
    *   **Recall**: Capacidad de detectar casos positivos (churn).
        
    *   **Precisión**: Calidad de las predicciones positivas.
        
    *   **F1-Score**: Balance entre precisión y recall.
        
*   **Trade-offs**:
    
    *   Priorizar recall si es crítico no omitir cancelaciones (ej., retención de clientes).
        
    *   Priorizar precisión si los falsos positivos son costosos.
        

## Resultados
----------

*   **Mejor Modelo**: Regresión Logística, con un AUC-ROC de 83% y precisión del 80%.
    
*   **Variables Clave**:
    
    *   `contrato_Mensual` y `serv_internet_Fibra optica` están fuertemente asociadas con la cancelación.
        
    *   `antiguedad` y `contrato_Bi-anual` son factores protectores contra el churn.
        

## Conclusión
----------

El proyecto proporciona herramientas robustas para predecir el churn en Telecom X, destacando la importancia de contratos a largo plazo y la antigüedad del cliente como factores clave. Los modelos permiten anticipar cancelaciones y diseñar estrategias de retención efectivas.

* * *

💻**Herramientas Utilizadas**:
- Python
-  Scikit-Learn
-  Pandas
-  Matplotlib
-  Seaborn
-  Plotly.  
**Repositorio**: [GitHub - Challenge Telecom X](https://github.com/freedox-cts/challenge-telecom-x)

Para más detalles, consulta el código y los análisis completos en el repositorio.