# Análisis Comparativo de la Incertidumbre: Inferencia Bayesiana vs Frecuentista (README Español/Inglés)

Este proyecto explora las diferencias entre los enfoques bayesiano y frecuentista para analizar datos de pruebas A/B (A/B Testing). Utiliza tasas de conversión simuladas para ilustrar cómo se pueden estimar probabilidades, comparar intervalos y tomar decisiones bajo incertidumbre.

**Nota:** Aunque esta sección del README está redactada en español, el código y los comentarios del notebook están completamente en inglés. Esto se hizo intencionalmente como recurso de práctica para entornos profesionales o bilingües.

## Estructura del Proyecto

```
bayes_vs_frequentist_ab_test/
├── data/
│   └── conversions.csv
├── notebooks/
│   └── Bayesian.ipynb
├── figures/
│   └── credible_vs_confidence.png
├── README.md
└── requirements.txt
```

## Conceptos Clave

- **Inferencia Frecuentista**: prueba z para proporciones, intervalos de confianza
- **Inferencia Bayesiana**: priors Beta, posterior mediante PyMC, HDIs
- **Teoría de Decisión**: cálculo de utilidad esperada con distribuciones posteriores

---

# Comparative Analysis of Uncertainty: Bayesian vs. Frequentist Inference (README Spanish/English)

This project compares frequentist and Bayesian approaches to A/B testing using simulated conversion data.

The notebook walks through:

- Estimation of success probabilities
- Confidence intervals (frequentist) vs. credible intervals (Bayesian)
- Hypothesis testing vs. posterior probability comparison
- Decision-making using expected utility theory

## Tools Used

- Python: pandas, numpy, matplotlib, seaborn
- `statsmodels` for classical inference
- `PyMC` and `ArviZ` for Bayesian modeling
- Jupyter Notebook

## How to Run

1. Install dependencies:
    ```
    pip install -r requirements.txt
    ```

2. Open the notebook:
    ```
    notebooks/Bayesian_Final_English_Clean.ipynb
    ```

3. Run all cells to reproduce the full analysis.

## Author

Andrés González Ortega  
Actuarial Science | Statistics | Financial Modeling  
This project is part of a bilingual portfolio demonstrating modern approaches to uncertainty.
