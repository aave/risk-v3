# Methodology
The composability of DeFi enables the Aave Protocol to connect with the rest of the ecosystem; however, it also exposes the protocol to various ecosystem risks. Tokens used in the protocol affect the protocol at its core (specifically tokens accepted as collateral which safeguard the solvency of the protocol). At least three different aspects of risk are important to assessing whether an asset exposes the Aave Protocol to undue risk: smart contract risk, counterparty risk, and market risk.

First, the Aave community must look at smart contract security and any risk presented by counterparties within the token’s protocol governance. If the risks are perceived to be unreasonably high, the tokens in question should be disqualified from usage within the aave protocol or be listed as Isolated assets. Then, the Aave community should look at market risks, which can be managed via the protocol’s set parameters.

## Risk Scale and Quantification Criterion

The following risk scale is created by Aave team as a reference guide, which can be used by the Aave community, for asset risk analysis. 

**Risk scale** ranges from **lowest risk (A+)** for the safest assets of the protocol (e.g., Ethereum) to the **highest risk (D-)**. The assets exposed to high risk factors may still be considered for integration; however, they should not qualify as collateral or be limited to Isolated mode to shield solvency of the protocol.

The historical data can be quantified in three different aspects of market risks as follows:

- Smart-contract Risk: quantified by **Days,** **Transactions**
- Counterparty Risk: quantified by **Holders**, **Permission**
- Market Risk: quantified by **Market Cap**, **Average Volume**, **Normalized Volatility**

These ratings are calculated per sub-factor and then aggregated via a rounded up average to account for diversification benefits.

![Risk Quantification Criterion](<../.gitbook/assets/Screenshot 2020-12-02 at 14.13.08.png>)

## Risk Factors

### Smart Contract Risk

**Smart contract risk** focuses on measuring the technical security of the underlying code for any asset. Only code for assets that have undergone rigorous audits by well-respected auditors are appropriate for the Aave Protocol; regardless of audits, smart contract risk remains (i.e., it can never be eliminated fully) and users must be vigilant in assessing such risk. Bug bounties can be used to help reduce smart contract risk. The **maturity** of any code can be assessed based on the number of days and the number of transactions with a particular smart contract — use, community, development and, in some instances, reliability are proxies for how battle-tested the code is.

Smart contract hacks have already resulted in millions of funds lost; accordingly, tokens with the highest smart-contract risk (i.e., D+ and below), should not be used as collateral. For clarity, tokens with a risk rating below D should not be integrated in the protocol.

### Counter-party Risk

**Counter-party risk** assesses qualitatively how and by who the currency is governed. There are different degrees of governance decentralisation that may give direct control over funds (e.g., as backing) or attack vectors to the governance architecture, which could expose control and funds. Counterparty risk is determined by the level of **centralisation**, which is measured by the number of parties that control a token’s protocol, as well as the number of holders and the level of **trust** in the entity, project, or processes.

Tokens with a high counterparty risk (i.e., below D+) should be disqualified for use as collateral.

### Market Risk

**Market risks** are linked to the size of a particular asset pool in the protocol, as well as fluctuations in both supply and demand. The markets need to hold sufficient volume to account for any liquidations in the particular pool (i.e., sell offs which tend to lower the price of the underlying asset through slippage affecting the value recovered).

Market risk assessments should use an average 24Hr volume representing the availability of the asset to assess **liquidity risk**: *E*[*volume*]

The **volatility risk** is based on the normalised fluctuations in the token price and is calculated as the standard deviation of the logarithmic returns: $$\sigma[ ln( \frac{close(t+1)}{close(t)})]$$This metric is in line with industry standards used by [Bitmex](https://www.bitmex.com/app/index/.EVOL7D) or [Gauntlet](https://gauntlet.network/reports/CompoundMarketRiskAssessment.pdf).

These values should be assessed at the following intervals: 1 week, 1 month, 3 months, 6 months, and 1 year.

Tokens can be subject to sudden volatility spikes, and it is not uncommon to witness a 30% price change within a week or a month. When a price increase occurs, a parameter readjustment may be implemented to limit the risks of new operations. 

Finally, we also consider the **market capitalisation** representing the size of the market.

Market risks are used to calibrate the model’s [risk parameters](risk-parameters.md). Volatility helps to define the required level of collateralisation, (i.e., the [Loan to Value](risk-parameters.md#loan-to-value)). The liquidity risks are contained by liquidation incentives (i.e., the [liquidation threshold](risk-parameters.md#liquidation-threshold) and [bonus](risk-parameters.md#liquidation-bonus)).

Tokens with high market risk might only qualify as collateral in *Isolation Mode*, which restricts them only back *Isolated Stablecoins*
