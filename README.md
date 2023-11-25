# QF620

## Part I: Analytical Option Formulae
Consider the following European options:
- Vanilla call/put
- Digital cash-or-nothing call/put
- Digital asset-or-nothing call/put

Derive and implement the following models to value these options in Python:
1. Black-Scholes model
2. Bachelier model
3. Black76 model
4. Displaced-diffusion model

## Part II: Model Calibration
On 1-Dec-2020, the S&P500 (SPX) index value was 3662.45, while the SPDR S&P500 Exchange Traded Fund (SPY) stock price was 366.02. The call and put option prices (bid & offer) over 3 maturities are provided in the spreadsheet:
- SPX options.csv
- SPY options.csv
The discount rate on this day is in the file: zero rates 20201201.csv.

Calibrate the following models to match the option prices:
1. Displaced-diffusion model
2. SABR model (fix β = 0.7)

Plot the fitted implied volatility smile against the market data. Report the model parameters:
1. σ, β
2. α, ρ, ν

Discuss how changing β in the displaced-diffusion model and ρ, ν in the SABR model affect the shape of the implied volatility smile.

## Part III: Static Replication
Suppose on 1-Dec-2020, we need to evaluate an exotic European derivative expiring on 15-Jan-2021 which pays:
1. Payoff function:
   <img width="209" alt="Screenshot 2023-11-25 at 2 11 28 PM" src="https://github.com/shannonwky/qf620/assets/151988516/c151d8b5-8e0c-42c5-a2f6-0a1c3b91d8a3">

2. “Model-free” integrated variance:
   <img width="158" alt="Screenshot 2023-11-25 at 2 12 24 PM" src="https://github.com/shannonwky/qf620/assets/151988516/f3ec8a7e-0cb6-4a2d-89f3-bd84e4d29074">

Determine the price of these 2 derivative contracts if we use:
1. Black-Scholes model (what σ should we use?)
2. Bachelier model (what σ should we use?)
3. Static-replication of European payoff (using the SABR model calibrated in the previous question)

## Part IV: Dynamic Hedging
Suppose S0 = $100, σ = 0.2, r = 5%, T = 1/12 year, i.e. 1 month, and K = $100. Use a Black-Scholes model to simulate the stock price. Suppose we sell this at-the-money call option, and we hedge N times during the life of the call option. Assume there are 21 trading days over the month. The dynamic hedging strategy for an option is:

<img width="454" alt="Screenshot 2023-11-25 at 2 13 39 PM" src="https://github.com/shannonwky/qf620/assets/151988516/04c72dbf-2484-4455-9faf-5b5c87b7d410">

Work out the hedging error of the dynamic delta hedging strategy by comparing the replicated position based on φ and ψ with the final call option payoff at maturity. Use 50,000 paths in your simulation, and plot the histogram of the hedging error for N = 21 and N = 84.

