# Master's Thesis: Forecasting Armed Conflict with Recurrent Neural Networks

**Work in progress.** Master's thesis at the University of Konstanz, expected end date June 2026.

## Research questions

Does adding theory-informed political event data (ICEWS) improve monthly forecasts of armed conflict fatalities beyond a purely autoregressive baseline, and which theoretical streams (bargaining, mass mobilization, escalation) contribute most?
Can Reccurent Neural Networks compete with the established VIEWS benchmark?

## Setup

- **Target**: state-based conflict fatalities from UCDP GED, monthly, log-transformed. H
- **Panel**: 61 countries (Africa and Middle East), January 2001 onward, 17k+ observations.
- **Features**: lagged target plus seven ICEWS event-count covariates grouped into three theory-informed blocks (bargaining, mass mobilization, escalation).
- **Models**: pooled LSTM and GRU with learned country embeddings, 6-month multi-step forecast horizon.
- **Experimental design**: 8 feature-block combinations × 2 architectures = 16 models, hyperparameters tuned once per architecture on the full-feature configuration and then frozen across all blocks.
- **Evaluation**: RMSE (conflict active & panel) and MAE in log space against the VIEWS fatalities benchmark on a Jan–Jun 2023 test window, plus per-country maps and SHAP analysis on the best performing countries.

