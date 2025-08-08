# Credit Risk Scorecard with GLM

## 🇺🇸 English Summary

This project develops an **interpretable credit risk scorecard** using a logistic Generalized Linear Model (GLM). Starting from 32,581 consumer loan applications, we perform comprehensive data cleaning, domain-driven feature engineering, and statistical modeling to predict loan default probability. The methodology includes parallel modeling approaches (raw-scale vs. z-scaled), p-value-based variable selection, and **cost-sensitive threshold optimization** using portfolio-derived loss functions. The final model achieves 0.877 ROC-AUC and reduces expected portfolio loss by 27% compared to a standard 0.50 cutoff, while maintaining regulatory interpretability through transparent coefficients.

***

# Scorecard de Riesgo Crediticio con GLM

## 📋 Descripción del Proyecto

Este proyecto desarrolla un **scorecard interpretable de riesgo crediticio** utilizando un Modelo Linear Generalizado (GLM) logístico. El objetivo principal es predecir la probabilidad de incumplimiento de préstamos de consumo y optimizar las decisiones de originación mediante un enfoque basado en costos.

## 🎯 Objetivos

- **Predictivo**: Estimar la probabilidad de default (`loan_status`) de solicitudes de préstamo
- **Económico**: Minimizar pérdidas esperadas mediante optimización de umbral por costos
- **Regulatorio**: Mantener interpretabilidad de coeficientes para auditoría y cumplimiento normativo
- **Operativo**: Proporcionar una herramienta práctica para decisiones de crédito


## 📊 Conjunto de Datos

- **Tamaño**: 32,581 solicitudes de préstamo
- **Tasa de default**: ~22%
- **Variables principales**:
    - **Demográficas**: edad, ingresos, antigüedad laboral
    - **Vivienda**: tipo de tenencia (RENT, OWN, MORTGAGE, OTHER)
    - **Préstamo**: monto, tasa de interés, grado crediticio (A-G), propósito
    - **Historial**: flag de default previo en buró, longitud historial crediticio


### Variables del Dataset

| Variable | Descripción | Tipo |
| :-- | :-- | :-- |
| `person_age` | Edad del solicitante | Numérica |
| `person_income` | Ingresos anuales | Numérica |
| `person_home_ownership` | Tipo de vivienda | Categórica |
| `person_emp_length` | Años de empleo | Numérica |
| `loan_intent` | Propósito del préstamo | Categórica |
| `loan_grade` | Grado crediticio (A-G) | Ordinal |
| `loan_amnt` | Monto del préstamo | Numérica |
| `loan_int_rate` | Tasa de interés | Numérica |
| `loan_status` | Estado del préstamo (0=pagado, 1=default) | **Target** |
| `cb_person_default_on_file` | Historial de default | Binaria |

## 🔧 Metodología

### 1. Preparación de Datos

- **Valores faltantes**: Imputación mediana estratificada por `loan_grade`
- **Outliers**: Winsorización al percentil 99.5
- **Codificación**: Conversión Y/N → 1/0 para variables binarias
- **Duplicados**: Eliminación de registros duplicados


### 2. Ingeniería de Características

- **Codificación ordinal**: `loan_grade` A→G = 1→7
- **Variables dummy**: One-hot encoding para `loan_intent` y `person_home_ownership`
- **Transformaciones**:
    - `dti` = debt-to-income ratio
    - `log_person_income` = log₁₀(ingresos)


### 3. Modelado GLM

- **Selección de variables**: p-valor < 0.05
- **Validación**: Hold-out 80/20 estratificado


### 4. Optimización de Umbral

- **Matriz de costos empírica**:
    - `COST_FN` = mediana monto préstamos en default
    - `COST_FP` = mediana monto buenos × tasa mediana
- **Búsqueda óptima**: Minimización de pérdida esperada total


## 📈 Resultados Principales

### Métricas del Modelo

| Métrica | Valor |
| :-- | :-- |
| **ROC-AUC** | 0.877 |
| **Recall** | 0.68 |
| **Precision** | 0.71 |
| **Specificity** | 0.95 |
| **Accuracy** | 0.864 |

### Impacto Económico

- **Umbral óptimo**: τ* ≈ 0.38
- **Reducción de pérdida**: 27% vs umbral estándar (0.50)
- **Captura de defaults**: 68% de verdaderos incumplimientos


## 📊 Visualizaciones Clave

El notebook incluye:

- Distribuciones de variables numéricas y categóricas
- Análisis de correlaciones
- Curvas ROC y Precision-Recall
- Matriz de confusión optimizada
- Análisis de umbral vs. métricas de negocio


## 💼 Aplicación Práctica

### Recomendaciones de Implementación

1. **Monitoreo mensual** de recall y precision
2. **Recalibración** si recall < 60% o precision < 65%
3. **Validación continua** con nuevos datos

### Próximos Pasos

- Implementar Weight of Evidence (WOE) binning
- Explorar regularización L1/L2
- Benchmark con modelos ensemble (XGBoost, LightGBM)
- Validación cruzada temporal


## 📝 Aspectos Técnicos

### Dependencias Principales

- `pandas`, `numpy`: Manipulación de datos
- `scikit-learn`: Machine learning
- `statsmodels`: Modelado estadístico GLM
- `seaborn`, `matplotlib`: Visualización


### Consideraciones Regulatorias

- Coeficientes interpretables en unidades de negocio
- Documentación completa de transformaciones
- Metodología auditoria para validación de modelos
- Justificación estadística de selección de variables

***

**Nota**: Este proyecto se enfoca en la metodología estadística y aplicación práctica del GLM para riesgo crediticio. Para detalles técnicos completos, consultar el notebook principal.

