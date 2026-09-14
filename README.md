# ⚡💧 Consumo de Energía y Agua de Modelos de IA (2025)

Análisis del consumo energético e hídrico de modelos de Inteligencia Artificial generativa usando el benchmark público ML.ENERGY Benchmark v3 de la Universidad de Michigan.

---

## 📌 Pregunta de Investigación

**Principal:**

¿Cuántos kilovatios hora (kWh) de energía eléctrica y litros (L) de agua consumieron los modelos de IA analizados durante 2025?

**Preguntas de apoyo:**

1. ¿Cómo varía el consumo entre las GPUs NVIDIA H100 y B200?
2. ¿Qué tareas de benchmark presentan el mayor consumo energético?
3. ¿Cuáles son los 10 modelos con mayor consumo total de energía?

---

## 📊 Fuente de Datos

ML.ENERGY Benchmark v3 — Proyecto de investigación de código abierto de la Universidad de Michigan.

| Característica | Detalle |
| :--- | :--- |
| Repositorio | ml-energy/benchmark-v3 (Hugging Face) |
| Total de corridas | 838 |
| Modelos analizados | 34 |
| GPUs | NVIDIA H100 y B200 |
| Tareas de benchmark | gpqa, lm-arena-chat, image-chat, sourcegraph-fim, video-chat |
| Acceso | Librería oficial mlenergy-data (Python) |

Nota sobre el agua: El consumo de agua NO viene medido directamente en el dataset. Se estima aplicando el factor WUE (Water Usage Effectiveness) de Google Cloud: 1.08 litros de agua por cada kWh consumido.

---

## 📁 Estructura del Repositorio

dataxperience_proyectog7/

├── README.md                       # Este archivo

├── ProyectoFinal_G7.ipynb          # Cuaderno con todo el código y análisis

├── Informe_Final.pdf               # Informe escrito del proyecto

└── Presentacion.pdf                # Diapositivas de la sustentación

---

## 🚀 Cómo Ejecutar el Código

### Requisitos previos

- Cuenta en Google Colab o Python 3.10+ instalado.
- Token de Hugging Face (el dataset es gated).
- Librerías: mlenergy-data, pandas, matplotlib, seaborn, scikit-learn.

### Pasos

1. Abre el notebook en Google Colab o Jupyter.
2. Instala las dependencias (primera celda del notebook):
   !pip install mlenergy-data pandas pyarrow matplotlib seaborn scikit-learn
3. Configura tu token de Hugging Face como variable de entorno:
   import os
   os.environ["HF_TOKEN"] = "tu_token_aqui"
4. Ejecuta todas las celdas en orden (Entorno de ejecución → Ejecutar todas).

### Cómo obtener un token de Hugging Face

1. Crea una cuenta en huggingface.co
2. Acepta los términos del dataset en su página oficial.
3. Ve a Settings → Access Tokens y genera uno.
4. Cópialo en la celda correspondiente del notebook.

---

## 🔍 Metodología

El análisis sigue estas etapas:

1. Carga de datos desde Hugging Face con mlenergy-data.
2. Limpieza y conversión:
   - Conversión de julios a kWh: kWh = julios / 3,600,000.
   - Estimación de agua: litros = kWh × 1.08.
3. Análisis Exploratorio (EDA):
   - Consumo total por GPU.
   - Consumo por tarea de benchmark.
   - Top 10 modelos más consumidores.
   - Distribución de energía por prompt.
   - Velocidad vs. energía por token.
4. Análisis Estadístico:
   - Matriz de correlación entre variables.
   - Comparación por GPU (principio del Cuarteto de Anscombe).
5. Machine Learning:
   - Comparación de 5 modelos de clasificación.
   - Predicción del tipo de GPU (H100 vs B200).
   - Clustering (K-Means) y PCA.

---

## 📈 Resultados Principales

| Métrica | Valor |
| :--- | :--- |
| Energía total consumida | 266.56 kWh |
| Agua total estimada | 287.88 litros |
| Total de corridas | 838 |
| GPU con mayor consumo | B200 (164.35 kWh, 60.8% más que H100) |
| Tarea más consumidora | gpqa (107.64 kWh, 40.4% del total) |
| Modelo de mayor consumo | Qwen 3 235B A22B Thinking FP8 (39.06 kWh) |

### Hallazgos del Machine Learning

- Se compararon 5 modelos de clasificación (Regresión Logística, SVM, KNN, Árbol de Decisión, Random Forest).
- Mejor modelo: Árbol de Decisión.
- Accuracy: 58.5% en validación cruzada, 67% en prueba.
- ROC-AUC: 0.688.
- Conclusión: El consumo energético por sí solo no es suficiente para predecir con alta precisión el tipo de GPU.

---

## 🧰 Tecnologías Utilizadas

- Python 3.13
- pandas — Manipulación de datos
- numpy — Cálculos numéricos
- matplotlib / seaborn — Visualización
- scikit-learn — Machine Learning
- mlenergy-data — Acceso al dataset
- Google Colab — Entorno de ejecución

---

## 👥 Autores

| Nombre |
| :--- |
| Samuel Alvarado Currea |
| Natalia Castiblanco |
| Ángel Velásquez |
| Sofia Lorena Pinzon Suarez |

Curso: Data Experience

Facultad: Ingeniería

Año: 2026

---

## 📄 Licencia

Este proyecto es de uso académico. Los datos pertenecen al proyecto ML.ENERGY de la Universidad de Michigan.

---

## 🙏 Agradecimientos

Al equipo de ML.ENERGY por publicar el benchmark benchmark-v3 de forma abierta y accesible.
