# Risk Parameters

Each asset in the Aave protocol has specific values related to their risk, which influences how they are supplied and borrowed. The calibration of the parameters for V2 is more aggressive as the Aave ecosystem is mature with some educated users and liquidators. In addition, Gauntlet is optimising the parameters weekly based on market conditions as described in the next section.&#x20;

The table below shows a summary of the latest values.

| Name                  | Symbol | Collateral | Loan To Value | Liquidation Threshold | Liquidation Bonus | Reserve Factor |
| --------------------- | ------ | :--------: | :-----------: | :-------------------: | :---------------: | :------------: |
| **Stablecoins**       |        |            |               |                       |                   |                |
| Ampleforth            | AMPL   |     no     |               |                       |                   |       10%      |
| Binance USD           | BUSD   |     no     |       -       |           -           |         -         |       10%      |
| DAI                   | DAI    |     yes    |      75%      |          80%          |         5%        |       10%      |
| Fei                   | FEI    |     no     |               |                       |                   |       20%      |
| Frax                  | FRAX   |     no     |               |                       |                   |       10%      |
| Gemini Dollars        | GUSD   |     no     |       -       |           -           |         -         |       10%      |
| Paxos Standard        | PAX    |     no     |               |                       |                   |       10%      |
| RAI                   | RAI    |     no     |       -       |           -           |         -         |       20%      |
| Synthetix USD         | SUSD   |     no     |       -       |           -           |         -         |       20%      |
| True USD              | TUSD   |     yes    |      75%      |          80%          |         5%        |       10%      |
| USDC                  | USDC   |     yes    |      80%      |          85%          |         4%        |       10%      |
| Tether                | USDT   |     no     |       -       |           -           |         -         |       10%      |
| **Other Assets**      |        |            |               |                       |                   |                |
| Aave                  | AAVE   |     yes    |      60%      |          70%          |        7.5%       |       0%       |
| Balancer              | BAL    |     yes    |      65%      |          70%          |        10%        |       20%      |
| Basic Attention Token | BAT    |     yes    |      75%      |          80%          |        7.5%       |       20%      |
| Curve DAO             | CRV    |     yes    |      45%      |          60%          |        8.5%       |       20%      |
| DeFi Pulse Index      | DPI    |     yes    |      60%      |          70%          |        10%        |       20%      |
| Enjin                 | ENJ    |     yes    |      60%      |          65%          |        7.5%       |       20%      |
| Ethereum              | ETH    |     yes    |     82.5%     |          85%          |         5%        |       10%      |
| Kyber Network         | KNC    |     yes    |      60%      |          70%          |        10%        |       20%      |
| Chainlink             | LINK   |     yes    |      70%      |          75%          |        10%        |       20%      |
| Decentraland          | MANA   |     yes    |      65%      |          70%          |        7.5%       |       35%      |
| Maker                 | MKR    |     yes    |      65%      |          70%          |         8%        |       20%      |
| Republic Protocol     | REN    |     yes    |      60%      |          65%          |         8%        |       20%      |
| Ren Filecoin          | RenFIL |     no     |       -       |           -           |         -         |       35%      |
| Synthetix             | SNX    |     yes    |      40%      |          60%          |        7.5%       |       35%      |
| Uniswap               | UNI    |     yes    |      60%      |          70%          |        10%        |       20%      |
| Wrapped BTC           | WBTC   |     yes    |      70%      |          75%          |        6.5%       |       20%      |
| Wrapped ETH           | WETH   |     yes    |      80%      |          85%          |         5%        |       10%      |
| Sushi Bar             | XSUSHI |     yes    |      45%      |          60%          |        8.5%       |       35%      |
| Yearn YFI             | YFI    |     yes    |      50%      |          65%          |        7.5%       |       20%      |
| 0x                    | ZRX    |     yes    |      65%      |          70%          |        7.5%       |       20%      |

The table above results from the asset risk assessment relating to security, governance and the markets. Tokens with security concerns around their smart contract cannot be considered for integration since these risks are impossible to control. Similarly, tokens with high risk exposure to single counter-parties cannot be used as collateral.

To retrieve the relevant values directly from the smart contracts, see [this section of the developer docs](https://docs.aave.com/developers/the-core-protocol/lendingpool#getreservedata).

Gauntlet Network has tested the model parameterisation finding a low risk of insolvency but also suggesting some minor changes to further reduce it. The details can be found in Risk Audits, [Gauntlet Aave Market Risk Assessment](../audits/gauntlet.md).



## Risk Parameters Change

When market conditions change, risks change, and so we are continuously monitoring the assets integrated into the protocol which sometimes requires to quickly adapt the risk parameters. The table below tacks parameters changes which are in bold.

### Dynamic Risk Parameter by Gauntlet

[AIP 29](https://app.aave.com/governance/25-QmcbpNrBCbJcQiyEgHpeE1D9PajYd9D8iCwbAt7mFGngmS) The Aave DAO elected Gauntlet to provide dynamic risk parameters recommendations for the Aave Protocol.

**22/10/2021** [**AIP 42 Risk Parameter Updates**](https://app.aave.com/#/governance/42-Qmd8PTDdcq971N6QhLAKBdxN3sjdV5KJqqVw45CaRGRnej)****

| Parameter                 | Current Value | Recommended Value |   |   |   |
| ------------------------- | ------------- | ----------------- | - | - | - |
| BAT Liquidation Threshold | 75%           | 80%               |   |   |   |
| CRV Loan To Value         | 35%           | 45%               |   |   |   |
| CRV Liquidation Threshold | 55%           | 60%               |   |   |   |
| ENJ Loan To Value         | 55%           | 60%               |   |   |   |
| REN Loan To Value         | 50%           | 55%               |   |   |   |
| SUSHI Loan To Value       | 30%           | 45%               |   |   |   |
| UNI Loan To Value         | 55%           | 60%               |   |   |   |
| WBTC Liquidation Bonus    | 7.5%          | 6.5%              |   |   |   |
| YFI Liquidation Bonus     | 8%            | 7.5%              |   |   |   |

**9/10/2021** [**AIP 39 Risk Parameters Update**](https://ipfs.aave.com/#/governance/39-QmXQMnHQMP6KmwkCG8MjBCjxxNEeaHszh9FgFZFASkqPS2)****

| Asset  | Reco LTV  (current) | Reco LT  (current) | Reco LB  (current) |
| ------ | ------------------- | ------------------ | ------------------ |
| WETH   | 82.5% (80%)         |                    |                    |
| CRV    | 35% (40%)           |                    |                    |
| ENJ    | 55% (50%)           | 65% (60%)          |                    |
| MANA   | 65% (60%)           | 70% (65%)          |                    |
| UNI    | 50% (60%)           |                    |                    |
| YFI    | 50% (45%)           | 65% (60%)          | 8% (10%)           |
| ZRX    | 65% (60%)           |                    |                    |
| XSUSHI | 30% (35%)           |                    |                    |
| USDC   |                     |                    | 4% (5%)            |

#### 24/09/2021 [AIP 38 Liquidation Bonus for Aave V2 Assets](https://app.aave.com/governance/38-QmciauyTVnoHG6bAXCxHjHqTsUfiDz7rSGFxMADqFgCh4z)

| Current Liquidation\_Bonus | Recommended Liquidation Bonus |
| -------------------------- | ----------------------------- |
| WBTC (9%)                  | 7.5%                          |
| REN (9%)                   | 7.5%                          |
| BAT (9%)                   | 7.5%                          |
| YFI (12.5%)                | 10%                           |
| MKR (10%)                  | 8%                            |
| ZRX (8%)                   | 7.5%                          |
| CRV (12.5%)                | 10%                           |
| XSUSHI (12.5%)             | 10%                           |
| AAVE (8%)                  | 7.5%                          |
| MANA (8%)                  | 7.5%                          |
| SNX (9%)                   | 7.5%                          |

#### 14/09/2021 [AIP 36 LTV and liquidations thresholds to moderate levels](https://app.aave.com/governance/33-QmVkeNwzQzshdjAhZHMQxU5Pbe87TrR1mwnyArzNYiPqaX)&#x20;

| Current LTV/Liq\_Threshold | Moderate LTV | Moderate Liq\_Threshold |
| -------------------------- | ------------ | ----------------------- |

| USDC (80%, 85%) | 82.5 | 85 |
| --------------- | ---- | -- |

| DAI (75%, 80%) | 75 | 80 |
| -------------- | -- | -- |

| TUSD (75%, 80%) | 80 | 82.5 |
| --------------- | -- | ---- |

| WBTC (70%, 75%) | 70 | 75 |
| --------------- | -- | -- |

| WETH (80%, 82.5%) | 80 | 85 |
| ----------------- | -- | -- |

| REN (55%, 60%) | 55 | 65 |
| -------------- | -- | -- |

| BAT (70%, 75%) | 70 | 75 |
| -------------- | -- | -- |

| YFI (40%, 55%) | 45 | 60 |
| -------------- | -- | -- |

| DPI (60%, 70%) | 60 | 70 |
| -------------- | -- | -- |

| LINK (70%, 75%) | 70 | 75 |
| --------------- | -- | -- |

| BAL (55%, 60%) | 65 | 70 |
| -------------- | -- | -- |

| MKR (60%, 65%) | 65 | 70 |
| -------------- | -- | -- |

| ZRX (60%, 65%) | 60 | 70 |
| -------------- | -- | -- |

| UNI (60%, 65%) | 60 | 70 |
| -------------- | -- | -- |

| KNC (60%, 65%) | 60 | 70 |
| -------------- | -- | -- |

| CRV (40%, 55%) | 40 | 55 |
| -------------- | -- | -- |

| XSUSHI (25%, 45%) | 35 | 60 |
| ----------------- | -- | -- |

| ENJ (55%, 60%) | **50** | 60 |
| -------------- | ------ | -- |

| AAVE (50%, 65%) | 60 | 70 |
| --------------- | -- | -- |

| SNX (15%, 40%) | 20 | 45 |
| -------------- | -- | -- |

#### 4/09/2021 [AIP 34 Liquidations Bonus Update](https://app.aave.com/governance/30-QmccRszk94JUyj3xGcBUxUzCo43jZDQYgesEULsudVjm9v)

| Asset  | Current Liquidation Bonus | Recommended Liquidation Bonus Update |
| ------ | ------------------------- | ------------------------------------ |
| ZRX    | 10%                       | 8%                                   |
| WBTC   | 10%                       | 9%                                   |
| SNX    | 10%                       | 9%                                   |
| YFI    | 15%                       | 12.5%                                |
| CRV    | 15%                       | 12.5%                                |
| AAVE   | 10%                       | 8%                                   |
| REN    | 10%                       | 9%                                   |
| MANA   | 10%                       | 8%                                   |
| BAT    | 10%                       | 9%                                   |
| XSUSHI | 15%                       | 12.5%                                |

### Changes from V1 to V2

![Risk Parameter Change from V1 to V2](<../.gitbook/assets/Screenshot 2020-12-07 at 14.26.01.png>)

## Risk Parameters Analysis

The risk parameters allow to mitigate market risks of the currencies supported by the protocol. Each borrowing is guaranteed by a collateral that may be subject to volatility. Sufficient margin and incentives are needed for the position to remain collateralised in adverse market conditions. If the value of the collateral falls bellow a threshold, part of it is auctioned to repay part of the position and keep the ongoing borrowing collateralised.

### Collaterals

USDT, BUSD, PAX and sUSD are strongly exposed to the risk of single point of failure in their governance. Their counter-party risk is too high both in terms of centralisation and trust. For this reason, we cannot consider them to be warrant of the solvency of the protocol. On the other hand, AMPL and RAI are decentralised, though AMPL struggles with stability while RAI has little battletesting.  These assets cannot be used as collaterals

Overall, stablecoins are mostly used for borrowing, while volatile assets which users are long on are mostly used as collateral. Hence, the users of the protocol still gain great benefits from the addition of these stablecoins. Their risks are mitigated by the fact they cannot be used as collateral.

Market risks can be mitigated through Aave’s risk parameters which define collateralisation and liquidation rules. These parameters are calibrated per currency to account for the specific risks identified as shown in Figure 2.

### **Loan to Value**

The Loan to Value (LTV) ratio defines the maximum amount of currency that can be borrowed with a specific collateral. It’s expressed in percentage: at LTV=75%, for every 1 ETH worth of collateral, borrowers will be able to borrow 0.75 ETH worth of the corresponding currency. Once a borrow is taken, the LTV evolves with market conditions.&#x20;

{% hint style="info" %}
\
For each wallet the maximum LTV is calculate as the weighted average of the LTVs of the collateral assets and their value:

$$Max LTV = \frac{ \sum{Collateral_i \: in \: ETH \: \times \: LTV_i}}{Total \: Collateral \: in \: ETH \:}$$
{% endhint %}

### **Liquidation Threshold**

The liquidation threshold is the percentage at which a position is defined as undercollateralised. For example, a Liquidation threshold of 80% means that if the value rises above 80% of the collateral, the position is undercollateralised and could be liquidated.

The delta between the Loan-To-Value and the Liquidation Threshold is a safety cushion for borrowers.

{% hint style="info" %}
For each wallet the Liquidation Threshold is calculate as the weighted average of the Liquidation Thresholds of the collateral assets and their value:

$$Liquidation \: Threshold= \frac{ \sum{Collateral_i \: in \: ETH \: \times \: Liquidation \: Threshold_i}}{Total \: Collateral \: in \: ETH \:}$$
{% endhint %}

### **Liquidation Bonus**

Bonus on the price of assets of the collateral when liquidators purchase it as part of the liquidation of a loan that has passed the liquidation threshold.

### Health Factor

For each wallet, these risks parameters enable the calculation of the health factor:

$$H_f = \frac{ \sum{Collateral_i \: in \: ETH \: \times \: Liquidation \: Threshold_i}}{Total \: Borrows \: in \: ETH}$$&#x20;

When $$H_f < 1$$ the position may be liquidated to maintain solvency as described in the diagram below.

![Risk Parameters Safeguard Solvency](<../.gitbook/assets/Risk - Alexandra@2x (3).jpg>)

### Reserve Factor

The reserve factor allocates a share of the protocol's interests to a collector contract as reserve for the ecosystem. This reserve is new to V2, used to sustain the DAO and pay protocol contributors. It is made out of various assets including AAVE.

Aave's solvency risk is covered by the Safety Module, with the incentives coming from the ecosystem reserve. As such, the Reserve Factor is also a risk premium and so it is calibrated based on the overall risk of the asset. Stablecoins are the less risky assets with lower reserve factor while volatile assets hold more risk with a higher factor.

The collector contract can be found at [0x464c71f6c2f760dda6093dcb91c24c39e5d6e18c](https://etherscan.io/address/0x464c71f6c2f760dda6093dcb91c24c39e5d6e18c).

### From Risks to Risk Parameters

Market risks have the most direct impact on the risk parameters:

#### **Liquidity**&#x20;

The liquidity is based on the volume on the markets, which is key for the liquidation process. This can be mitigated through the liquidation parameters:  the lower the liquidity, the higher the incentives.

#### Volatility

The volatility **** of price can negatively affect the collateral which safeguards the solvency of the protocol and must cover the liabilities. The risk of the collateral falling below the borrowed amounts can be mitigated through the level of coverage required, the Loan-To-Value. It also affects the liquidation process as the margin for liquidators needs to allow for profit.

The less volatile currencies are the stablecoins followed by ETH, they have the highest LTV at 75%, and the highest liquidation threshold at 80%.

The most volatile currencies REP and LEND have the lowest LTV at 35% and 40%. The liquidations thresholds are set at 65% to protect our users from a sharp drop in price which could lead to undercollaterisation followed by liquidation.

#### **Market Capitalisation**

The market capitalisation represents the size of the market, which is important when it comes to liquidating collateral. This can be mitigated through the liquidation parameters: the smaller the market cap, the higher the incentives.

#### Overall Risk

The overall risk rating is used to calibrate the Reserve Factor with factors ranging from 10% for the less risky assets to 35% for the riskiest.
