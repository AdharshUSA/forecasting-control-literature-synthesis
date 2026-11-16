# Modern Forecasting and Control: A Four-Paper Synthesis

Course project for **IE 579: Design and Control of Production and Manufacturing Systems**, Purdue University. Team of three. A literature review and synthesis: the methods and results below belong to the original authors, and the contribution here is the comparison and the combined architecture.

## Problem

Classical forecasting such as ARIMA and simple exponential smoothing assumes linear, stable systems and treats variance as noise. Real production systems are nonlinear and stochastic. The mismatch shows up as the bullwhip effect, unplanned downtime and wasted capital and energy. Planning models also tend to assume known demand, deterministic returns and exact inventory counts, while real data is noisy and incomplete.

## Approach

We compared four recent papers and combined them into one architecture:

| Layer | Paper | Role |
|---|---|---|
| Forecast the future | Kück and Freitag (2021), *International Journal of Production Economics* 231 | Local k-nearest-neighbor models from nonlinear dynamics for stochastic customer demand |
| Boost accuracy | Rosienkiewicz (2021), *Eksploatacja i Niezawodnosc* 23(2) | AI-hybrid forecasting models for manufacturing when data is scarce |
| Estimate the present | Polotski (2022), *IFAC-PapersOnLine* 55(10) | Kalman filter that recovers true inventory and return rate from noisy data |
| Deploy at scale | Wölfle et al. (2024), *Data-Centric Engineering* | Energy Service Generics framework: forecasting and optimization code delivered as services |

Background reading: Fatima and Rahimi (2024), a review of time-series forecasting algorithms for industrial manufacturing (*Machines* 12, 380), which covers ARIMA and exponential smoothing, SVM and ANN models, hybrid models and GANs.

## What the papers report

- **Rosienkiewicz (2021):** proposes four hybrid models (econometric, ANN, SVM and extreme learning machine). Because explanatory variables are often unavailable, the inputs are the forecasts of nine traditional methods. Tested on three real cases: production planning, maintenance and quality control. In production planning the hybrid models reached a coefficient of determination above 77% on all five products, and the hybrid ANN was the most accurate on three of the five.
- **Polotski (2022):** a failure-prone manufacturing and remanufacturing system with uncertain returns, controlled by a policy that uses Kalman-filter estimates ("estimation in the loop"). Against a policy based on the long-term average return rate, the paper reports cost savings of about 2.5% over a season, about 2% at high return rates and up to 7% when returns are low. This is a simulation study.
- **Wölfle et al. (2024):** the contribution is a software framework, not a new model. It turns existing forecasting or optimization code into services, and the paper argues that this makes energy management systems economically viable at scale. The paper's own title uses "Forecasting and Optimization as a Service"; we shorten it to FaaS.

We tied each paper to course concepts: EOQ and MTO/MTS inventory models, learning models, cyber-physical systems and stochasticity.

## Illustrative example

A smartphone maker estimates true refurbished inventory with a Kalman filter (9,745 units), forecasts new-phone demand with k-NN (53,500 units), predicts a line failure with an AI hybrid, and delivers all three to managers through a FaaS platform. The numbers in the example are illustrative, not from a built system.

## Conclusions and future work

1. Systems need to estimate the present and forecast the future.
2. Hybrid models perform better in complex, real-world settings.
3. FaaS makes advanced models practical to deploy.

Future work: integrate the models on one platform for head-to-head tests, add explainable AI to the neural models, and extend k-NN to multivariate inputs such as marketing spend and competitor pricing.

## Team

Gabriel Pacheco, Adharsh Rajasekar, Yiyang Lu
