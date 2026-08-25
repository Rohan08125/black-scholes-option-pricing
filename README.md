# Black-Scholes Option Pricing with Monte Carlo Simulation

This project prices a European call option on AAPL using the analytical Black-Scholes model and validates the result with a Monte Carlo simulation. Historical volatility is estimated from daily returns, and key option Greeks are computed to study price sensitivity.

---

## Features

* Download AAPL market data using yfinance
* Calculate daily returns and annualized historical volatility
* Implement the Black-Scholes European call pricing formula
* Simulate stock prices using geometric Brownian motion
* Price the option using up to 1,000,000 Monte Carlo paths
* Analyze Monte Carlo convergence and pricing error
* Compute Delta, Gamma, and Vega
* Analyze option-price sensitivity to volatility
* Visualize the simulated terminal stock-price distribution

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* SciPy
* yfinance

---

## Model Assumptions

The project assumes a European call option with:

* No dividends
* Constant volatility
* Constant risk-free interest rate
* Lognormal stock-price dynamics
* Geometric Brownian Motion for Monte Carlo simulation

### Black-Scholes Model

The European call price is:

C = S N(d₁) − K e⁻ʳᵀ N(d₂)

where

d₁ = [ln(S/K) + (r + σ²/2)T] / (σ√T)

d₂ = d₁ − σ√T

### Monte Carlo Simulation

Future stock prices are simulated using:

S_T = S₀ exp((r − σ²/2)T + σ√T Z)

where Z is a standard normal random variable.

The option value is estimated as:

C = e⁻ʳᵀ E[max(S_T − K, 0)]

As the number of simulated paths increases, the Monte Carlo estimate approaches the analytical Black-Scholes value.

---

## Example Setup and Results

Using AAPL data from 2023:

| Parameter | Value |
|---|---:|
| Spot price | $190.55 |
| Strike price | $200.00 |
| Maturity | 1 year |
| Risk-free rate | 5.00% |
| Historical volatility | 19.95% |
| Black-Scholes call price | $15.2845 |
| Monte Carlo price (1M paths) | $15.3006 |
| Absolute pricing gap | $0.0161 |

The 1,000,000-path simulation produces a close approximation to the analytical benchmark. The relative pricing error is approximately 0.105%, illustrating the sampling error inherent in Monte Carlo estimation.

---

## Option Greeks

The model computes:

* **Delta:** 0.5429
* **Gamma:** 0.0104
* **Vega:** 75.5783 per unit change in volatility

These Greeks quantify sensitivity to changes in the underlying stock price and volatility.

---

## Project Structure

```text
black-scholes-option-pricing/
├── black_scholes_option_pricing.ipynb
├── README.md
├── requirements.txt
└── LICENSE
```
