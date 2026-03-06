# Black-Scholes Option Pricing

This project implements the Black-Scholes model to price European call options using real market data.

The project also compares the analytical Black-Scholes price with a Monte Carlo simulation approach.

## Features

- Download stock market data using yfinance
- Calculate daily returns
- Estimate annualized volatility
- Implement the Black-Scholes option pricing formula
- Monte Carlo simulation for option pricing
- Compare analytical vs simulation pricing
- Visualize option price sensitivity to volatility
- Compute option Greeks (Delta, Gamma, Vega)

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- SciPy
- yfinance

## Model

The Black-Scholes formula for a European call option:

C = S N(d1) − K e^{-rT} N(d2)

Where:

S = stock price  
K = strike price  
r = risk-free interest rate  
T = time to maturity  
σ = volatility

## Results

Example output from the model:

Black-Scholes Price ≈ 15.28  
Monte Carlo Price ≈ 15.30  

The Monte Carlo simulation converges to the analytical Black-Scholes price as the number of simulations increases.

## Project Structure
