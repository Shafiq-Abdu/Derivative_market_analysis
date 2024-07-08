
# Black-Scholes Model

## History

The Black-Scholes Model, developed in 1973 by Fischer Black, Myron Scholes, and Robert Merton, revolutionized the pricing of options contracts and laid the foundation for modern quantitative finance.

- **Origins:** Fischer Black and Myron Scholes collaborated to solve the problem of pricing options contracts, with significant contributions from Robert Merton.
- **Nobel Prize:** Myron Scholes and Robert Merton were awarded the Nobel Prize in Economic Sciences in 1997 for their work on the Black-Scholes model.
- **Impact:** The model enabled fair pricing of derivatives, leading to the growth of options trading and influencing subsequent developments in quantitative finance.

## Formula

The Black-Scholes formula is used to calculate the theoretical price of European-style call and put options on non-dividend paying stocks.

### Call Option Price

$$
C = S_0 N(d_1) - X e^{-rT} N(d_2)
$$

# Black-Scholes PDE Explanation

The Black-Scholes PDE is a fundamental equation in the mathematical finance field used for modeling the price dynamics of financial derivatives, such as options. It is given by:

$$
\frac{\partial V}{\partial t} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 V}{\partial S^2} + r S \frac{\partial V}{\partial S} - r V = 0
$$

where:
- $V = V(S, t)$ is the price of the derivative as a function of the underlying asset price $S$ and time $t$.
- $\sigma$ is the volatility of the underlying asset.
- $r$ is the risk-free interest rate.
- $\frac{\partial V}{\partial t}$ is the partial derivative of $V$ with respect to time.
- $\frac{\partial V}{\partial S}$ is the partial derivative of $V$ with respect to the underlying asset price.
- $\frac{\partial^2 V}{\partial S^2}$ is the second partial derivative of $V$ with respect to the underlying asset price.

## Derivation Outline

1. **Assumptions**:
    - The underlying asset price follows a geometric Brownian motion:
      
$$
  dS = \mu S  dt + \sigma S  dW
$$

   where $\mu$ is the drift rate and $dW$ is a Wiener process.
    - No arbitrage opportunities exist in the market.

2. **Portfolio Construction**:
    - Construct a risk-free portfolio consisting of a long position in the option and a short position in the underlying asset.
    - Let $\Delta$ be the hedge ratio (number of shares of the underlying asset held per option).

3. **Ito's Lemma**:
    - Apply Ito's Lemma to the option price $V(S, t)$:

$$
dV = \left( \frac{\partial V}{\partial t} + \mu S \frac{\partial V}{\partial S} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 V}{\partial S^2} \right) dt + \sigma S \frac{\partial V}{\partial S}  dW
$$


5. **Eliminate Risk**:
    - Choose $\Delta = \frac{\partial V}{\partial S}$ to eliminate the $dW$ term, making the portfolio risk-free.
    - The value of the portfolio $\Pi$ is:

$$
\Pi = V - \Delta S
$$

6. **Portfolio Dynamics**:
    - The change in portfolio value is:

$$
d\Pi = dV - \Delta dS
$$

Substituting $dS$ and $dV$, and using $\Delta = \frac{\partial V}{\partial S}$, we get:

$$
d\Pi = \left( \frac{\partial V}{\partial t} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 V}{\partial S^2} \right) dt
$$

7. **Risk-Free Rate**:
    - Since the portfolio is risk-free, it must earn the risk-free rate $r$:

$$
d\Pi = r \Pi  dt
$$

8. **Equating Portfolio Returns**:
    - Equating the expressions for $d\Pi$ and solving for $\frac{\partial V}{\partial t}$, we obtain the Black-Scholes PDE:
  
# Option Greeks in the Black-Scholes PDE

The Black-Scholes PDE involves several partial derivatives of the option price with respect to various parameters. These derivatives are known as the option Greeks. Here are the key Greeks used in the Black-Scholes PDE:

## Delta ($\Delta$)

Delta ($\Delta$) measures the sensitivity of the option price to changes in the underlying asset price. It is the first partial derivative of the option price with respect to the underlying asset price:

$$
\Delta = \frac{\partial V}{\partial S}
$$

Delta represents the amount by which the option price changes for a one-unit change in the underlying asset price.

## Gamma ($\Gamma$)

Gamma ($\Gamma$) measures the rate of change of Delta with respect to changes in the underlying asset price. It is the second partial derivative of the option price with respect to the underlying asset price:

$$
\Gamma = \frac{\partial^2 V}{\partial S^2}
$$

Gamma represents the convexity of the option price with respect to the underlying asset price.

## Theta ($\Theta$)

Theta ($\Theta$) measures the sensitivity of the option price to the passage of time. It is the partial derivative of the option price with respect to time:

$$
\Theta = \frac{\partial V}{\partial t}
$$

Theta represents the rate at which the option price decreases as the option approaches its expiration date, often referred to as time decay.

## Vega ($\nu$)

Vega ($\nu$) measures the sensitivity of the option price to changes in the volatility of the underlying asset. While Vega is not explicitly in the Black-Scholes PDE, it is related to the volatility term $\sigma$:

$$
\nu = \frac{\partial V}{\partial \sigma}
$$

Vega represents the amount by which the option price changes for a one-unit change in the volatility of the underlying asset.

## Rho ($\rho$)

Rho ($\rho$) measures the sensitivity of the option price to changes in the risk-free interest rate. While Rho is also not explicitly in the Black-Scholes PDE, it is related to the risk-free interest rate $r$:

$$
\rho = \frac{\partial V}{\partial r}
$$

Rho represents the amount by which the option price changes for a one-unit change in the risk-free interest rate.

## Summary in the Black-Scholes PDE

The Black-Scholes PDE combines Delta, Gamma, and Theta in the following form:

$$
\frac{\partial V}{\partial t} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 V}{\partial S^2} + r S \frac{\partial V}{\partial S} - r V = 0
$$

Here, $\frac{\partial V}{\partial t}$ is Theta, $\frac{\partial V}{\partial S}$ is Delta, and $\frac{\partial^2 V}{\partial S^2}$ is Gamma. These Greeks help in understanding how the option price is affected by various factors and are essential for managing the risk associated with options trading.


$$
\frac{\partial V}{\partial t} + \frac{1}{2} \sigma^2 S^2 \frac{\partial^2 V}{\partial S^2} + r S \frac{\partial V}{\partial S} - r V = 0
$$

This PDE is used to determine the price of European call and put options by solving it with appropriate boundary conditions.

