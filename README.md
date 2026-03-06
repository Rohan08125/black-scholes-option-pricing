# Black-Scholes Option Pricing

This project implements the Black–Scholes model to price European call options using real market data.
It also compares the analytical Black–Scholes price with a Monte Carlo simulation approach and computes key option sensitivities (Greeks).

---

## Features

* Download stock market data using yfinance
* Calculate daily returns
* Estimate annualized volatility
* Implement the Black–Scholes option pricing formula
* Monte Carlo simulation for option pricing
* Compare analytical vs simulation pricing
* Visualize option price sensitivity to volatility
* Compute option Greeks (Delta, Gamma, Vega)

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* SciPy
* yfinance

---

## Model

This project prices European call options using two approaches:

1. Black–Scholes analytical model
2. Monte Carlo simulation

---

### Black–Scholes Model

The Black–Scholes formula for a European call option is:

C = S N(d₁) − K e^{-rT} N(d₂)

where

d₁ = [ln(S/K) + (r + σ²/2)T] / (σ√T)

d₂ = d₁ − σ√T

Parameters:

S : Current stock price

K : Strike price

r : Risk-free interest rate

T : Time to maturity (years)

σ : Volatility of the underlying asset


N(.) represents the cumulative distribution function of the standard normal distribution.

---

### Monte Carlo Simulation

The Monte Carlo method simulates possible future stock prices using the geometric Brownian motion model:

S_T = S_0 exp((r − σ²/2)T + σ√T Z)

where Z is a standard normal random variable.

The option price is estimated as the discounted expected payoff:

C = e^{-rT} E[max(S_T − K, 0)]

As the number of simulations increases, the Monte Carlo estimate converges to the analytical Black–Scholes price.

---

### Option Greeks

The project also computes key option sensitivities (Greeks), which measure how the option price reacts to changes in market variables.

Delta

Δ = N(d₁)

Measures the sensitivity of the option price to changes in the underlying stock price.

Gamma

Γ = N'(d₁) / (S σ √T)

Measures the rate of change of Delta with respect to the stock price.

Vega

Vega = S N'(d₁) √T

Measures the sensitivity of the option price to changes in volatility.

---

## Results

Example output from the model:

Black–Scholes Price ≈ 15.28
Monte Carlo Price ≈ 15.30

The Monte Carlo simulation converges to the analytical Black–Scholes price as the number of simulations increases.


---

