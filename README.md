# Modern Forecasting and Control: A Four-Paper Synthesis

Course project for **IE 579: Design and Control of Production and Manufacturing Systems**, Purdue University. Team of three.

## Problem

Classical forecasting such as ARIMA and simple exponential smoothing assumes linear, stable systems and treats variance as noise. Real production systems are nonlinear and stochastic. The mismatch shows up as the bullwhip effect, unplanned downtime and wasted capital and energy.

## Approach

We reviewed four recent papers and combined them into one architecture:

| Layer | Paper | Role |
|---|---|---|
| Forecast the future | Kück and Freitag (2021) | k-NN models from nonlinear dynamics for chaotic demand |
| Boost accuracy | Rosienkiewicz (2021) | AI-hybrid models for linear and nonlinear patterns with scarce data |
| Estimate the present | Polotski (2022) | Kalman filter to recover true state (e.g., inventory) from noisy data |
| Deploy at scale | Wölfle et al. (2024) | Forecasting as a Service (FaaS) architecture |

We tied each paper to course concepts: EOQ and MTO/MTS inventory models, learning models, cyber-physical systems and stochasticity.

## Illustrative example

A smartphone maker estimates true refurbished inventory (Kalman filter), forecasts new-phone demand (k-NN), predicts a line failure (AI hybrid) and delivers all three to managers through a FaaS platform. The numbers in the example are illustrative, not from a built system.

## Conclusions and future work

1. Systems need to estimate the present and forecast the future.
2. Hybrid models perform better in complex, real-world settings.
3. FaaS makes advanced models practical to deploy.

Future work: integrate the models on one platform for head-to-head tests, add explainable AI to the neural models, and extend k-NN to multivariate inputs such as marketing spend and competitor pricing.

## Team

Gabriel Pacheco, Adharsh Rajasekar, Yiyang Lu
