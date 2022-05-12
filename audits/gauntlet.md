---
description: Gauntlet's Market Risk Assessment Summary
---

# Market Risk Assessment

_The summary below has been shared by Watson from_ [_Gauntlet Network in the Aave Governance Forum_](https://governance.aave.com/t/gauntlet-s-market-risk-assessment/3814)_, where you can ask all the questions you may have. The full report is available_ [_here._](https://gauntlet.network/reports/aave)__



At the time of writing, Aave has over $7, $8, $10 billion in TVL. With growth of this scale, mitigating financial and market risks is increasingly important as billions in customer funds are on the line.

Within decentralized finance (DeFi), borrowing protocols have four main risk factors:

1. Security risk
2. Governance risk
3. Oracle risk
4. Market risk

This post will focus on market risk, but we discuss how the Aave protocol addresses each of the other risk factors in our formal report.

## **Defining Market Risks**

There are four primary sources of market risk within the protocol:

1. Extreme downward price movement: Shocks to market prices of collateral that cause the contract to become insolvent due to under-collateralization
2. Asset illiquidity and liquidator inaction: Loss of liquidity in an external market place, leading to a liquidator being disincentivized to liquidate defaulted collateral
3. Cascading liquidations: liquidations lower external market prices which in turn lead to further liquidations (i.e. a deflationary spiral)
4. Slashing of the safety module: Insolvency of the safety module due to extreme events where multiple collateral types concurrently fail to be liquidated

How do we test if the Aave protocol can be resilient to each of these market risks? Simulated stress tests!

## **Simulated Stress Tests**

The main tool that we use to perform simulation-based stress tests on Aave’s Ethereum smart contracts is agent-based simulation (ABS). ABS has been used in a variety of stress test contexts, including to estimating censorship in cryptocurrency protocols, detecting fraudulent trading activity in CFTC exchanges,and stress testing frameworks from the European Central Bank and the Federal Reserve. These simulations, while powerful, can be difficult to make both useful and accurate as model complexity can make it hard to match experimental results. Careful design, tuning, and infrastructure architecture can help avoid these pitfalls and has made ABS invaluable in industries such as algorithmic trading and self-driving car deployment.

Please take a look at our report to learn more about our simulation environment!

Many elements of our simulation are designed to study the aforementioned market risks.

_Extreme downward price movement_\
We use a multi-asset correlated Geometric Brownian motion (GBM) to simulate price trajectories. The two most important aspects of this model are asset volatility and asset correlation. In order to properly simulate market capitulation and extreme price drops, we train models on historical data with various volatility regimes. Below is the price of ETH on Black Thursday with the cumulative liquidation value on the Aave V1 protocol. Both the price path and the delay in liquidations are key inputs to our simulation.

![](https://lh6.googleusercontent.com/Fur6i66BanoyJIsn5p3yqzb58mmum2Vz3jBfCih8Qp\_YUv4jAaB3xxxwKA-mDvt6fv4tw10gGsRe2UhZUVDvtEFgxn\_D4x7kk2-8ezdKZfMBTt3MreHMxG3uzQrEDfUMJq7IqRCu)

With the abundance of cryptoassets available on the Aave protocol, it is important to quantify and understand asset correlation, which can give insight into possible contagion and correlated liquidation and insolvency risk. These are the correlation matrices for Aave V2 in March 2021 (Top) and Aave V1 in January 2021 (bottom).

![](https://lh3.googleusercontent.com/DNFJXbT-p\_QXgGxXLI4aQbWYRGtiRJK9QGF8JTR6rw5NFA93MVuxd6IF637Eozvtz1cnL8jLAiJKs3FNMsCFjeyK3afH9E2Kpri8C3hMyA2XDNQSIGqNGAfX-LCws499mNWtB0PI)

![](https://lh5.googleusercontent.com/\_J-r8QqVMe5MDdbY0uJfC5inXV18r6ExBFKyh8jAcgYU\_T7Zewqe39JoROW6NBdYOj9UcEyfqdKk3gWZn84Z5eXBNApIZlpaR\_Jml\_Pw9vwnHKsm\_hViCDBCBAv3FRPXDENGVQkp)

### _Asset illiquidity and liquidator inaction_

Asset illiquidity can lead to liquidator inaction because the liquidator will need to give up large amounts of profit to trade out of collateral and borrow asset positions. Below is a visualization of optimal liquidator trade sizing with respect to expected slippage in different volatilities and order sizes.

![](https://lh6.googleusercontent.com/N1h-AKld1V7J5oTJktgt63I8m1mFOaxI6E\_4vB6lubJj2hf\_\_HtUzT4641K9ugxRf4UX-chXA5K\_SdPYNp5AY-G8JsSxTVI3Y\_8IvECEbsk9m537scQzhTPWoaYu5teA6TLM6M\_L)

In addition, extreme network congestion will also lead to liquidator inaction. In order to simulate gas congestion and transaction delay, we construct modified and truncated normal distributions from 3 month trailing gas price data. At each time step in the simulation, we sample from the probability distribution to define the liquidator behavior.

As we increase ETH volatility in our simulations, we also increase the mean, standard deviation, and skew of the gas price distribution. Below are the daily gas percentile curves for February 2021 and generated gas curves.

![](https://lh6.googleusercontent.com/hDodGigrkEIwxh\_SbBnEXH8wAw6JjQR08E9vrGi\_-YXKWcIVmTebJytViif2Mb1bk5cjd7dIDiqmC284ErgIw1viN05Teh-WED0TYamWhpk5HI0twF3ZRdFe61D1DhQAAzxgpr8K)

![](https://lh5.googleusercontent.com/kldymP3dm4cIIMnP85rdCBL3CiCBqDlgqyN6OmGX\_gzQf2A8VQlXxPrW6xl7mAYWMzgTvwtFPiqJsBdz7jJagA1qv3yH0CaPR4qGfW04PlG5HlIhuZyBnrnW6hTjXUuqF1UtCYsB)

### _Cascading liquidations_

The deflationary spiral that can occur as a result of large liquidations is reproduced in our simulation by training market impact models. These models are trained on order-book (for centralized exchanges) and AMM (for decentralized exchanges) data. After a trade occurs (i.e. selling of liquidated collateral), we capture the impact that it has in the short-term and long-term.

Two factors that can affect the market impact are asset volatility and the size of the trades. We define the scaled liquidity of an asset as the average daily traded volume of the asset divided by the total collateral on the protocol. This is a snapshot of the market characteristics of each of the assets on Aave V2 in March 2021.

![](https://lh5.googleusercontent.com/Ht8\_T2O9ar1xp\_DqQ6Owbkow1Us5D2UOPjdZ9VgLoglhH\_oxCQHpYGohD8zi73t9KojYOUdM4ki2-PpdBNAn0zj\_HbmCbo4uh40sPKulLC-O2naEHv7jzp65QN3Xg-LiNz8KB247)

### _Slashing of the safety module_

The Aave protocol has a safety module denominated in the native AAVE token which serves as a backstop for protocol insolvency. Yield seeking investors can purchase AAVE, stake (lock) it within an insurance pool, and earn a pro-rata portion of AAVE rewards (currently 550 AAVE per day).\
If an Aave market reaches a state where its liabilities (outstanding liens) are greater than its assets (collateral), then the AAVE safety module covers the shortfall of all markets voted by the community.

Our assumptions for safety module slashing are very conservative: we only consider the staked Aave safety module and do not use the liquidity provided by the 80/20 Balancer pool. In addition, we make the assumption that most centralized liquidity will disappear in a slashing event. In simulation, whenever there is an insolvency on the protocol, we sell Aave into the market and model the impact with only DEX liquidity.

## **Metrics**

We will first define metrics that will help us answer these questions in a quantitative manner.

* Insolvent account: Any account where the total borrow value in USD is larger than the total collateral value in USD.
* Net insolvent value: When looking at a single account, this is the net insolvent value of the account at the end of a simulation run divided by the total collateral value of the account at the beginning of the run. When looking at the entire protocol, this is the sum of the net insolvent value of all accounts divided by the total collateral value of all accounts.
* Net insolvent value percentage: When looking at the entire protocol, this is the sum of the net insolvent value of all accounts divided by the total collateral value of all accounts.
* Asset net insolvent value percentage: This is the sum of net insolvent value divided by the total collateral value pro-rata supply percentage for all accounts that supply a given asset as collateral. Because of the many-to-many nature of collateral and borrowed assets on the Aave protocol, attributing insolvency statistics to specific assets can be convoluted.
* Slashing run percentage: This is the percentage of simulation runs that end with greater than 1% of the total value (in Aave) of the safety module slashed to cover insolvencies and with greater than 10% drop in total value (in USD) of the safety module.

## **Results**

Our baseline results for almost 6000 simulation runs showed that the protocol is resilient based on our metrics (<1% net insolvent value percentage of the entire protocol and <5% net insolvent value percentage of every asset). The graphs below show the percentage of users who will have any insolvency and the net insolvent value percentage of each asset in our initial simulation runs.

![](https://lh4.googleusercontent.com/q-5UlO9KmLQf\_GmG\_NHZmzBMV8Ex9r0YPZapE9dBHogiMQSOcE0JQk5CPPlS2BSftHbME69PGYy9dvsLrogsvEyyq3VYo13r9xFx-a0kRMOPXLfFf3yVrfz-LSp4Yks29Y7W2qnb)

![](https://lh4.googleusercontent.com/kw\_H3YfHr9Ts8ItcvUh4OaM1JRJ\_TA0ihYzEsTJNpuh0NKecf7ehpiX2XqKuezmco8BvBDsPDfjk3yetYXRDGdmr3POoWSk8wXOUyjG1qb5ZMxlyVvkYXzh6Nhk5VHGwp5EX8XaS)

The initial simulation runs also serve to identify which assets’ parameters could have the largest impact on the health of the protocol. We chose YFI to study the impacts of various borrow parameters and liquidation parameters. Below is a graph of YFI asset net insolvent value percentage as a function of correlated asset volatility and loan-to-value ratio. Note that the insolvent value percentage is monotonic in both loan-to-value and volatility scalar, as one intuitively expects.

![](https://lh5.googleusercontent.com/Wv2TU\_Sqau9wRcJDSxI2T526Nsk5fzgdjFeCk-yIRRn90uKAfW3q5YQ4HRr2DfhcSgHjL69qo7FfOSi0hj\_2TXLR8derk5e6G3X7sLl30\_rrm78LSO-r0VW7cUD0MZtSzq7ehZVk)

Next is a graph of YFI asset net insolvent value percentage as a function of correlated asset volatility and liquidation threshold. Note that the choice of liquidation threshold is only important at high enough volatilities: at low volatilities, changes to the threshold do little to change net insolvent value.

![](https://lh5.googleusercontent.com/FUJW9l9xZsRXyFNIPBh95U8kmKkGuvFvSg\_7zIerT2fmKzEr9WygrevetLD2W\_7wrMckfboJkj1kjiGylZDyIHi5bqKm5SJOe6r6NscIBCaMY3wHyVNvWW-\_JoLEI29Y0Ii\_vXvC)

This is a graph of YFI asset net insolvent value percentage as a function of correlated asset volatility and liquidation bonus. Note that this measures the likelihood of correlated cascades (e.g. the y-axis is the volatility of an asset highly correlated to YFI with different liquidity levels). This figure illustrates that correlated assets admit a \`safe region’ in terms of liquidation bonus where net insolvent value stays relatively low. Unlike the previous figure, we see that there is a much stronger dependence on liquidation threshold even at lower volatility scalars.

![](https://lh3.googleusercontent.com/eQVqGfHXTISDW\_k3O6DaLWk9Fq7zI5mS7gtD4C05NPCLP-QIRBhJjR0XlAd6qi72v1XMToWtwK\_EEcGtyNgd0xwHGzzk8vSuSTBeBCVjrAlSZJ31fkJIIWT96ZTuiOdlk6ZdKacu)

This is the total collateralization of the Aave protocol as a function of correlated asset volatility and liquidation bonus. Note that the total collateralization ratio of the system is inversely related to the net insolvency value at high volatility levels when the liquidation bonus is above 115%.

![](https://lh4.googleusercontent.com/\_2BEeozJZ2h1CUN8cYloUisjB7ZwZy9j2\_b8RupgG90fnq0fnf66K\_cPyrVDD5pYESgI9I4qcUoomoersaYn9lj6GDuMqyUKPO0lMFdS1preoe\_x0HIbxGuj2H8tdJzZT1\_rjqGz)

Finally, this is the percentage of simulation runs that ended with significant slashing (>1% Safety Module sold and >10% decrease in USD value). Note that we only observe significant slashing at high liquidation bonus and volatilities and that there is a \`safe region’ of moderately sized liquidation bonuses.

![](https://lh6.googleusercontent.com/xMNVyhLbst7pCWmkNp\_MgLOG3dag4T5E1NkLTlh\_kxZghA-u903Lgt7jkGHcGl9gTzQ0aWkWmi\_A77IaHxM9zp1mXjguCEPmB9KPKD7kdDEjmwCLn\_8x43yMUkbCh3ghO7LPythe)

In section 6.3.1 of the formal report, we give a more mathematical explanation for why the liquidation bonus has this relationship with protocol safety.

## **Conclusions**

In this report we conducted a market-risk assessment of the Aave protocol via agent-based simulations run against the Aave contracts.

We stress-tested the liquidation mechanism under a wide range of market volatility and sizing scenarios to ensure that the protocol can prevent borrowers from becoming under-collateralized in most of these cases.

We also used historical market data from centralized and decentralized cryptocurrency exchanges to ensure that assumptions about volatility and slippage are representative of real-world conditions.

**We found that the protocol can withstand aggressive borrowing parameters even in extreme asset volatility and network congestion situations**. However, variations in the liquidation bonuses of the protocol lead to more drastic and unexpected results, and liquidation bonus should not be the primary tool used to adjust protocol-wide market risk.

We also studied the relationship between borrower behavior as a result of borrowing parameter adjustments to understand the returns of both AAVE holders and lenders on the Aave protocol as a result of parameter changes. As market conditions change,

the optimal parameters and suggestions will need to dynamically shift as well.

Our results suggest that monitoring and adjustment of protocol parameters is crucial for reducing risk to lenders and slashing in the safety module.

The community can expect us to be more active going forward with parameter suggestions and liquidation analysis in the near future!
