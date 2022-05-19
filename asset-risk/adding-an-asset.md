# Adding an Asset

Aave enables users to supply and borrow digital assets through the pooling of funds. Suppliers receive protocol-issued aTokens, which gather supplies and the interest generated. Each borrow is secured by a collateral acting as a risk mitigation tool against default. 
More details on how the protocol works can be found in [Aave’s Technical Paper](https://github.com/aave/aave-v3-core/blob/master/techpaper/Aave_V3_Technical_Paper.pdf).

https://github.com/aave/aave-v3-core/blob/master/techpaper/Aave_V3_Technical_Paper.pdf

Given the specificities of Aave’s model, the selection of assets has been performed with the following constraints:

1. **Each additional token slightly increase the gas cost of the borrow and redeem actions permanently.** The token must be included in the smart contract, adding complexity and thus costs.

2. **Each token added to Aave protocol as collateral increases the protocol risk of insolvency.** From a financial perspective, the assets of Aave Protocol are the collaterals, while the liabilities are the borrowed amounts. The underlying tokens of assets and liabilities often differ, with borrows mostly in stablecoins and backed by volatile tokens. This means the protocol is heavily exposed to the failure of supported token systems as well as market fluctuations.

{% hint style="info" %}
To mitigate the protocol risk of insolvency, V3 allows to list new riskier token in *Isolation Mode*. Read more [👉🏻 Isolation Mode](https://docs.aave.com/developers/whats-new/isolation-mode)
{% endhint %}

3. **A centralised asset accepted as collateral exposes the protocol to its centralisation risk.** The single point of failure risks of underlying token flow into Aave Protocol.

4. **Assets only enabled for supplying and borrowing (not usable as collaterals) aka _Siloed assets_ present lower risk for the protocol.** Collaterals are the assets of the protocol. To remain solvent, these assets must remain greater than the liabilities. Tokens which can only be used for borrowing should always be excessively backed by collateral assets.

5. **Having liquidity from different tokens in our pools reduces risks via diversification benefits.**

When adding a token to the protocol, significant controls are required to ensure the asset will add more value than risk. Only tokens with a worthy product and significant community should be considered. The asset risk methodology offers a framework to assess and compare the tokens' risks for the protocol, and how to calibrate model parameters to mitigate those risks.

{% hint style="info" %}
  V3 of Aave protocol introduce new `ASSET_LISTING_ADMIN` role, assigned by Aave Governance, which allows holders of this role to:
  - add new assets to the Aave V3 markets
  - update asset oracle sources
  - update fallback oracles
{% endhint %}

{% hint style="info" %}
See the [Governance docs](https://docs.aave.com/governance/) for the new asset listing process.
{% endhint %}
