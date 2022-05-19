# Adding an Asset


Aave enables users to deposit and borrow digital currencies through the pooling of funds. Depositors receive protocol-issued aTokens, which gather deposits and the interest generated. Each loan is secured by a collateral acting as a risk mitigation tool against default. As the means of exchange, currencies are central in Aave’s non-custodial lending operations. More details on how the protocol works can be found in [Aave’s V3 Whitepaper](https://github.com/aave/aave-v3-core/blob/master/techpaper/Aave_V3_Technical_Paper.pdf).

Given the specificities of Aave’s model, currencies are added with the following constraints:

1. **Each additional currency will slightly increase the gas cost of the borrow and redeem actions permanently.** The currency must be included in the smart contract, adding complexity and thus costs.
2. **Each currency added to Aave protocol as collateral increases the protocol risk of insolvency.** From a financial perspective, the assets of Aave Protocol are the collaterals, while the liabilities are the borrowed amounts. The underlying currencies of assets and liabilities often differ, with loans mostly taken in stablecoins and backed by volatile tokens. This means the protocol is heavily exposed to the failure of supported token systems as well as market fluctuations. This is mitigated by the possibility to add a collateral in isolation mode with a specific debt ceiling, with only certain assets, currently stablecoins, available for borrowing.
3. **A centralised currency accepted as collateral exposes the protocol to its centralisation risk.** The single point of failure risks of underlying currencies flow into Aave Protocol.
4. **Currencies only enabled for depositing and borrowing (not usable as collaterals) present lower risk for the protocol.** Collaterals are the assets of the protocol. To remain solvent, these assets must remain greater than the liabilities, the borrows. Currencies which can only be used for borrowing should always be excessively backed by the collaterals.
5. **Having volume across currencies in our lending pools reduces risks via diversification benefits.**

When adding a currency to the protocol, significant controls are required to ensure the currency will add more value than risk. Aave V3 offers risk mitigation tools that can be used to list riskier assets faster. The currency risk methodology explores whether the currencies represent a reasonable amount of risk for the protocol, calibrating the currencies parameters to mitigate those risks.&#x20;

{% hint style="info" %}
See the [Governance docs](https://docs.aave.com/governance/) for the new asset listing process.
{% endhint %}
