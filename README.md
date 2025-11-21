## Data Science Project: Modelado predictivo para detección de incumplimiento de pago (*default*) en clientes de tarjeta de crédito (clasificación), así como su monto de pago mensual (regresión) en el conjunto de datos 'Default of Credit Card Clients'.
________________________________________
**Objetivo**

El objetivo de este proyecto es, dado el conjunto de datos 'Default of Credit Card Clients', desarrollar modelos para predecir:
1) La cantidad de pago mensual (dólares NT) en Junio, 2005 por parte de un cliente.
2) Si o no un cliente cae en incumplimiento de pago (*default*) para Octubre 2005.
 ________________________________________

**Diccionario**
| Variable                       | Descripción                                                                                                                                                     |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ID**                         | Identificador de cada cliente                                                                                                                                   |
| **LIMIT_BAL**                  | Monto de crédito otorgado en dólares NT (incluye crédito individual y familiar/suplementario)                                                                   |
| **SEX**                        | Género (1 = hombre, 2 = mujer)                                                                                                                                  |
| **EDUCATION**                  | Nivel educativo (1 = posgrado, 2 = universidad, 3 = preparatoria, 4 = otros, 5 = desconocido, 6 = desconocido)                                                  |
| **MARRIAGE**                   | Estado civil (1 = casado, 2 = soltero, 3 = otros)                                                                                                               |
| **AGE**                        | Edad en años                                                                                                                                                    |
| **PAY_0**                      | Estado de pago en septiembre de 2005 (-1 = pago puntual, 1 = retraso de 1 mes, 2 = retraso de 2 meses, …, 8 = retraso de 8 meses, 9 = retraso de 9 meses o más) |
| **PAY_2**                      | Estado de pago en agosto de 2005 (misma escala que PAY_0)                                                                                                       |
| **PAY_3**                      | Estado de pago en julio de 2005 (misma escala que PAY_0)                                                                                                        |
| **PAY_4**                      | Estado de pago en junio de 2005 (misma escala que PAY_0)                                                                                                        |
| **PAY_5**                      | Estado de pago en mayo de 2005 (misma escala que PAY_0)                                                                                                         |
| **PAY_6**                      | Estado de pago en abril de 2005 (misma escala que PAY_0)                                                                                                        |
| **BILL_AMT1**                  | Monto del estado de cuenta en septiembre de 2005 (dólares NT)                                                                                                   |
| **BILL_AMT2**                  | Monto del estado de cuenta en agosto de 2005 (dólares NT)                                                                                                       |
| **BILL_AMT3**                  | Monto del estado de cuenta en julio de 2005 (dólares NT)                                                                                                        |
| **BILL_AMT4**                  | Monto del estado de cuenta en junio de 2005 (dólares NT)                                                                                                        |
| **BILL_AMT5**                  | Monto del estado de cuenta en mayo de 2005 (dólares NT)                                                                                                         |
| **BILL_AMT6**                  | Monto del estado de cuenta en abril de 2005 (dólares NT)                                                                                                        |
| **PAY_AMT1**                   | Monto del pago realizado en septiembre de 2005 (dólares NT)                                                                                                     |
| **PAY_AMT2**                   | Monto del pago realizado en agosto de 2005 (dólares NT)                                                                                                         |
| **PAY_AMT3**                   | Monto del pago realizado en julio de 2005 (dólares NT)                                                                                                          |
| **PAY_AMT4**                   | Monto del pago realizado en junio de 2005 (dólares NT)                                                                                                          |
| **PAY_AMT5**                   | Monto del pago realizado en mayo de 2005 (dólares NT)                                                                                                           |
| **PAY_AMT6**                   | Monto del pago realizado en abril de 2005 (dólares NT)                                                                                                          |
| **default.payment.next.month** | Incumplimiento de pago el próximo mes (1 = sí, 0 = no)                                                                                                          |

________________________________________
**Solución**

Para resolver este reto se realizó, principalmente:

1. El análisis del conjunto de datos y entrenamiento de un modelo de vecinos cercanos (Jupyter notebook).
2. Desarrollo y prueba de una API implementada con FastAPI (scripts .py)

La estructura de este proyecto es:

```text
API_similaridad_inmuebles_CuauhtemocCDMX/
├── appFastAPI/
│   ├── app.py                     # Lógica principal de la API
│   ├── model.py                   # Funciones de procesamiento usadas en producción
│   ├── requirements.txt           # Dependencias específicas de la API
│
├── notebooks/
│   └── model_develop_cuahutemoc_properties.ipynb            # Notebook de análisis
│
├── output/
│   ├── app/
│   │   └── static/
│   │       └── app/
│   │           ├── mapa_propiedades_production.csv          # Propiedades similares identificadas (tabla) en API
│   │           └── mapa_propiedades_production.html         # Propiedades similares identificadas (mapa) en API
│   └── notebooks/
│       └── mapa_propiedades/      # Visualizaciones generadas desde notebooks
│
├── data/
│   └── cuahutemoc_properties.csv  # Dataset original
│
├── Respuestas_a_Desarrollo_de_Solucion.docx  # Respuestas solicitadas en el reto
├── Reto_de_Data_Science.docx                 # Intrucciones de reto
├── requirements.txt                          # Dependencias generales del proyecto
└── README.md
```

________________________________________
**Ejecución de Solución**

**Análisis**:
1. Abrir una terminal de Anaconda Prompt e ir a la carpeta donde descargaste este proyecto:
   cd your_local_root\reto-tecnico
2. Crear y activar el entorno virtual
   conda create -n api_inmuebles_cuauhtemoc_env python=3.11.7 -y
   conda activate api_inmuebles_cuauhtemoc_env
3. Instalar dependencias
   pip install -r requirements.txt
4. Navegar a your_local_root\reto-tecnico\notebooks y abrir el archivo model_develop_cuahutemoc_properties.ipynb en un su IDE prefererido, por ejemplo VSCode.
5. Ejecutar el script, indicando adecuadamente el environment previamente creado.


**API**:
1. Abrir una terminal de Anaconda Prompt e ir a la carpeta donde descargaste este proyecto:
   cd your_local_root\reto-tecnico
2. Crear y activar el entorno virtual
   conda create -n api_inmuebles_cuauhtemoc_env python=3.11.7 -y
   conda activate api_inmuebles_cuauhtemoc_env
3. Instalar dependencias
   pip install -r requirements.txt
4. Ejecutar el servidor FastAPI
   uvicorn appFastAPI.app:app --reload
5. Abrir la documentación interactiva (Ver el link en la terminal de Anaconda Prompt) en un navegador web
   Ejemplo: http://127.0.0.1:8000/docs
6. Colocar 7 carácteristicas de un inmueble en la API app, del cual desee encontrar similares a ella en la alcaldía Cuauhtemoc, CDMX. Las 7 carácteristicas son:
   ```text
   precio: float               # Valor en pesos mexicanos (MXN)
   recamaras: int              # Número de recamaras en el inmueble
   baños: int                  # Número de baños en el inmueble
   año_construccion: float     # Año de construcción del inmueble
   latitude: float             # Dentro de los límites de la alcaldía Cuauhtemoc, CDMX
   longitude: float            # Dentro de los límites de la alcaldía Cuauhtemoc, CDMX
   estado_conservacion: float  # Valor entre 0 y 1 donde 0 es pésimo y 1 excelente
   ```
8. Como salida verá una lista de las carácteristicas más similares a la dada. Adicionalmente, podra ver el link a un mapa que visualiza estas.

**Interpretación de solución para negocio**:

La solución tiene potencial para resolver múltiples necesidades del negocio, incluyendo la automatización de valuaciones, la optimización de estrategias de precio, el soporte analítico para asesores comerciales, la auditoría y estandarización del uso de comparables, y el fortalecimiento de modelos de riesgo mediante información más confiable y homogénea.
