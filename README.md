# Lung ASC overall survival calculator

**Aimin Jiang et al. · Shandong Cancer Hospital**

A browser-based five-factor Cox nomogram for 1-, 3-, and 5-year overall survival in pathologically confirmed lung adenosquamous carcinoma. The development cohort comprised 307 patients treated at Shandong Cancer Hospital in 2009–2026.

## Website

https://jiangaimin1995.github.io/lung-asc-os-calculator/

## Predictors and scores

| Predictor | Category assigned points | Points |
|---|---|---:|
| Age | ≥65 years | 100.000000 |
| Pulmonary metastasis | Yes | 68.385144 |
| Liver metastasis | Yes | 67.468104 |
| Surgical resection | No | 98.938009 |
| Serum albumin | <40 g/L | 72.237066 |

Other categories contribute zero points. Low risk means total points ≤171.175075 (displayed as 171.1751); high risk means points above that original cohort median. Predictions use the original fitted Cox coefficients and baseline survival, not interpolation from the nomogram graphic. Aggregate parameters are available in `model-parameters.json`.

## Use and verification

Select all five clinical factors and choose **Calculate prognosis**. Calculations occur on the user's device. Patient inputs are not uploaded or stored. The single-file `index.html` can also be downloaded and opened offline.

All 307 original point totals and risk groups were verified in R without exporting patient-level data. All 32 possible predictor combinations matched independent R predictions to an absolute survival-probability tolerance of 1e-12.

The calculator is a research tool requiring external validation. Surgical status represents an association in the development model and does not estimate causal treatment benefit. The cohort-median risk group is not an intervention threshold.

## Version and attribution

Initial release: **1.0.0**, 18 October 2026. Original analysis: R 4.4.2, rms 6.9.0, survival 3.7.0.

Hospital emblem source: https://www.sd-cancer.com/ (https://static.sd-cancer.com/images/logo.png). The official emblem is displayed with an English hospital name.

This repository contains aggregate parameters and calculator code only; it does not contain patient-level records.
