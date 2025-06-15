# Credit Risk Modeling: Bayesian and Frequentist Logistic Regression

**Descripción en español**  
Este proyecto consiste en construir un modelo de riesgo de crédito usando regresión logística. Se compararán modelos frecuentistas con una versión bayesiana para obtener distribuciones posteriores de los coeficientes e interpretar incertidumbre.  
Se elaborarán resúmenes PDF en español e inglés para un público general, además del informe técnico.

**English Description**  
This project uses logistic regression to predict credit default. A Bayesian model will be used alongside a classical model to compare inference, uncertainty, and posterior predictions.  

## Folder Structure

```
credit_risk_modeling/
├── data/
├── notebooks/
│   ├── credit_logit_analysis.ipynb
├── figures/
├── report/
│   ├── summary_plain_es.pdf
│   ├── summary_plain_en.pdf
│   ├── report_en.pdf
│   └── report_es.pdf
├── README.md
└── requirements.txt
```

## Goals

- Explore and preprocess real credit data
- Fit logistic model (frequentist)
- Fit Bayesian logistic regression
- Compare uncertainty around coefficients
- Evaluate with ROC curves and posterior predictive checks
