# solar-predict-rmse

**Code and data for estimating intra-day and day-ahead solar irradiance forecast RMSE using site-specific solar variability, with associated uncertainty bounds.**  
Based on the paper: *A simple method for quickly estimating solar irradiance forecast errors* (Solar Energy, 2025).

## Overview

This repository contains Python code and datasets to reproduce the results of the paper.  
The method uses a simple linear regression between the standard deviation of hourly changes in the clear-sky index (σ(Δkc)) and the Root Mean Square Error (RMSE) of solar irradiance forecasts.

Two model types are provided:
- **Intra-day models**: Forecast horizons from 1h to 6h (Neural Network–based reference forecasts).
- **Day-ahead model**: 24h forecast horizon (ECMWF-based reference forecasts).

Each model provides:
- A regression equation to estimate RMSE from σ(Δkc)
- The 2.5% and 97.5% quantile bounds (95% uncertainty interval)

## Features

- Estimate RMSE forecast error for a given site before deploying a forecasting system
- Models calibrated on 60 globally distributed ground stations
- Applicable using **only solar variability** (can be computed from ground or satellite GHI data)
- Output includes prediction uncertainty bounds

## Repository Structure
├── data/ # Example datasets for model calibration and verification
├── notebooks/ # Jupyter notebooks for reproducing paper figures
├── README.md # Project description
└── LICENSE # License file

If you use this code or data, please cite:
Lauret, P., David, M., Le Gal La Salle, J., Lorenz, E., Perez, R., Voyant, C. (2025).
A simple method for quickly estimating solar irradiance forecast errors. Solar Energy.
https://doi.org/xxx
