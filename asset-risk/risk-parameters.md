# Risk Parameters

Each asset within the Aave Protocol has specific values related to their risk, which influences how they are supplied and borrowed within the protocol. V3 has better risk mitigations tools with additional risk parameters relating to security, governance, and the markets.

It is crucial for Aave community understand the underlying risk of each asset: assess the smart contracts security, understand the risks of centralisation and market risks. Onboarded assets, onboard their risks to the Aave Protocol. Aave V3 offers new risk mitigation parameters that allow the onboarding of assets highly exposed to these risk factors with limits and isolation mode.

All the assets supported by the Aave protocol are added via the Aave Governance proposal or via the Asset listing admins selected by the Aave Governance.

You can find the risk parameters per markets in:

* [Polygon](polygon.md)
* [Avalanche](avalanche.md)

To retrieve the relevant values directly from the smart contracts, see [this section of the developer docs](https://docs.aave.com/developers/core-contracts/pool#getreservedata).

## Risk Parameters Analysis

The risk parameters mitigate the market risks of the assets supported by the Aave protocol. Each borrow is based on an over-collateralization with a different asset that may, be subject to volatility. Sufficient margin and incentives are needed for the position to remain collateralised in the event of adverse market conditions. If the value of the collateral falls bellow a predetermined threshold, a portion of it will be auctioned as a `LIQUIDATION_BONUS` to repay a portion of the debt position and keep the ongoing borrow collateralised.

Market risks can be mitigated through Aave’s risk parameters, which define collateralisation and liquidation rules.

These parameters are calibrated on a per asset basis to account for the specific risks identified.

The Aave Protocol V3 introduces 👇🏻 new (additional) risk parameters to provide a higher level of protection against insolvency.

### Supply Caps

Supply caps define the maximum amount of an asset which can be supplied to the protocol. Supply caps can be used to limit the protocol’s exposure to riskier assets and protect against infinite minting exploits. A supply cap is an optional parameter, and the value will depend on on-chain liquidity of the asset and total volume of collateral assets in the pool.

### Borrow Caps

Borrow caps define the maximum amount of an asset which can be borrowed. Borrow caps can be used to prevent traditional and flash borrowing of an asset which may experience a price exploit and lead to protocol insolvency. A borrow cap is an optional parameter, and the value will depend on-chain liquidity of the asset and total volume of borrowed assets in the pool.

### Isolation Mode

Isolation mode can be used to limit the systemic risk of listing riskier assets. Isolation mode limits an asset to only borrow isolated stablecoins and only use a single isolated asset as collateral at a time. More info on isolation mode can be found [here](https://docs.aave.com/developers/whats-new/isolation-mode).

### Siloed Mode

In V3, new assets with potentially manipulatable oracles (e.g., illiquid Uni V3 pairs where the price can be affected drastically by a single trade) can be listed in Siloed Mode to limit the overall risk of insolvency of the protocol. A siloed asset on the Aave Protocol restricts the borrower to single borrows only (i.e., a user borrowing a siloed asset cannot borrow any other asset).

### eMode

Efficient Mode (”eMode”) allows assets which are correlated in price (e.g., DAI, USDC, and USDT) to be listed in the same eMode category which maximises capital efficiency by allowing higher LTVs when both the borrowed and collateral asset belong to the same eMode category. Currently, only a single eMode category is defined in the Aave Protocol V3 markets - Stablecoins, category 1.

V3 allows `RISK_ADMINS` and `POOL_ADMIN`, selected by Aave Governance, to configure up to 255 eMode categories, with each `EModeCategory` having the following risk management parameters:

* LTV (loan to value)
* Liquidation Threshold
* Liquidation Bonus
* Custom price oracle (optional)

Other risk parameters from V2

### Loan to Value

The Loan to Value (”LTV”) ratio defines the maximum amount of assets that can be borrowed with a specific collateral. It is expressed as a percentage (e.g., at LTV=75%, for every 1 ETH worth of collateral, borrowers will be able to borrow 0.75 ETH worth of the corresponding currency). Once a borrow occurs, the LTV evolves with market conditions.

### Liquidation Threshold

The liquidation threshold is the percentage at which a position is defined as undercollateralised. For example, a Liquidation threshold of 80% means that if the value rises above 80% of the collateral, the position is undercollateralised and could be liquidated.

The delta between the LTV and the Liquidation Threshold is a safety mechanism in place for borrowers.

{% hint style="info" %}
For each wallet, the Liquidation Threshold is calculate as the weighted average of the Liquidation Thresholds of the collateral assets and their value:

$$Liquidation \: Threshold= \frac{ \sum{Collateral_i \: in \: ETH \: \times \: Liquidation \: Threshold_i}}{Total \: Collateral \: in \: ETH \:}$$
{% endhint %}

### Liquidation Penalty

The liquidation penalty is a fee rendered on the price of assets of the collateral when liquidators purchase it as part of the liquidation of a loan that has passed the liquidation threshold.

### Liquidation Factor

The liquidation factor directs a share of the liquidation penalty to a collector contract from the ecosystem treasury.

### Health Factor

For each wallet, these risks parameters enable the calculation of the health factor:

$$H_f = \frac{ \sum{Collateral_i \: in \: ETH \: \times \: Liquidation \: Threshold_i}}{Total \: Borrows \: in \: ETH}$$

When $$H_f < 1$$ the position may be liquidated to maintain solvency as described in the diagram below.

![Risk Parameters Safeguard Solvency](<../.gitbook/assets/Risk - Alexandra@2x (3).jpg>)

### Reserve Factor

The reserve factor allocates a share of the protocol’s interests to a collector contract from the ecosystem treasury.

Aave’s solvency risk is covered by the Safety Module, with incentives originating from the ecosystem reserve. As such, the Reserve Factor is a risk premium calibrated based on the overall risk of the asset. Stablecoins are the least risky assets with a lower reserve factor while volatile assets hold more risk and have a higher factor.

### Collaterals

USDT and sUSD have increased risk exposure due to the risk of a single point of failure in their governance. Their counterparty risk is too high, both in terms of centralisation and trust. For this reason, they cannot warrant the solvency of the protocol. Accordingly, these assets are limited to be used as collateral in Isolation Mode. On the other hand, agEUR and jEUR are decentralised; however, these assets have little battle-testing and cannot be used as collateral.

Overall, stablecoins are used both for borrowing and as collateral, while volatile assets, which many users are long on, are mostly used as collateral. Hence, users of the protocol still benefit from the addition of these stablecoins, and their risks are mitigated by the fact they cannot be used as collateral.

### From Risks to Risk Parameters

Market risks have the most direct impact on the risk parameters:

#### Liquidity

Liquidity based on on-chain liquidity and trading volume, is key for the liquidation process. These can be mitigated through the caps and liquidation parameters (i.e., the lower the liquidity, the higher the incentives).

#### Volatility

Price volatility can negatively affect the collateral which must cover liabilities and safeguards the solvency of the protocol. The risk of the collateral falling below the borrowed amounts can be mitigated through the level of coverage required through the LTV. It also affects the liquidation process as the margin for liquidators needs to allow for profit.

The least volatile currencies are stablecoins followed by ETH. They have the highest LTV at 75%, and the highest liquidation threshold at 80%.

The most volatile assets have the lowest LTV at 35% and 40%. The liquidation thresholds are set at 65% to protect our users from a sharp drop in price which could lead to undercollaterisation followed by liquidation.

#### Market Capitalisation

Market capitalisation represents the size of the market, which is key when it comes to liquidating collateral. While the risk of assets with smaller market capitalisations is more contained, it is often more volatile as these assets are generally less mature. A higher market capitalisation, among other factors, typically signals a more developed ecosystem (i.e., more liquidity on exchanges, which enables liquidations with less of an impact on price). The market capitalisation, along with liquidity, both on exchanges and on Aave, allow for the quantification of liquidation risks. The liquidation parameters are therefore adjusted to mitigate the risk of a high price impact liquidation for assets with smaller markets (i.e., the smaller the market cap, the higher the incentives).

#### Overall Risk

The overall risk rating is used to calibrate the Reserve Factor with factors ranging from 10% for the less risky assets to 35% for the riskiest.
