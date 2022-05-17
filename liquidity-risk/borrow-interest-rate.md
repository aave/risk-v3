---
description: Mitigating liquidity risk through the borrow interest rate model
---

# Borrow Interest Rate

Aave’s interest rate strategy is calibrated to manage liquidity risk and optimise utilisation. The borrow interest rates come from the [Utilisation Rate](historical-utilization.md) $$U$$.

$$U$$is an indicator of the availability of capital in the pool. The interest rate model is used to manage liquidity risk through user incentivises to support liquidity:

* When capital is available: low interest rates to encourage borrow.
* When capital is scarce: high interest rates to encourage repayments of debt and additional supply.

To retrieve the interest rate strategy contract on-chain, see [this section of the developer docs](https://docs.aave.com/developers/core-contracts/pool#getreservedata).

## Interest Rate Model

Liquidity risk materialises when utilisation is high, it becomes more problematic as $$U$$ gets closer to 100%. To tailor the model to this constraint, the interest rate curve is split in two parts around an optimal utilisation rate $$U_{optimal}$$. Before  $$U_{optimal}$$the slope is small, after it starts rising sharply.&#x20;

The interest rate$$R_t$$follows the model:

$$if \hspace{1mm} U < U_{optimal}:  \hspace{1cm}  R_t = R_0 + \frac{U_t}{U_{optimal}} R_{slope1}$$  &#x20;

$$if \hspace{1mm} U \geq  U_{optimal}:  \hspace{1cm} R_t = R_0 + R_{slope1} + \frac{U_t-U_{optimal}}{1-U_{optimal}}R_{slope2}$$



In the borrow rate technical implementation, the [calculateCompoundedInterest](https://github.com/aave/aave-v3-core/blob/e46341caf815edc268893f4f9398035f242375d9/contracts/protocol/libraries/math/MathUtils.sol#L51) method relies on an approximation that mostly affects high interest rates. The resulting actual borrow rate is:

&#x20;$$Actual APY = (1+Theoretical APY/secsperyear)^{secsperyear}-1$$

Both the variable and stable interest models, are derived from the formula above from the [Whitepaper](https://github.com/aave/aave-protocol/blob/master/docs/Aave\_Protocol\_Whitepaper\_v1\_0.pdf) with different parameters for each asset.

* When $$U < U_{optimal}$$ the borrow interest rates increase slowly with utilisation
* When $$U \geq  U_{optimal}$$ the borrow interest rates increase sharply with utilisation to above 50% APY if the liquidity is fully utilised.

Variable debt see their rate constantly evolving with utilisation. This means they are not ideal for financial planning.

Hence stable debts, that maintain their interest rate at issuance until the specific rebalancing conditions are met. For rebalancing the stable rate down, the debts stable rate$$S$$needs to be greater than the current stable rate$$S_t$$ plus a delta equal to 20%: $$S \geq S_t + 20\%$$.

For rebalancing the stable rate up, these two conditions need to be met:

1. Utilisation Rate: $$U_t > 95\%$$&#x20;
2. Overall Borrow Rate, the weighted average of all the borrow rates: $$R_O < 25\%$$&#x20;



## Model Parameters

The interest rate parameters have been calibrated per cluster of currencies that share similar risk profiles. First, it's crucial to distinguish assets that are used predominantly as collateral (volatile assets) which need liquidity at all times to enable liquidations. These assets require a low Optimal Utilisation rate typically calibrated around 45%. Secondly, the asset's liquidity on Aave is an important factor as the more liquidity, the more stable the utilisation: interest rates of assets with lower liquidity should be more conservative. For example lower liquidity stablecoins have lower Optimal Utilisation Ratio than those with higher liquidity.&#x20;

It's also key to consider market conditions: how can the asset be used in the current market? Aave's borrowing costs must be aligned with market yield opportunities. Or there would be a rate arbitrage with rational users incentivized to borrow all the liquidity on Aave to take advantage of higher yield opportunities.

When market conditions change, the interest rate parameters can be adapted. These changes must adapt to utilisation on Aave’s market as well as to incentives across DeFi.

With the rise of liquidity mining, Aave also adapted its cost of borrowing by lowering  $$U_{optimal}$$ of the assets affected. This increased the borrow costs that are now partially offset by the liquidity reward.

Following the favorable historical review of liquidity risk, the interest rate models have been optimised to be more competitive while keeping theirs risk mitigation properties.&#x20;

### Variable Interest Rate Model Parameters

| Asset  |  $$U_{optimal}$$ | Base | Slope 1 | Slope 2 |
| ------ | :--------------: | :--: | :-----: | :-----: |
| DAI    |        80%       |  0%  |    4%   |   75%   |
| sUSD   |        90%       |  0%  |    4%   |   60%   |
| USDC   |        90%       |  0%  |    4%   |   60%   |
| USDT   |        90%       |  0%  |    4%   |   60%   |
| EURS   |        90%       |  0%  |    4%   |   60%   |
| JEUR   |        90%       |  0%  |    4%   |   60%   |
| agEUR  |        90%       |  0%  |    4%   |   60%   |
| AAVE   |                  |      |         |         |
| BAL    |        45%       |  0%  |    7%   |   300%  |
| CRV    |        45%       |  0%  |    7%   |   300%  |
| DPI    |        45%       |  0%  |    7%   |   300%  |
| ETH    |        45%       |  0%  |    7%   |   300%  |
| LINK   |        45%       |  0%  |    7%   |   300%  |
| WBTC   |        45%       |  0%  |    7%   |   300%  |
| WMATIC |        45%       |  0%  |    7%   |   300%  |
| WONE   |        45%       |  0%  |    7%   |   300%  |
| WFTM   |        45%       |  0%  |    7%   |   300%  |
| WAVAX  |        45%       |  0%  |    7%   |   300%  |
| GHST   |        45%       |  0%  |    7%   |   300%  |
| SUSHI  |        45%       |  0%  |    7%   |   300%  |

### Stable Interest Rate Model Parameters

The stable rate provides predictability for the borrower which comes at a cost, as the interest rates are higher than the variable rate. However the rate of a stable loan is fixed until the rebalancing conditions are met:

1. Utilisation Rate: $$U_t > 95\%$$&#x20;
2. Overall Borrow Rate, the weighed average of all the borrow rates: $$R_O < 25\%$$&#x20;

The currencies the most exposed to liquidity risk do not offer stable rate borrowing.

The base rate of the stable rate model corresponds to the average market rate of the asset.

| Asset  |  $$U_{optimal}$$ | Base | Slope 1 | Slope 2 |
| ------ | :--------------: | :--: | :-----: | :-----: |
| DAI    |        80%       |  1%  |  0.5%   |   75%   |
| sUSD   |        90%       |  1%  |  0.5%   |   75%   |
| USDC   |        90%       |  1%  |  0.5%   |   75%   |
| USDT   |        90%       |  1%  |  0.5%   |   75%   |
| EURS   |        90%       |  1%  |  0.5%   |   75%   |
| JEUR   |        90%       |  1%  |  0.5%   |   75%   |
| agEUR  |        90%       |  1%  |  0.5%   |   75%   |
| AAVE   |                  |      |         |         |
| BAL    |        45%       |  2%  |    7%   |   300%  |
| CRV    |        45%       |  2%  |    7%   |   300%  |
| DPI    |        45%       |  2%  |    7%   |   300%  |
| ETH    |        45%       |  2%  |    7%   |   300%  |
| LINK   |        45%       |  2%  |    7%   |   300%  |
| WBTC   |        45%       |  2%  |    7%   |   300%  |
| WMATIC |        45%       |  2%  |    7%   |   300%  |
| WONE   |        45%       |  2%  |    7%   |   300%  |
| WFTM   |        45%       |  2%  |    7%   |   300%  |
| WAVAX  |        45%       |  2%  |    7%   |   300%  |
| GHST   |        45%       |  2%  |    7%   |   300%  |
| SUSHI  |        45%       |  2%  |    7%   |   300%  |

## Interest Rate Parameters Change

When market conditions change, risks change. The utilisation of reserves is continuously monitored to check liquidity is available. In case of prolonged full utilisation, the interest rate parameters are adapted to mitigate any risks emerging from market conditions

The borrow interest rates paid are distributed as yield for aToken holders who have supplied to the protocol, excluding a share of yields sent to the ecosystem reserve defined by the reserve factor. This interest rate is generated on the asset that is borrowed out then shared among all the liquidity providers. The supply APY, $$D_t$$, is:

$$S_t = U_t ( SB_t S_t   + VB_t V_t)(1-R_t)$$

* $$U_t$$, the utilisation ratio
* $$SB_t$$, the share of stable borrows
* $$S_t$$, the average stable rate
* $$VB_t$$, the share of variable borrows
* $$V_t$$, the variable rate
* $$R_t$$, the reserve factor

You can view the protocol's deposit APY on the [Aave App](https://app.aave.com/reserve-overview/?underlyingAsset=0xd586e7f844cea2f87f50152665bcbc2c279d8d70&marketName=proto_avalanche_v3) for each asset.

The average Supply APY over a period also includes Flash Loan fees.