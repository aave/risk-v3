# Aave's Risk Framework

{% hint style="info" %}
Aave holds security at its core with V3 audits by [Trail of Bits](https://github.com/aave/aave-v3-core/blob/master/audits/07-01-2022\_TrailOfBits\_AaveV3.pdf), [ABDK](https://github.com/aave/aave-v3-core/blob/master/audits/27-01-2022\_ABDK\_AaveV3.pdf), [Peckshield](https://github.com/aave/aave-v3-core/blob/master/audits/14-01-2022\_PeckShield\_AaveV3.pdf), [OpenZeppelin](https://github.com/aave/aave-v3-core/blob/master/audits/01-11-2021\_OpenZeppelin\_AaveV3.pdf), \[SigmaPrime] and formal verification by [Certora](https://github.com/aave/aave-v3-core/blob/master/Certora/certora/Verification\_Report.pdf) further detailed in Security & Audits.
{% endhint %}

Aave Protocol V3 introduces more sophisticated risk parameters and features to provide the protocol with a high level of protection against potential insolvency.&#x20;

👇🏻 is the list of new protocol _risk management_ additions

* **Isolation mode assets** allows to list riskier assets in _Isolation,_ restricting to:
  * borrowing restricted to isolated stablecoins
  * use of single isolated asset as collateral at a time
* **Siloed assets** allows assets with potentially manipulatable oracle to be listed as supply-only i.e. cannot be used as collateral.
* **New Permissioned Roles** for `RISK_ADMIN` Aave Governance can now elect entities with a permissioned role in the protocol. These entities can change risk parameters, if needed, without a governance vote for parameter update. This enables protocol to adjust risk parameters more efficiently and quickly as the market matures.
* **Supply and Borrow caps** each asset reserve can now be configured to have upper bounds on supply and borrow (optional). This helps in reducing exposure to certain assets and mitigates infinite minting or price oracle manipulation risks.
* **Variable liquidation close factor** In V3 liquidation mechanism has been improved to allow the position to be fully liquidated when it approaches insolvency (HF < 0.95)
* **Price Oracle sentinel** mainly aimed for L2s to handle eventual downtime of the sequencers by introducing a grace period for liquidations and ability for `RISK_ADMINS` to disable borrowing for a reserve under specific circumstances.

The following documentation analyses the fundamental risks of the protocol and describes the processes in place to mitigate them in more details.

{% hint style="info" %}
If you have any questions, join the [Aave community Discord server](https://discord.gg/fVaDMqT); our team and members of the community look forward to helping you understand Aave's risks and risk management procedures.
{% endhint %}
