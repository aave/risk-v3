# Adding an Asset

Aave enables users to supply and borrow digital assets through liquidity pools. Suppliers receive protocol-issued aTokens, holding the user’s supplied assets and accrued yield. Each borrow is secured by collateral acting as a risk mitigation tool against default. More details on how the protocol works can be found in [Aave’s Technical Paper](https://github.com/aave/aave-v3-core/blob/master/techpaper/Aave\_V3\_Technical\_Paper.pdf).

Given the specificities of Aave V3, the 👇🏻 listed assets follow specific considerations:

* [Polygon V3 market assets](polygon.md#related-smart-contracts)
* [Harmony V3 market assets](harmony.md#related-smart-contracts)
* [Avalanche V3 market assets](avalanche.md#related-smart-contracts)
* [Arbitrum V3 market assets](arbitrum.md#related-smart-contracts)
* [Optimism V3 market assets](optimism.md#related-smart-contracts)
* [Fantom V3 market assets](fantom.md#related-smart-contracts)

1. **Each additional token slightly increase the gas cost of transactions permanently.** The token must be included in the smart contract, adding complexity and thus costs.
2.  **Each token added to Aave protocol as collateral increases the protocol risk of insolvency.** From a financial perspective, the token enabled as collateral can be considered as assets of Aave protocol, while the amount of tokens borrowed considered as the liabilities of the Aave protocol. The underlying tokens of assets and liabilities often differ, with borrows mostly in stablecoins and tokens used as collateral being volatile tokens. Thus, it is crucial that while adding new tokens the Aave Community considers:



    * Only assets with best risk profiles should be supported as collateral
    * Riskier assets should only be enabled as collateral in _Isolation mode_
    * New assets with higher risk and lower liquidity should be only considered listed in _Isolation mode_ (for both borrow and collateral use)

    {% hint style="info" %}
    To mitigate the protocol risk of insolvency, V3 allows to list new riskier token in _Isolation Mode_. Read more [👉🏻 Isolation Mode](https://docs.aave.com/developers/whats-new/isolation-mode)
    {% endhint %}
3. **A centralised asset accepted as collateral exposes the protocol to centralisation risk.** The single point of failure risks of underlying tokens flow into the Aave Protocol.
4. **Assets that have risk of manipulable oracles are listed as single borrow assets** (i.e. if a user borrows said asset, they cannot borrow any other asset (a/k/a Siloed assets)).
5. Tokens only enabled for supplying and borrowing (i.e., not usable as collateral) present lower risk for the protocol. Collateral are the assets of the protocol. To remain solvent, these assets must remain greater than the liabilities borrowed from the protocol. Tokens which can only be used for borrowing should always be excessively backed by collateral assets (e.g., a user can supply DAI as collateral and borrow DAI in variable mode backed by DAI as collateral; however, this is not the case for agEUR which is not usable as collateral and must always be borrowed against less risky assets).
6. **Having liquidity from different tokens reduces risks via diversification benefits.**



When adding a token to the protocol, significant analysis must be made by the Aave community to ensure that the asset will add more value than risk. Only tokens with a worthy product and significant community should be considered. The asset risk methodology offers a framework to assess and compare tokens’ risks to the protocol, and how to calibrate model asset parameters to mitigate those risks.

{% hint style="info" %}
V3 of Aave protocol introduce new \`ASSET\_LISTING\_ADMIN\` role, assigned by Aave Governance, which allows holders of this role to: - add new assets to the Aave V3 markets - update asset oracle sources - update fallback oracles
{% endhint %}

{% hint style="info" %}
See the \[Governance docs]\(https://docs.aave.com/governance/) for the new asset listing process.
{% endhint %}
