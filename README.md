# ml-finanzas

Proyectos de machine learning aplicado a banca: detección de fraude, análisis de anomalías
en carteras de clientes y series temporales de mercado.

Pablo Lamas Pillo — [LinkedIn](https://www.linkedin.com/in/pablo-lamas-pillo-710b75113)

---

## Sobre este repositorio

Cuatro años trabajando en banca comercial y análisis de riesgo me han dado una visión
concreta de dónde se toman las decisiones y con qué información. Estos proyectos son el
resultado de construir la parte técnica desde ese punto de partida: el foco no está solo en
entrenar el modelo, sino en qué decisión de negocio habilita y a qué coste.

Desarrollados en el marco del **Máster en IA Aplicada al Sector Financiero**
(Instituto Europeo de Posgrado).

---

## Proyectos

### 🔍 Detección de fraude

El mismo problema abordado por dos vías complementarias, para comparar qué aporta cada
enfoque cuando la clase positiva es minoritaria y el coste de los errores es asimétrico.

| Notebook | Enfoque | Técnicas |
|---|---|---|
| [`fraude_regresion_logistica.ipynb`](./fraude_regresion_logistica.ipynb) | Supervisado | Regresión logística con ponderación de clases, curva Precision-Recall, análisis de coeficientes |
| [`fraude_no_supervisado.ipynb`](./fraude_no_supervisado.ipynb) | No supervisado | DBSCAN e Isolation Forest, dos configuraciones cada uno, comparación sistemática de métricas |

**Por qué importa el enfoque no supervisado:** en la práctica rara vez se dispone de un
histórico de fraude etiquetado y suficientemente representativo. Entrenar sin la etiqueta y
reservarla solo para evaluar reproduce el escenario real.

**Datos.** Ambos notebooks usan el conjunto *Credit Card Fraud Detection* de la Université
Libre de Bruxelles, disponible en
[Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) (Database Contents
License v1.0): 284.807 transacciones de tarjetas europeas, 492 de ellas fraudulentas
(0,172%), con las variables anonimizadas mediante PCA. Descargando el fichero, ambos
notebooks son reproducibles de principio a fin.

---

### 📊 [Detección de anomalías en cartera de clientes](./analisis_cartera.ipynb)

Identificación de comportamientos atípicos sobre una cartera de 30.000 clientes y 65
variables, sin etiqueta previa. Incluye selección de variables, imputación, comparación
entre DBSCAN e Isolation Forest y un análisis explícito del **trade-off entre falsos
positivos y falsos negativos**: cuántas revisiones manuales cuesta cada punto adicional de
detección.

> Los datos utilizados no se publican en este repositorio.

---

### 📈 [Series temporales de mercado](./analisis_spx_dax.ipynb)

Análisis del comportamiento conjunto de S&P 500 y DAX sobre 6.269 observaciones diarias
(1994–2018), con foco en la crisis financiera de 2008.

---

## Stack

`Python` · `pandas` · `numpy` · `scikit-learn` · `matplotlib` · `seaborn`

Modelos: regresión logística, DBSCAN, Isolation Forest, clustering jerárquico, PCA
Evaluación: matriz de confusión, precision / recall / F1, ROC-AUC, curva Precision-Recall

---

## Nota sobre los datos

Los ficheros de datos no se incluyen en el repositorio, por tamaño en el caso de los
públicos y por confidencialidad en el de la cartera de clientes. Los notebooks conservan el
código y los resultados de su ejecución original.

Los dos proyectos de detección de fraude son **reproducibles**: basta descargar el conjunto
público enlazado más arriba. El de anomalías en cartera no lo es, por lo que se documentan
en el propio notebook las métricas y conclusiones obtenidas.
