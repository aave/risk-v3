# Methodology


The composability of DeFi enables Aave Protocol to connect with the rest of the ecosystem. However, it also exposes the protocol to financial contagion. Tokens used in the protocol affect the protocol at its core, in particular tokens accepted as collateral which safeguard the solvency of the protocol. To ensure an asset holds a reasonable amount of risk, we investigate three different levels:
  - Smart Contract Risk
  - Counter-party Risk
  - Market Risk

First, we look at smart contract security and counter-parties in the governance. If these risks are too high, the tokens will be disqualified for the protocol or be listed as *Isolated* or *Siloed* assets. Then we look at market risks, which can be managed via the protocol’s parameters.

## Risk Scale

Our risk scale ranges from **lowest risk A+** for the safest assets of the protocol (often Ethereum) to the **highest risk D-**. The assets exposed to high risk factors can be considered for integration. However, they will not qualify as collateral to shield solvency.

## Risk Factors

### Smart Contract Risk


**Smart contract risk** focuses on the technical security of a token based on its underlying code. If one of the supported tokens is compromised, collaterals will be affected, threatening the solvency of the protocol. Projects must have undergone audits to be considered, yet smart contract risk is significant, bug bounties can help but it cannot be fully mitigated. We assess **maturity** based on the number of days and the number of transactions of the smart contract as a representation of use, community and development. These proxies show how battle-tested the code is.

Smart contract hacks have already resulted in millions of losses and so tokens with the highest smart-contract risk D+ and below, cannot be used as collateral. Tokens with a risk rating below D cannot be integrated in the protocol.

### Counter-party Risk

**Counter-party risk** assesses qualitatively how and by who the currency is governed. We observe difference degrees of governance decentralisation that may give direct control over funds (as backing, for example) or attack vectors to the governance architecture which could expose control and funds. The counter-party risk is measured from the level of **centralisation** corresponding to the number of parties that control the said token's protocol as well as the number of holders and the **trust** in the entity, project or processes.

Tokens with a high counter-party risk below D+ disqualify as collateral i.e. can only be listed as *Siloed Assets*.

### Market Risk


**Market risks** are linked to the market size and fluctuations in offer and demand. These risks are particularly relevant for the assets of the protocol: the collateral. If the value of the collateral decreases, it might reach the liquidation threshold and start getting liquidated. The markets then need to hold sufficient volume for these liquidations - sells which tend to lower the price of the underlying asset through slippage affecting the value recovered.

We look at the average 24h volume representing the availability of the currency to assess **liquidity risk**: $$E[volume]$$&#x20;

The **volatility risk,** based on the normalised fluctuations in the token price and calculated as the standard deviation of the logarithmic returns: $$\sigma[ ln( \frac{close(t+1)}{close(t)})]$$This metric is in line with industry standards used by  [Bitmex](https://www.bitmex.com/app/index/.EVOL7D) or [Gauntlet](https://gauntlet.network/reports/CompoundMarketRiskAssessment.pdf).

We look at these values at: 1 week, 1 month, 3 months, 6 months and 1 year.

Tokens can be subject to sudden volatility spikes; it is not uncommon to witness 30% changes in price within a week or a month. When this is a price increase, to protect our users, it might be followed by a parameter readjustment to limit risks of new operations.

Finally, we also consider the **market capitalisation** representing the size of the market.

Market risks are used for the calibration of the model’s [risk parameters](risk-parameters.md). The volatility helps define the required level of collateralisation, the [Loan to Value](risk-parameters.md#loan-to-value). The liquidity risks are contained by liquidation incentives: the [liquidation threshold](risk-parameters.md#liquidation-threshold) and [bonus](risk-parameters.md#liquidation-bonus).

Tokens with high market risk might only qualify as collateral in *Isolation Mode*, which restricts them to back only *Isolated Stablecoins*

## Risk Assessment
The methodology to link historical data to risk factors has been formalised based on rigid criteria for each factor and rating.

### Risk Quantification Criterion

The historical data is computed through our risk quantification algorithm resulting in risk ratings from the lowest risks A+ to the highest risks D- following the criteria in the table below.

![Risk Quantification Criterion](<../.gitbook/assets/Screenshot 2020-12-02 at 14.13.08.png>)

These ratings are calculated per sub-factor then aggregated via a rounded up average to account for diversification benefits.
