# Risk Parameters

Each asset in the Aave protocol has specific values related to their risk, which influences how they are supplied and borrowed in the protocol. The calibration of the parameters for V3 is more aggressive and have additional risk parameters.

The table below shows a summary of the latest values.
{% hint style="info" %}
Some of the tokens are listed only in some of the V3 markets based on their availability in the given L1 or L2 chain and associated risk.
{% endhint %}
[Risk]

| Name                  | Symbol | Siloed | Collateral in Isolation | Borrow in Isolation | Loan To Value | Liquidation Threshold | Liquidation Bonus | Debt Ceiling  | Supply Cap | Borrow Cap | Reserve Factor | Markets  |
| --------------------- | ------ | :----: | :---------------------: | :-----------------: | :-----------: | :-------------------: | :---------------: | :-----------: | :--------: | :--------: | :------------: | :------- |
| **Stablecoins**       |        |        |                         |                      |               |                       |                   |               |            |            |                | 
| DAI                   | DAI    | false  |         -               |         true         |      75%      |          80%          |         5%        |       -       |     2B     |     0      |       10%      | Optimism, Arbitrum, Polygon, Fantom, Avalanche, Harmony
| USDC                  | USDC   | false  |         -               |         true         | 82.5% (Polygon, Avalanche, Fantom)/80%(Optimism, Arbitrum, Harmony) |          85%          |         4%        |       -       |     2B     |      0     |       10%      | Optimism, Arbitrum, Polygon, Fantom, Avalanche, Harmony
| Tether                | USDT   | false  |       true              |         true         |       75%     |          80%          |         5%        |      5M       |     2B     |      0     |       10%      | Optimism, Arbitrum, Polygon, Fantom, Avalanche, Harmony
| Synthetix USD         | SUSD   | false  |         -               |          -           |       -       |           -           |         -         |      -        |     2B     |      0     |       10%      | Optimism,
| Statis EURS Token     | EURS   | false  |         -               |          -           |       65%     |          70%          |         7.5%      |      5M       |     2B     |      0     |       10%      | Arbitrum, Polygon
| Jarvis synthetic Euro | JEUR   | false  |                         |          -           |       -       |           0           |         0         |       -       |     -      |      -     |       20%      | Polygon
| Angel Protocol Euro   | agEUR  | false  |                         |          -           |       -       |           0           |         0         |       -       |     -      |      -     |       20%      | Polygon
                         | 
| **Other Assets**      |        |        |                         |                      |               |                       |                   |               |            |            |                |
| Chainlink             | LINK   | false  |                         |          -           | 50%(Polygon, Avalanche, Fantom) / 70% (Arbitrum, Optimism, Harmony) | 65%(Polygon, Avalanche, Fantom) / 75% (Arbitrum, Optimism, Harmony) |         7.5%      |       -       |    0       |     0      |       20%      | Optimism, Arbitrum, Polygon, Fantom, Avalanche, Harmony
| Wrapped BTC           | WBTC   | false  |                         |          -           |      70%      |          75%          |         6.5%      |       -       |    0       |     0      |       20%      | Optimism, Arbitrum, Polygon, Fantom, Avalanche, Harmony
| Wrapped ETH           | WETH   | false  |                         |          -           |      80%      |          82.5%        |         5%        |       -       |    0       |     0      |       10%      | Optimism, Arbitrum, Polygon, Fantom, Avalanche, Harmony
| Aave                  | AAVE   | false  |                         |          -           |      60%      |          70%          |         7.5%      |       -       |    0       |     -      |       0%       | Optimism, Arbitrum, Polygon, Avalanche, Harmony
| Polygon protocol coin | WMATIC | false  |                         |          -           |      65%      |          70%          |        10%        |       -       |    0       |     0      |       20%      | Polygon
| Harmony protocol coin | WONE   |     ye |                         |                      |      80%      |          85%          |         5%        |               |            |            |       10%      | Harmony
| Fantom protocol       | WFTM   |     ye |                         |                      |      80%      |          85%          |         5%        |               |            |            |       10%      | Fantom
| Avalanche protocol    | WAVAX  |     ye |                         |                      |      80%      |          85%          |         5%        |               |            |            |       10%      | Avalanche
| Aavegotchi            | GHST   | false  |                         |          -           |      25%      |          45%          |        15%        |       -       |    0       |     0      |       10%      | Polygon
| Balancer              | BAL    | false  |                         |          -           |      20%      |          45%          |        10%        |       -       |    0       |     0      |       20%      | Polygon
| Curve DAO             | CRV    | false  |                         |          -           |      75%      |          80%          |         5%        |       -       |    0       |     0      |       10%      | Polygon, Fantom
| DeFi Pulse Index      | DPI    | false  |                         |          -           |      20%      |          45%          |        10%        |       -       |    0       |     0      |       20%      | Polygon
| Sushi                 | SUSHI  | false  |                         |          -           |      20%      |          45%          |        10%        |       -       |    0       |     0      |       20%      | Polygon, Fantom

The table above results from the asset risk assessment relating to security, governance and the markets. Assets with security concerns around their smart contract cannot be considered for integration since these risks are impossible to control. Similarly, tokens with high risk exposure to single counter-parties cannot be used as collateral.

To retrieve the relevant values directly from the smart contracts, see [this section of the developer docs](https://docs.aave.com/developers/the-core-protocol/lendingpool#getreservedata).

Gauntlet Network has tested the model parameterisation finding a low risk of insolvency but also suggesting some minor changes to further reduce it. The details can be found in Risk Audits, [Gauntlet Aave Market Risk Assessment](../audits/gauntlet.md).


{% hint style="info" %}
V2 [ 👉🏻 risk parameter change](https://docs.aave.com/risk/asset-risk/risk-parameters#risk-parameters-change).
{% endhint %}

## Risk Parameters Analysis
The risk parameters allow to mitigate market risks of the assets supported on Aave Protocol. Each borrowing is guaranteed by a collateral that may be subject to volatility. Sufficient margin and incentives are needed for the position to remain collateralised in adverse market conditions. If the value of the collateral falls bellow a threshold, part of it is auctioned as `LIQUIDATION_BONUS` to repay portion of the debt position and keep the ongoing borrowing collateralised.

Market risks can be mitigated through Aave’s risk parameters which define collateralisation and liquidation rules.

These parameters are calibrated per asset to account for the specific risks identified as shown in Figure 2.


Aave Protocol V3 introduces 👇🏻 new (additional) risk parameters to provide a higher level of protection against insolvency.


### Supply Caps:
Supply caps define the maximum amount of an asset which can be supplied to the protocol. Supply caps can be used to limit the protocol exposure to riskier asset, and prevent against infinite minting exploits. A supply cap is an optional parameter, and the value will depend on the circulating and maximum supply of the asset.

### Borrow Caps
Borrow caps define the maximum amount of an asset which can be borrowed. Borrow caps can be used to prevent traditional and flash borrowing of an asset which may experience a price exploit and lead to protocol insolvency. A borrow cap is an optional parameter, and the value will depend on the circulating and maximum supply of the asset.

### Isolation Mode
Isolation mode can be used to limit the systemic risk of listing riskier assets. The *Isolation mode* limits an asset to:
- only borrow isolated stablecoins
- only use single isolated asset as collateral at a time

More info on isolation mode can be found [here](https://docs.aave.com/developers/whats-new/isolation-mode).

### Siloed Mode
In V3 new assets with potentially manipulatable oracles (eg. illiquid Uni V3 pairs) can be listed in ***Siloed Mode*** to limit the risk of overall solvency of the protocol. A *siloed* assets is listed on Aave protocol as supply-only assets i.e. cannot be used as collateral.


Other risk parameters also supported in V2

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

### Collaterals

USDT, BUSD, PAX and sUSD are strongly exposed to the risk of single point of failure in their governance. Their counter-party risk is too high both in terms of centralisation and trust. For this reason, we cannot consider them to be warrant of the solvency of the protocol. On the other hand, AMPL and RAI are decentralised, though AMPL struggles with stability while RAI has little battletesting.  These assets cannot be used as collaterals

Overall, stablecoins are mostly used for borrowing, while volatile assets which users are long on are mostly used as collateral. Hence, the users of the protocol still gain great benefits from the addition of these stablecoins. Their risks are mitigated by the fact they cannot be used as collateral.


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
