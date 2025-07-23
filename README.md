# 🔍 Análisis de Abandono de Clientes con Machine Learning
![Machine Learning](https://image.lexica.art/full_webp/5456ffbd-a76d-47b2-b3a8-60041eeb9795)
Un proyecto completo de análisis predictivo para identificar patrones de abandono de clientes utilizando múltiples algoritmos de machine learning y evaluación comparativa de rendimiento.

## 📊 Descripción del Proyecto

Este proyecto implementa un sistema de análisis predictivo para determinar la probabilidad de abandono (churn) de clientes utilizando técnicas avanzadas de machine learning. El objetivo principal es comparar el rendimiento de diferentes algoritmos para identificar cuál proporciona la mejor precisión predictiva.

## 🎯 Objetivos

- Analizar patrones de comportamiento que indican abandono de clientes
- Implementar múltiples algoritmos de clasificación
- Evaluar y comparar el rendimiento de cada modelo
- Identificar las características más importantes que influyen en el abandono
- Proporcionar insights accionables para la retención de clientes

## 📂 Estructura del Proyecto

```
proyecto-churn-analysis/
├── data/
│   ├── raw/                    # Datos originales
│   ├── processed/              # Datos procesados
│   └── external/               # Datos externos
├── notebooks/
│   ├── 01_exploratory_analysis.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_model_training.ipynb
│   └── 04_model_evaluation.ipynb
├── src/
│   ├── data/                   # Scripts de procesamiento
│   ├── models/                 # Modelos implementados
│   ├── visualization/          # Visualizaciones
│   └── utils/                  # Utilidades
├── models/                     # Modelos entrenados
├── reports/                    # Reportes y análisis
└── requirements.txt
```

## 🛠️ Tecnologías Utilizadas

- **Google Colab**
- **Pandas** - Manipulación de datos
- **NumPy** - Operaciones numéricas
- **Scikit-learn** - Algoritmos de ML
- **XGBoost** - Gradient boosting
- **LightGBM** - Gradient boosting ligero
- **Matplotlib/Seaborn** - Visualización
- **Plotly** - Visualizaciones interactivas

## 🤖 Algoritmos Implementados

### Algoritmos de Clasificación
                        
LightGBM                
Gradient Boosting       
Logistic Regression     
XGBoost                 
Random Forest          
K-Nearest Neighbors    
Support Vector Machine  
Decision Tree

## 📈 Métricas de Evaluación

- **Accuracy** - Precisión general
- **Precision** - Precisión por clase
- **Recall** - Sensibilidad
- **F1-Score** - Media armónica de precision y recall
- **ROC-AUC** - Área bajo la curva ROC
- **Precision-Recall AUC** - Área bajo la curva PR
- **Matriz de Confusión** - Análisis detallado de predicciones

## 🚀 Instalación y Uso

### Prerrequisitos
```bash
git clone https://github.com/tu-usuario/churn-analysis-ml.git
cd churn-analysis-ml
```

### Instalación de dependencias
```bash
pip install -r requirements.txt
```

### Ejecución del análisis
```bash
# Ejecutar análisis exploratorio
jupyter notebook notebooks/01_exploratory_analysis.ipynb

# Procesar datos
python src/data/preprocess_data.py

# Entrenar modelos
python src/models/train_models.py

# Evaluar modelos
python src/models/evaluate_models.py
```

## 📊 Resultados Principales

### Comparación de Modelos
---
## Comparación de Modelos

A continuación, se presenta una tabla comparativa de los resultados de diferentes modelos:

| Modelo                  | Accuracy | Precision | Recall   | F1-Score | ROC AUC  | Training Time |
| :---------------------- | :------- | :-------- | :------- | :------- | :------- | :------------ |
| **LightGBM** | 0.814009 | 0.679487  | 0.566845 | 0.618076 | 0.852304 | 0.190744      |
| **Gradient Boosting** | 0.811642 | 0.670860  | 0.570410 | 0.616570 | 0.856820 | 1.090859      |
| **Logistic Regression** | 0.804070 | 0.647887  | 0.573975 | 0.608696 | 0.848263 | 0.029151      |
| **XGBoost** | 0.794605 | 0.631470  | 0.543672 | 0.584291 | 0.832934 | 0.199656      |
| **Random Forest** | 0.781827 | 0.600402  | 0.532977 | 0.564684 | 0.814406 | 1.505419      |
| **K-Nearest Neighbors** | 0.770469 | 0.572519  | 0.534759 | 0.552995 | 0.782056 | 0.201206      |
| **Support Vector Machine** | 0.792712 | 0.669421 | 0.433155 | 0.525974 | 0.806785 | 5.421773      |
| **Decision Tree** | 0.731661 | 0.494755  | 0.504456 | 0.499559 | 0.662563 | 0.035676      |

---

## 🔧 Preprocesamiento de Datos

- **Limpieza**: Manejo de valores faltantes y outliers
- **Encoding**: Codificación de variables categóricas
- **Scaling**: Normalización de variables numéricas
- **Feature Engineering**: Creación de nuevas características
- **Balanceo**: Técnicas SMOTE para clases desbalanceadas

## 📝 Insights y Recomendaciones
---
### Correlaciones negativas fuertes (factores protectores):

1.  **Tipo_contrato**: -0.397 (La más fuerte - contratos largos protegen del abandono)
2.  **Antigüedad_meses**: -0.352 (Clientes antiguos cancelan menos)
3.  **Seguridad_en_línea**: -0.289 (Tener seguridad reduce abandono)
4.  **Soporte_técnico**: -0.282 (Soporte técnico es protector)
5.  **Cargo_total**: -0.199 (Sorprendentemente, mayor cargo total = menos cancelación)

---
### Correlaciones positivas (factores de riesgo):

1.  **Cargo_mensual**: 0.193 (Cargos mensuales altos aumentan abandono)
2.  **Cuentas_Diarias**: 0.193 (Igual valor que cargo mensual)
3.  **Factura_sin_papel**: 0.192 (Facturación digital se asocia con más abandono)
4.  **Tiene_dependientes**: -0.164 (Tener dependientes es protector)
5.  **Adulto_mayor**: 0.151 (Adultos mayores tienden a cancelar más)

---
### Insights importantes:

1.  Los **contratos a largo plazo** son el factor protector más fuerte.
2.  Existe una **paradoja del cargo**: un mayor cargo total (acumulativo) resulta en menos abandono, pero un mayor cargo mensual se asocia con más abandono.
3.  Los **servicios adicionales** (como seguridad y soporte) actúan como "pegamento" para retener clientes.
4.  La **antigüedad es clave**: cuanto más tiempo lleva un cliente, menos probable es que cancele.

## 🤝 Contribuciones  

Las contribuciones son bienvenidas. Por favor:  

1. Fork el proyecto  
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE.md](LICENSE.md) para más detalles.

## 👥 Autores

- **Angel Troncoso** - *Desarrollo inicial* - [tu-github](https://github.com/AngelTroncoso)

## 🙏 Agradecimientos

- Dataset proporcionado por [Alura Latam]
- Comunidad de Kaggle por los insights
- Contribuidores de las librerías open source utilizadas

## 📞 Contacto

- Email: angeltroncoso2019@outlook.es
- LinkedIn: [Angel Troncoso](https://www.linkedin.com/in/angeltroncoso/)
- Twitter: [Angel Troncoso](https://x.com/AngelTronc26452)

---

⭐ **¡Dale una estrella al proyecto si te pareció útil!**
