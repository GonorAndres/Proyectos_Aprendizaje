# Probabilistic Forecasting of Financial Time Series

**Descripción en español**  
Este proyecto busca predecir series de tiempo financieras (como rendimientos) usando modelos probabilísticos. Se compararán intervalos clásicos con predicciones posteriores bayesianas y se analizará la utilidad práctica de incorporar incertidumbre explícita.  

**English Description**  
This project applies time series models (frequentist and Bayesian) to forecast financial data. The goal is to compare classical confidence intervals with posterior predictive distributions and emphasize uncertainty-aware forecasting.

## Folder Structure

```
financial_forecasting/
├── data/
├── notebooks/
│   └── forecast_analysis.ipynb
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

- Download and clean financial time series
- Fit baseline model (ARIMA or GARCH)
- Implement Bayesian time series model
- Forecast with uncertainty bands
- Compare classical and Bayesian intervals
