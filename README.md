# 4. Capítulo 4: Resultado

## 4.1. Definición del problema ✓ completo

- **Variable target definida:** PM (matrícula efectiva)
- **Tipo de problema:** clasificación binaria supervisada
- **Métrica objetivo:** F1-Score / PR-AUC (accuracy descartado)
- **Contexto de negocio:** desbalance 1:50 documentado

## 4.2. Recolección y carga de datos ✓ completo

- **Dataset cargado:** 11,679,400 registros × 24 variables
- **Encoding:** cp1252, fechas parseadas
- **Persistencia:** guardado en formato Parquet limpio

## 4.3. Análisis exploratorio de datos (EDA) ✓ completo

- **4.3.1 Descripción del dataset final:** resumen de columnas, tipos y tamaño final del dataset.
- **4.3.2 Calidad de datos:** detección y conteo de `NaN`, "SIN DATO", y ceros encubiertos; plan de imputación/documentación.
- **4.3.3 Distribución univariada de variables clave:** histogramas, boxplots y resumen estadístico para variables numéricas y frecuencias para categóricas.
- **4.3.4 Desbalance del target:** ratio 1:50 documentado; baseline naive y su performance demostrada.
- **4.3.5 Análisis bivariado:** `FUENTE_ORIGEN` discrimina ~32× — evidencia de fuerte variable predictora.
- **4.3.6 Análisis temporal:** estacionalidad semestral confirmada; series temporales y decomposición realizadas.
- **4.3.7 Duplicados y consistencia:** 13,473 registros eliminados; `FACULTAD` recuperada al 99.9% tras limpieza.
- **Plan de variables:** 23 variables evaluadas para modelado (candidatas, transformaciones y codificaciones propuestas).

## 4.4. Ingeniería de features — en curso

- **4.4.1 Descarte de variables:** 9 columnas eliminadas (criterios: varianza baja, colinealidad, irrelevancia de negocio).
- **4.4.2 Derivación desde fechas:** mes, semestre, `fue_valorado`, `dias_a_valoracion`.
- **4.4.3 Tratamiento de missings:** imputación (media/moda/valor constante) o bandera indicadora de ausencia.
- **4.4.4 Encoding de variables categóricas:** one-hot encoding, label encoding según naturaleza de la variable.
- **4.4.5 Dataset final para modelado:** ~16 features seleccionadas; matriz lista para train/test.

## 4.5. Selección y entrenamiento de modelos — pendiente

- **Split train / validation / test:** estratificado por target para preservar desbalance.
- **Baseline:** Regresión Logística (puntuación de referencia).
- **Modelos candidatos:** Random Forest, XGBoost, LightGBM.
- **Tratamiento del desbalance:** `class_weight`, SMOTE, threshold tuning.

## 4.6. Evaluación y selección del modelo final — pendiente

- **Comparación por F1-Score y PR-AUC:** métricas clave de evaluación.
- **Curvas Precision-Recall y ROC:** visualización de performance.
- **Feature importance:** decisión final sobre `GENERO` y otras variables controvertidas.
- **Optimización de umbral de decisión:** ajuste del threshold para maximizar F1 / PR-AUC.
- **Matriz de confusión final:** TN, FP, FN, TP; análisis de errores.

## 4.7. Interpretación y conclusiones — pendiente

- **SHAP values:** explicabilidad local y global del modelo.
- **Perfiles de riesgo de no matrícula:** segmentación y caracterización de estudiantes en riesgo.
- **Recomendaciones para el área comercial:** acciones y estrategias recomendadas.
- **Limitaciones y trabajo futuro:** alcance del modelo, supuestos, y líneas de investigación abiertas.

---

(Generado automáticamente desde demo2.ipynb)
