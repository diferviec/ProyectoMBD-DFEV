# ProyectoMBD-DFEV

## 🎯 Objetivo

Desarrollar un modelo predictivo que permita identificar de forma automática transacciones sospechosas de fraude, mediante el análisis de registros históricos de validación, mejorando así los controles operativos y la eficiencia institucional.

---

## 📚 Contexto

Las tarjetas preferenciales (dirigidas a estudiantes, adultos mayores y personas con discapacidad) han sido utilizadas indebidamente por terceros, generando pérdidas económicas y afectando la equidad del sistema. Actualmente, la detección es manual, reactiva y poco escalable.

---

## 🛠️ Metodología

- **Datos utilizados:** Registros de validaciones de tarjetas de enero a diciembre de 2024.
- **Preprocesamiento:**
  - Limpieza de datos, filtrado de perfiles no preferenciales y registros inválidos.
  - Emparejamiento ENTRY–EXIT con ventana máxima de 20 minutos.
  - Generación de variables: duración, validaciones múltiples, viajes incompletos, etc.
- **Balanceo de clases:** SMOTE + Tomek Links.
- **Modelos entrenados:** `Random Forest` y `XGBoost`.
- **Evaluación:** Métricas centradas en `Recall`, `F1-Score`, y `AUC-ROC`.
- **Ajuste de umbral de decisión:** para priorizar detección de fraudes aún con baja precisión.

---

## 📈 Resultados

- `XGBoost` con umbral 0.01 alcanzó un **Recall de 97%**, detectando casi todos los fraudes con una precisión del 3%.
- Se redujo en **87.5%** la carga de revisión manual (de 6,083 a 761 validaciones en 15 días).
- Se propone este enfoque como sistema de alerta temprana para mejorar el control interno y la eficiencia operativa.

---

## 📂 Estructura del repositorio

├── ProyectoCapstoneDEFV.ipynb # Notebook principal con procesamiento y modelado
├── README.md # Documento explicativo del proyecto

Por motivos de confidencialidad y resguardo institucional, la base de datos utilizada en este proyecto no se encuentra disponible en el repositorio.
Los registros de validación pertenecen al sistema operativo de la Aerovía de Guayaquil y fueron procesados de forma local, cumpliendo con las políticas de uso interno.
No obstante, el código, estructura y metodología están documentados para facilitar su comprensión, replicación con datos propios o adaptación a otros contextos.

---

## 📦 Requisitos e instalación

Este proyecto fue desarrollado en Python 3.10. Para ejecutar el código correctamente, asegúrate de tener instaladas las siguientes librerías:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost
