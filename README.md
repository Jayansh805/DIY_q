### **Portfolio Optimization using the Markowitz Model**

#### **1. Objective**

To find the optimal allocation of assets in a portfolio that maximizes expected return for a given level of risk using Markowitz's Modern Portfolio Theory (MPT).

---

#### **2. Data Sources**

* **Yahoo Finance (via `yfinance` library)**: Historical daily price data for selected stocks:

  * AAPL, WMT, NVDA, TM, JPM, AVGO, TSLA, ASML
* **Date Range**: April 1, 2019 – March 31, 2022
* **Data used**: Adjusted Close Prices

---

#### **3. Mathematical & Statistical Methods**

**a. Daily Returns Calculation**

* Formula:

  $$
  r_t = \frac{P_t - P_{t-1}}{P_{t-1}}
  $$

  where $r_t$ is the return on day $t$ and $P_t$ is the adjusted closing price.

**b. Mean Returns & Covariance Matrix**

* Mean Return: Average of daily returns for each asset.
* Covariance Matrix: Measures co-movement of asset returns, essential for risk calculation.

**c. Portfolio Performance**

* Expected Annual Return:

  $$
  E(R_p) = \sum w_i \cdot \mu_i \times 252
  $$
* Portfolio Risk (Standard Deviation):

  $$
  \sigma_p = \sqrt{w^T \Sigma w} \times \sqrt{252}
  $$

  where:

  * $w$ = asset weights,
  * $\mu$ = mean returns,
  * $\Sigma$ = covariance matrix

**d. Optimization Problem**

* Objective: Minimize portfolio risk for a target return.
* Constraints:

  * Sum of weights = 1 (fully invested portfolio)
  * No short selling (weights ≥ 0)

**e. Sharpe Ratio Optimization**

* Sharpe Ratio:

  $$
  S = \frac{E(R_p) - R_f}{\sigma_p}
  $$

  (Assuming risk-free rate $R_f = 0$ in the notebook)

---

#### **4. Code Implementation Highlights**

* **Libraries Used**: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy.optimize`, `yfinance`
* **Portfolio Optimization**:

  * Defined functions to compute portfolio performance (returns, risk).
  * Used `scipy.optimize.minimize()` for constrained optimization.
* **Efficient Frontier**:

  * Simulated thousands of random portfolios to visualize risk-return profiles.
  * Plotted the efficient frontier using `matplotlib`.

---

#### **5. Results Visualization**

* Efficient Frontier plot with Sharpe-optimal portfolio highlighted.
* Allocation of optimal weights displayed using a bar chart.

---
