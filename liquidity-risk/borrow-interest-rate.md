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

* When $$U < U_{optimal}$$ the borrow interest rates increase slowly with utilisation
* When $$U \geq  U_{optimal}$$ the borrow interest rates increase sharply with utilisation to above 50% APY if the liquidity is fully utilised.

Both the variable and stable interest models, are derived from the formula above from the [Whitepaper](https://github.com/aave/aave-protocol/blob/master/docs/Aave\_Protocol\_Whitepaper\_v1\_0.pdf) with different parameters for each asset.

Variable debt see their rate constantly evolving with utilisation. This means they are not ideal for financial planning.

Hence stable debts, that maintain their interest rate at issuance until the specific rebalancing conditions are met. In V3 interest models are optimised by new rate strategy parameter **Optimal Stable/Total Debt Ratio** to algorithmically manage stable rate.

$$if \hspace{1mm} ratio < ratio_{o}: \hspace{1cm} R_{t} = r_{0} + \frac{ratio - ratio_{o}}{1 - ratio_{o}}R_{base}$$

## Model Parameters

First, it's crucial to distinguish assets that are used predominantly as collateral (volatile assets) which need liquidity at all times to enable liquidations. Secondly, the asset's liquidity on Aave is an important factor as more the liquidity -> more stable the utilisation. Interest rates of assets with lower liquidity should be more conservative.

It's also key to consider market conditions: how can the asset be used in the current market? Aave's borrowing costs must be aligned with market yield opportunities. Or there would be a rate arbitrage with rational users incentivized to borrow all the liquidity on Aave to take advantage of higher yield opportunities.

With the rise of liquidity mining, Aave also adapted its cost of borrowing by lowering  $$U_{optimal}$$ of the assets affected. This increased the borrow costs that are now partially offset by the liquidity reward.

### Variable Interest Rate Model Parameters

Variable rate parameters:
 - $$U_{optimal}$$ 
 - Base Variable Borrow Rate
 - Variable Rate Slope 1
 - Variable Rate Slope 2

### Stable Interest Rate Model Parameters

Stable rate parameters:
 - $$U_{optimal}$$ 
 - Base Variable Borrow Rate
 - Variable Rate Slope 1
 - Variable Rate Slope 2
 - Stable to Total Debt Ratio

The stable rate provides predictability for the borrower which comes at a cost, as the interest rates are higher than the variable rate. However the rate of a stable loan is fixed until the rebalancing conditions are met:

1. Utilisation Rate: $$U_t > 95\%$$&#x20;
2. Overall Borrow Rate, the weighed average of all the borrow rates: $$R_O < 25\%$$&#x20;

{% hint style="info" %}
The assets that are most exposed to liquidity risk do not offer stable rate borrowing.
{% endhint %}

{% hint style="info" %}
The base rate of the stable rate model corresponds to the average market rate of the asset.
{% endhint %}

### V3 Interest rate Parameters
The interest rate parameters for V3 markets have been deployed with 3 interest rate strategies calibrated per cluster of assets that share similar risk profiles. 

## Rate Strategy Volatile One
Volatile assets need liquidity at all times, thus calibrated at low Optimal Utilisation Ratio.

{% hint style="info" %}
 AAVE, BAL, CRV, DPI, GHST, LINK, SUSHI, WAVAX, WBTC, WETH, WFTM, WMATIC, WONE
{% endhint %}
  
  | Parameters                | Value |
  | :------------- ---------: | :---: |
  | Optimal Usage             |  45%  |
  | Base Variable Borrow Rate |   0   | 
  | Variable Rate Slope 1     |   4%  |
  | Variable Rate Slope 2     | 300%  |
  | Base Stable Borrow Rate   |   2%  |
  | Stable Rate Slope 1       |   7%  |
  | Stable Rate Slope 2       | 300%  |

## Rate Strategy Stable One
Low liquidity stablecoins have lower Optimal Utilisation Ratio than those with higher liquidity.

{% hint style="info" %}
DAI
{% endhint %}

  | Parameters                | Value |
  | :------------- ---------: | :---: |
  | Optimal Usage             |  90%  |
  | Base Variable Borrow Rate |   0   | 
  | Variable Rate Slope 1     |   4%  |
  | Variable Rate Slope 2     |  60%  |
  | Base Stable Borrow Rate   |   2%  |
  | Stable Rate Slope 1       |  0.5% |
  | Stable Rate Slope 2       |  60%  |

## Rate Strategy Stable One
High liquidity stablecoins which are callibrated to lower rates to encourage borrow.

{% hint style="info" %}
SUSD, USDC, USDT, EURS, JEUR, AGEUR
{% endhint %}

  | Parameters                         | Value |
  | :------------- ---------:          | :---: |
  | Optimal Usage                      |  80%  |
  | Base Variable Borrow Rate          |   0   | 
  | Variable Rate Slope 1              |   4%  |
  | Variable Rate Slope 2              |  75%  |
  | Base Stable Borrow Rate            |   1%  |
  | Stable Rate Slope 1                |  0.5% |
  | Stable Rate Slope 2                |  75%  |
  | Optimal Stable to Total Debt Ratio |  20%  |

## Interest Rate Parameters Change

When market conditions change, risks change. The utilisation of reserves is continuously monitored to check liquidity is available. In case of prolonged full utilisation, the interest rate parameters are adapted to mitigate any risks emerging from market conditions

The borrow interest rates paid are distributed as yield for aToken holders who have supplied to the protocol, excluding a share of yields sent to the ecosystem reserve defined by the reserve factor. This interest rate is generated on the asset that is borrowed out then shared among all the liquidity providers. The supply APY, $$D_t$$, is:

{% hint style="info" %}
When market conditions change, the interest rate parameters must be changed to adapt to utilisation on Aave’s market as well as to incentives across DeFi.
{% endhint %}

$$S_t = U_t ( SB_t S_t   + VB_t V_t)(1-R_t)$$

* $$U_t$$, the utilisation ratio
* $$SB_t$$, the share of stable borrows
* $$S_t$$, the average stable rate
* $$VB_t$$, the share of variable borrows
* $$V_t$$, the variable rate
* $$R_t$$, the reserve factor

You can view the protocol's deposit APY on the [Aave App](https://app.aave.com/reserve-overview/?underlyingAsset=0xd586e7f844cea2f87f50152665bcbc2c279d8d70&marketName=proto_avalanche_v3) for each asset.

The average Supply APY over a period also includes Flash Loan fees.
