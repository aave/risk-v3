---
description: Mitigating liquidity risk through the borrow interest rate model
---

# Borrow Interest Rate

Aave’s interest rate strategy is calibrated to manage liquidity risk and optimise utilisation. The borrow interest rates come from the [Utilisation Rate](historical-utilization.md) $$U$$.

$$U$$is an indicator of the availability of capital in the pool. The interest rate model is used to manage liquidity risk through user incentivises to support liquidity:

* When capital is available: low interest rates to encourage loans.
* When capital is scarce: high interest rates to encourage repayments of loans and additional deposits.

To retrieve the interest rate strategy contract on-chain, see [this section of the developer docs](https://docs.aave.com/developers/the-core-protocol/lendingpool#getreservedata).

## Interest Rate Model

Liquidity risk materialises when utilisation is high, its becomes more problematic as $$U$$ gets closer to 100%. To tailor the model to this constraint, the interest rate curve is split in two parts around an optimal utilisation rate $$U_{optimal}$$. Before  $$U_{optimal}$$the slope is small, after it starts rising sharply.&#x20;

The interest rate$$R_t$$follows the model:

$$if \hspace{1mm} U < U_{optimal}:  \hspace{1cm}  R_t = R_0 + \frac{U_t}{U_{optimal}} R_{slope1}$$  &#x20;

$$if \hspace{1mm} U \geq  U_{optimal}:  \hspace{1cm} R_t = R_0 + R_{slope1} + \frac{U_t-U_{optimal}}{1-U_{optimal}}R_{slope2}$$



In the borrow rate technical implementation, the [calculateCompoundedInterest](https://github.com/aave/protocol-v2/blob/baeb455fad42d3160d571bd8d3a795948b72dd85/contracts/protocol/libraries/math/MathUtils.sol#L45) method relies on an approximation that mostly affects high interest rates. The resulting actual borrow rate can is:

&#x20;$$Actual APY = (1+Theoretical APY/secsperyear)^{secsperyear}-1$$

Both the variable and stable interest models, are derived from the formula above from the [Whitepaper](https://github.com/aave/aave-protocol/blob/master/docs/Aave\_Protocol\_Whitepaper\_v1\_0.pdf) with different parameters for each asset.

* When $$U < U_{optimal}$$ the borrow interest rates increase slowly with utilisation
* When $$U \geq  U_{optimal}$$ the borrow interest rates increase sharply with utilisation to above 50% APY if the liquidity is fully utilised.

Variable loans see their rate constantly evolving with utilisation. This means they are not ideal for financial planning.

Hence stable loans, that maintain their interest rate at issuance until the specific rebalancing conditions are met. For rebalancing the stable rate down, the loans stable rate$$S$$needs to be greater than the current stable rate$$S_t$$ plus a delta equal to 20%: $$S \geq S_t + 20\%$$.

For rebalancing the stable rate up, these two conditions need to be met:

1. Utilisation Rate: $$U_t > 95\%$$&#x20;
2. Overall Borrow Rate, the weighted average of all the borrow rates: $$R_O < 25\%$$&#x20;



## Model Parameters

The interest rate parameters have been calibrated per cluster of currencies that share similar risk profiles. First, it's crucial to distinguish assets that are used predominantly as collateral (volatile assets) which need liquidity at all times to enable liquidations. These assets require a low Optimal Utilisation rate typically calibrated around 45%. Secondly, the asset's liquidity on Aave is an important factor as the more liquidity, the more stable the utilisation: interest rates of assets with lower liquidity should be more conservative. For example lower liquidity stablecoins have lower Optimal Utilisation Ratio than those with higher liquidity.&#x20;

It's also key to consider market conditions: how can the asset be used in the current market? Aave's borrowing costs must be aligned with market yield opportunities. Or there would be a rate arbitrage with rational users incentivized to borrow all the liquidity on Aave to take advantage of higher yield opportunities.

When market conditions change, the interest rate parameters can be adapted. These changes must adapt to utilisation on Aave’s market as well as to incentives across DeFi.

The interest rate curve of SNX is much higher than that of other assets due to the staking incentives of the Synthetix platform. This makes SNX the most utilised pool generating the highest yields.

With the rise of liquidity mining, Aave also adapted its cost of borrowing by lowering  $$U_{optimal}$$ of the assets affected. This increased the borrow costs that are now partially offset by the liquidity reward.

Following the favorable historical review of liquidity risk, the interest rate models have been optimised to be more competitive while keeping theirs risk mitigation properties.&#x20;

### Variable Interest Rate Model Parameters

| Asset  |  $$U_{optimal}$$ | Base | Slope 1 | Slope 2 |
| ------ | :--------------: | :--: | :-----: | :-----: |
| AMPL   |        75%       |  0%  |    2%   | 10,000% |
| BUSD   |        80%       |  0%  |    4%   |   100%  |
| DAI    |        80%       |  0%  |    4%   |   75%   |
| GUSD   |        80%       |  0%  |    4%   |   100%  |
| PAX    |        90%       |  0%  |    4%   |   60%   |
| RAI    |        80%       |  0%  |    4%   |   75%   |
| sUSD   |        80%       |  0%  |    4%   |   100%  |
| TUSD   |        80%       |  0%  |    4%   |   75%   |
| USDC   |        90%       |  0%  |    4%   |   60%   |
| USDT   |        90%       |  0%  |    4%   |   60%   |
| AAVE   |                  |      |         |         |
| BAL    |        45%       |  0%  |    7%   |   300%  |
| BAT    |        45%       |  0%  |    7%   |   300%  |
| CRV    |        45%       |  0%  |    7%   |   300%  |
| DPI    |                  |      |         |         |
| ENJ    |        45%       |  0%  |    7%   |   300%  |
| ETH    |        65%       |  0%  |    8%   |   100%  |
| KNC    |                  |      |         |         |
| LINK   |        45%       |  0%  |    7%   |   300%  |
| MANA   |        45%       |  0%  |    7%   |   300%  |
| MKR    |        45%       |  0%  |    7%   |   300%  |
| REN    |        45%       |  0%  |    7%   |   300%  |
| REP    |        45%       |  0%  |    7%   |   150%  |
| SNX    |        80%       |  3%  |   12%   |   100%  |
| UNI    |        45%       |  0%  |    7%   |   300%  |
| WBTC   |        65%       |  0%  |    7%   |   100%  |
| XSUSHI |                  |      |         |         |
| YFI    |        45%       |  0%  |    7%   |   300%  |
| ZRX    |        45%       |  0%  |    7%   |   300%  |

### Stable Interest Rate Model Parameters

The stable rate provides predictability for the borrower which comes at a cost, as the interest rates are higher than the variable rate. However the rate of a stable loan is fixed until the rebalancing conditions are met:

1. Utilisation Rate: $$U_t > 95\%$$&#x20;
2. Overall Borrow Rate, the weighed average of all the borrow rates: $$R_O < 25\%$$&#x20;

The currencies the most exposed to liquidity risk do not offer stable rate borrowing.

The base rate of the stable rate model corresponds to the average market rate of the asset.

| Asset  |  $$U_{optimal}$$ | Base | Slope 1 | Slope 2 |
| ------ | :--------------: | :--: | :-----: | :-----: |
| AMPL   |                  |      |         |         |
| BUSD   |                  |      |         |         |
| DAI    |        80%       |  4%  |    2%   |   75%   |
| GUSD   |                  |      |         |         |
| PAX    |                  |      |         |         |
| RAI    |                  |      |         |         |
| sUSD   |                  |      |         |         |
| TUSD   |        80%       |  4%  |    2%   |   75%   |
| USDC   |        90%       |  4%  |    2%   |   60%   |
| USDT   |        90%       | 3.5% |    2%   |   60%   |
| AAVE   |                  |      |         |         |
| BAL    |                  |      |         |         |
| BAT    |        45%       |  3%  |   10%   |   300%  |
| CRV    |                  |      |         |         |
| ENJ    |        45%       |  3%  |   10%   |   300%  |
| ETH    |        65%       |  3%  |   10%   |   100%  |
| KNC    |        65%       |  3%  |   10%   |   300%  |
| LINK   |        45%       |  3%  |   10%   |   300%  |
| MANA   |        45%       |  3%  |   10%   |   300%  |
| MKR    |        45%       |  3%  |   10%   |   300%  |
| REN    |                  |      |         |         |
| SNX    |                  |      |         |         |
| UNI    |                  |      |         |         |
| WBTC   |        65%       |  3%  |   10%   |   60%   |
| XSUSHI |                  |      |         |         |
| YFI    |                  |      |         |         |
| ZRX    |        45%       |  3%  |   10%   |   300%  |

## Interest Rate Parameters Change

When market conditions change, risks change. The utilisation of reserves is continuously monitored to check liquidity is available. In case of prolonged full utilisation, the interest rate parameters are adapted to mitigate any risks emerging from market conditions

![Interest Rate Parameters Updates from V1 to V2](<../.gitbook/assets/Screenshot 2020-12-07 at 14.36.15.png>)

## Interest Rate Curves

This section shows Aave's **** APY per asset. ​

### AMPL

![Please note the AMPL interest rate model is extreme due to the rebasing nature of the token](<../.gitbook/assets/Screenshot 2021-11-23 at 18.46.56.png>)

### **BUSD | GUSD | sUSD**

![](<../.gitbook/assets/Screenshot 2021-11-23 at 18.44.25.png>)

### DAI | TUSD

![](<../.gitbook/assets/Screenshot 2021-11-23 at 18.41.46.png>)

### USDC | USDT

![](<../.gitbook/assets/Screenshot 2021-11-23 at 18.48.25.png>)

### BAL | BAT | CRV  | ENJ | LINK | MANA | MKR | REN |  WBTC | UNI | YFI | ZRX

![](<../.gitbook/assets/Screenshot 2021-11-23 at 18.50.23.png>)

No stable borrows for BAL, CRV, REN and YFI

### SNX

![](<../.gitbook/assets/Screenshot 2021-11-23 at 18.52.26.png>)

### WETH

![](<../.gitbook/assets/Screenshot 2021-11-23 at 18.54.20.png>)

## Related Smart Contracts

|      | Token                                                                                                               | aToken                                                                                                              | Stable Debt Token                                                                                                   | Variable Debt Token                                                                                                 | Interest Rate Strategy                                                                                                |
| ---- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| BUSD | [0x4fabb145d64652a948d72533023f6e7a623c7c53](https://etherscan.io/token/0x4fabb145d64652a948d72533023f6e7a623c7c53) | [0xA361718326c15715591c299427c62086F69923D9](https://etherscan.io/token/0xA361718326c15715591c299427c62086F69923D9) |                                                                                                                     | [0xbA429f7011c9fa04cDd46a2Da24dc0FF0aC6099c](https://etherscan.io/token/0xbA429f7011c9fa04cDd46a2Da24dc0FF0aC6099c) | [0x26D40544447F68a3De69005822195549934624B9](https://etherscan.io/address/0x26D40544447F68a3De69005822195549934624B9) |
| DAI  | [0x6b175474e89094c44da98b954eedeac495271d0f](https://etherscan.io/token/0x6b175474e89094c44da98b954eedeac495271d0f) | [0x028171bCA77440897B824Ca71D1c56caC55b68A3](https://etherscan.io/token/0x028171bCA77440897B824Ca71D1c56caC55b68A3) | [0x778A13D3eeb110A4f7bb6529F99c000119a08E92](https://etherscan.io/token/0x778A13D3eeb110A4f7bb6529F99c000119a08E92) | [0x6C3c78838c761c6Ac7bE9F59fe808ea2A6E4379d](https://etherscan.io/token/0x6C3c78838c761c6Ac7bE9F59fe808ea2A6E4379d) | [0xfffE32106A68aA3eD39CcCE673B646423EEaB62a](https://etherscan.io/address/0xfffE32106A68aA3eD39CcCE673B646423EEaB62a) |
| GUSD | [0x056fd409e1d7a124bd7017459dfea2f387b6d5cd](https://etherscan.io/token/0x056fd409e1d7a124bd7017459dfea2f387b6d5cd) | [0xD37EE7e4f452C6638c96536e68090De8cBcdb583](https://etherscan.io/token/0xD37EE7e4f452C6638c96536e68090De8cBcdb583) |                                                                                                                     | [0x279AF5b99540c1A3A7E3CDd326e19659401eF99e](https://etherscan.io/token/0x279AF5b99540c1A3A7E3CDd326e19659401eF99e) | [0x2893405d64a7Bc8Db02Fa617351a5399d59eCf8D](https://etherscan.io/address/0x2893405d64a7Bc8Db02Fa617351a5399d59eCf8D) |
| sUSD | [0x57ab1ec28d129707052df4df418d58a2d46d5f51](https://etherscan.io/token/0x57ab1ec28d129707052df4df418d58a2d46d5f51) | [0x6C5024Cd4F8A59110119C56f8933403A539555EB](https://etherscan.io/token/0x6C5024Cd4F8A59110119C56f8933403A539555EB) |                                                                                                                     | [0xdC6a3Ab17299D9C2A412B0e0a4C1f55446AE0817](https://etherscan.io/token/0xdC6a3Ab17299D9C2A412B0e0a4C1f55446AE0817) | [0x3082D0a473385Ed2cbd1f16087ab8b7BF79f0355](https://etherscan.io/address/0x3082D0a473385Ed2cbd1f16087ab8b7BF79f0355) |
| TUSD | [0x0000000000085d4780b73119b644ae5ecd22b376](https://etherscan.io/token/0x0000000000085d4780b73119b644ae5ecd22b376) | [0x101cc05f4A51C0319f570d5E146a8C625198e636](https://etherscan.io/token/0x101cc05f4A51C0319f570d5E146a8C625198e636) | [0x7f38d60D94652072b2C44a18c0e14A481EC3C0dd](https://etherscan.io/token/0x7f38d60D94652072b2C44a18c0e14A481EC3C0dd) | [0x01C0eb1f8c6F1C1bF74ae028697ce7AA2a8b0E92](https://etherscan.io/token/0x01C0eb1f8c6F1C1bF74ae028697ce7AA2a8b0E92) | [0x0DdEC679166C367ae45036c8b2c169C5FB2dceE1](https://etherscan.io/address/0x0DdEC679166C367ae45036c8b2c169C5FB2dceE1) |
| USDC | [0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48](https://etherscan.io/token/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48) | [0xBcca60bB61934080951369a648Fb03DF4F96263C](https://etherscan.io/token/0xBcca60bB61934080951369a648Fb03DF4F96263C) | [0xE4922afAB0BbaDd8ab2a88E0C79d884Ad337fcA6](https://etherscan.io/token/0xE4922afAB0BbaDd8ab2a88E0C79d884Ad337fcA6) | [0x619beb58998eD2278e08620f97007e1116D5D25b](https://etherscan.io/token/0x619beb58998eD2278e08620f97007e1116D5D25b) | [0x8Cae0596bC1eD42dc3F04c4506cfe442b3E74e27](https://etherscan.io/address/0x8Cae0596bC1eD42dc3F04c4506cfe442b3E74e27) |
| USDT | [0xdac17f958d2ee523a2206206994597c13d831ec7](https://etherscan.io/token/0xdac17f958d2ee523a2206206994597c13d831ec7) | [0x3Ed3B47Dd13EC9a98b44e6204A523E766B225811](https://etherscan.io/token/0x3Ed3B47Dd13EC9a98b44e6204A523E766B225811) | [0xe91D55AB2240594855aBd11b3faAE801Fd4c4687](https://etherscan.io/token/0xe91D55AB2240594855aBd11b3faAE801Fd4c4687) | [0x531842cEbbdD378f8ee36D171d6cC9C4fcf475Ec](https://etherscan.io/token/0x531842cEbbdD378f8ee36D171d6cC9C4fcf475Ec) | [0x515E87cb3fec986050F202a2bbfa362A2188bc3F](https://etherscan.io/address/0x515E87cb3fec986050F202a2bbfa362A2188bc3F) |
| AAVE | [0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9](https://etherscan.io/token/0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9) | [0xFFC97d72E13E01096502Cb8Eb52dEe56f74DAD7B](https://etherscan.io/token/0xFFC97d72E13E01096502Cb8Eb52dEe56f74DAD7B) |                                                                                                                     |                                                                                                                     |                                                                                                                       |
| BAT  | [0x0d8775f648430679a709e98d2b0cb6250d2887ef](https://etherscan.io/token/0x0d8775f648430679a709e98d2b0cb6250d2887ef) | [0x05Ec93c0365baAeAbF7AefFb0972ea7ECdD39CF1](https://etherscan.io/token/0x05Ec93c0365baAeAbF7AefFb0972ea7ECdD39CF1) | [0x277f8676FAcf4dAA5a6EA38ba511B7F65AA02f9F](https://etherscan.io/token/0x277f8676FAcf4dAA5a6EA38ba511B7F65AA02f9F) | [0xfc218A6Dfe6901CB34B1a5281FC6f1b8e7E56877](https://etherscan.io/token/0xfc218A6Dfe6901CB34B1a5281FC6f1b8e7E56877) | [0xBdfC85b140edF1FeaFd6eD664027AA4C23b4A29F](https://etherscan.io/address/0xBdfC85b140edF1FeaFd6eD664027AA4C23b4A29F) |
| CRV  | [0xd533a949740bb3306d119cc777fa900ba034cd52](https://etherscan.io/token/0xd533a949740bb3306d119cc777fa900ba034cd52) | [0x8dAE6Cb04688C62d939ed9B68d32Bc62e49970b1](https://etherscan.io/token/0x8dAE6Cb04688C62d939ed9B68d32Bc62e49970b1) |                                                                                                                     | [0x00ad8eBF64F141f1C81e9f8f792d3d1631c6c684](https://etherscan.io/token/0x00ad8eBF64F141f1C81e9f8f792d3d1631c6c684) | [0xE3a3DE71B827cB73663A24cDB6243bA7F986cC3b](https://etherscan.io/address/0xE3a3DE71B827cB73663A24cDB6243bA7F986cC3b) |
| ENJ  | [0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c](https://etherscan.io/token/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c) | [0xaC6Df26a590F08dcC95D5a4705ae8abbc88509Ef](https://etherscan.io/token/0xaC6Df26a590F08dcC95D5a4705ae8abbc88509Ef) | [0x943DcCA156b5312Aa24c1a08769D67FEce4ac14C](https://etherscan.io/token/0x943DcCA156b5312Aa24c1a08769D67FEce4ac14C) | [0x38995F292a6E31b78203254fE1cdd5Ca1010A446](https://etherscan.io/token/0x38995F292a6E31b78203254fE1cdd5Ca1010A446) | [0x4a4fb6B26e7F516594b7242240039EA8FAAc897a](https://etherscan.io/address/0x4a4fb6B26e7F516594b7242240039EA8FAAc897a) |
| KNC  | [0xdd974d5c2e2928dea5f71b9825b8b646686bd200](https://etherscan.io/token/0xdd974d5c2e2928dea5f71b9825b8b646686bd200) | [0x39C6b3e42d6A679d7D776778Fe880BC9487C2EDA](https://etherscan.io/token/0x39C6b3e42d6A679d7D776778Fe880BC9487C2EDA) | [0x9915dfb872778B2890a117DA1F35F335eb06B54f](https://etherscan.io/token/0x9915dfb872778B2890a117DA1F35F335eb06B54f) | [0x6B05D1c608015Ccb8e205A690cB86773A96F39f1](https://etherscan.io/token/0x6B05D1c608015Ccb8e205A690cB86773A96F39f1) | [0xFDBDa42D2aC1bfbbc10555eb255De8387b8977C4](https://etherscan.io/address/0xFDBDa42D2aC1bfbbc10555eb255De8387b8977C4) |
| LINK | [0x514910771af9ca656af840dff83e8264ecf986ca](https://etherscan.io/token/0x514910771af9ca656af840dff83e8264ecf986ca) | [0xa06bC25B5805d5F8d82847D191Cb4Af5A3e873E0](https://etherscan.io/token/0xa06bC25B5805d5F8d82847D191Cb4Af5A3e873E0) | [0xFB4AEc4Cc858F2539EBd3D37f2a43eAe5b15b98a](https://etherscan.io/token/0xFB4AEc4Cc858F2539EBd3D37f2a43eAe5b15b98a) | [0x0b8f12b1788BFdE65Aa1ca52E3e9F3Ba401be16D](https://etherscan.io/token/0x0b8f12b1788BFdE65Aa1ca52E3e9F3Ba401be16D) | [0xED6547b83276B076B771B88FcCbD68BDeDb3927f](https://etherscan.io/address/0xED6547b83276B076B771B88FcCbD68BDeDb3927f) |
| MANA | [0x0f5d2fb29fb7d3cfee444a200298f468908cc942](https://etherscan.io/token/0x0f5d2fb29fb7d3cfee444a200298f468908cc942) | [0xa685a61171bb30d4072B338c80Cb7b2c865c873E](https://etherscan.io/token/0xa685a61171bb30d4072B338c80Cb7b2c865c873E) | [0xD86C74eA2224f4B8591560652b50035E4e5c0a3b](https://etherscan.io/token/0xD86C74eA2224f4B8591560652b50035E4e5c0a3b) | [0x0A68976301e46Ca6Ce7410DB28883E309EA0D352](https://etherscan.io/token/0x0A68976301e46Ca6Ce7410DB28883E309EA0D352) | [0x004fC239848D8A8d3304729b78ba81d73d83C99F](https://etherscan.io/address/0x004fC239848D8A8d3304729b78ba81d73d83C99F) |
| MKR  | [0x9f8f72aa9304c8b593d555f12ef6589cc3a579a2](https://etherscan.io/token/0x9f8f72aa9304c8b593d555f12ef6589cc3a579a2) | [0xc713e5E149D5D0715DcD1c156a020976e7E56B88](https://etherscan.io/token/0xc713e5E149D5D0715DcD1c156a020976e7E56B88) | [0xC01C8E4b12a89456a9fD4e4e75B72546Bf53f0B5](https://etherscan.io/token/0xC01C8E4b12a89456a9fD4e4e75B72546Bf53f0B5) | [0xba728eAd5e496BE00DCF66F650b6d7758eCB50f8](https://etherscan.io/token/0xba728eAd5e496BE00DCF66F650b6d7758eCB50f8) | [0xE3a3DE71B827cB73663A24cDB6243bA7F986cC3b](https://etherscan.io/address/0xE3a3DE71B827cB73663A24cDB6243bA7F986cC3b) |
| REN  | [0x408e41876cccdc0f92210600ef50372656052a38](https://etherscan.io/token/0x408e41876cccdc0f92210600ef50372656052a38) | [0xCC12AbE4ff81c9378D670De1b57F8e0Dd228D77a](https://etherscan.io/token/0xCC12AbE4ff81c9378D670De1b57F8e0Dd228D77a) | [0x3356Ec1eFA75d9D150Da1EC7d944D9EDf73703B7](https://etherscan.io/token/0x3356Ec1eFA75d9D150Da1EC7d944D9EDf73703B7) | [0xcd9D82d33bd737De215cDac57FE2F7f04DF77FE0](https://etherscan.io/token/0xcd9D82d33bd737De215cDac57FE2F7f04DF77FE0) | [0x9B1e3C7483F0f21abFEaE3AeBC9b47b5f23f5bB0](https://etherscan.io/address/0x9B1e3C7483F0f21abFEaE3AeBC9b47b5f23f5bB0) |
| SNX  | [0xc011a72400e58ecd99ee497cf89e3775d4bd732f](https://etherscan.io/token/0xc011a72400e58ecd99ee497cf89e3775d4bd732f) | [0x35f6B052C598d933D69A4EEC4D04c73A191fE6c2](https://etherscan.io/token/0x35f6B052C598d933D69A4EEC4D04c73A191fE6c2) |                                                                                                                     | [0x267EB8Cf715455517F9BD5834AeAE3CeA1EBdbD8](https://etherscan.io/token/0x267EB8Cf715455517F9BD5834AeAE3CeA1EBdbD8) |                                                                                                                       |
| UNI  | [0x1f9840a85d5af5bf1d1762f925bdaddc4201f984](https://etherscan.io/token/0x1f9840a85d5af5bf1d1762f925bdaddc4201f984) | [0xB9D7CB55f463405CDfBe4E90a6D2Df01C2B92BF1](https://etherscan.io/token/0xB9D7CB55f463405CDfBe4E90a6D2Df01C2B92BF1) |                                                                                                                     | [0x5BdB050A92CADcCfCDcCCBFC17204a1C9cC0Ab73](https://etherscan.io/token/0x5BdB050A92CADcCfCDcCCBFC17204a1C9cC0Ab73) | [0x24ABFac8dd8f270D752837fDFe3B3C735361f4eE](https://etherscan.io/token/0x24ABFac8dd8f270D752837fDFe3B3C735361f4eE)   |
| WBTC | [0x2260fac5e5542a773aa44fbcfedf7c193bc2c599](https://etherscan.io/token/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599) | [0x9ff58f4fFB29fA2266Ab25e75e2A8b3503311656](https://etherscan.io/token/0x9ff58f4fFB29fA2266Ab25e75e2A8b3503311656) | [0x51B039b9AFE64B78758f8Ef091211b5387eA717c](https://etherscan.io/token/0x51B039b9AFE64B78758f8Ef091211b5387eA717c) | [0x9c39809Dec7F95F5e0713634a4D0701329B3b4d2](https://etherscan.io/token/0x9c39809Dec7F95F5e0713634a4D0701329B3b4d2) | [0xf41E8F817e6C399d1AdE102059c454093b24f35B](https://etherscan.io/token/0xf41E8F817e6C399d1AdE102059c454093b24f35B)   |
| WETH | [0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2](https://etherscan.io/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2) | [0x030bA81f1c18d280636F32af80b9AAd02Cf0854e](https://etherscan.io/token/0x030bA81f1c18d280636F32af80b9AAd02Cf0854e) | [0x4e977830ba4bd783C0BB7F15d3e243f73FF57121](https://etherscan.io/token/0x4e977830ba4bd783C0BB7F15d3e243f73FF57121) | [0xF63B34710400CAd3e044cFfDcAb00a0f32E33eCf](https://etherscan.io/token/0xF63B34710400CAd3e044cFfDcAb00a0f32E33eCf) | [0x4ce076b9dD956196b814e54E1714338F18fde3F4](https://etherscan.io/token/0x4ce076b9dD956196b814e54E1714338F18fde3F4)   |
| YFI  | [0x0bc529c00c6401aef6d220be8c6ea1667f6ad93e](https://etherscan.io/token/0x0bc529c00c6401aef6d220be8c6ea1667f6ad93e) | [0x5165d24277cD063F5ac44Efd447B27025e888f37](https://etherscan.io/token/0x5165d24277cD063F5ac44Efd447B27025e888f37) |                                                                                                                     | [0x7EbD09022Be45AD993BAA1CEc61166Fcc8644d97](https://etherscan.io/token/0x7EbD09022Be45AD993BAA1CEc61166Fcc8644d97) | [0xfd71623D7F41360aefE200de4f17E20A29e1d58C](https://etherscan.io/token/0xfd71623D7F41360aefE200de4f17E20A29e1d58C)   |
| ZRX  | [0xe41d2489571d322189246dafa5ebde1f4699f498](https://etherscan.io/token/0xe41d2489571d322189246dafa5ebde1f4699f498) | [0xDf7FF54aAcAcbFf42dfe29DD6144A69b629f8C9e](https://etherscan.io/token/0xDf7FF54aAcAcbFf42dfe29DD6144A69b629f8C9e) | [0x071B4323a24E73A5afeEbe34118Cd21B8FAAF7C3](https://etherscan.io/token/0x071B4323a24E73A5afeEbe34118Cd21B8FAAF7C3) | [0x85791D117A392097590bDeD3bD5abB8d5A20491A](https://etherscan.io/token/0x85791D117A392097590bDeD3bD5abB8d5A20491A) | [0x1a4babC0e20d892167792AC79618273711afD3e7)](https://etherscan.io/token/0x1a4babC0e20d892167792AC79618273711afD3e7)  |

## Deposit APY

The borrow interest rates paid are distributed as yield for aToken holders who have deposited in the protocol, excluding a share of yields sent to the ecosystem reserve defined by the reserve factor. This interest rate is paid on the capital that is lent out then shared among all the liquidity providers. The deposit APY, $$D_t$$, is:

$$D_t = U_t ( SB_t S_t   + VB_t V_t)(1-R_t)$$

* $$U_t$$, the utilisation ratio
* $$SB_t$$, the share of stable borrows
* $$S_t$$, the average stable rate
* $$VB_t$$, the share of variable borrows
* $$V_t$$, the variable rate
* $$R_t$$, the reserve factor

You can view the protocol's deposit APY on the [Aave App](https://app.aave.com/reserve-overview/DAI-0x6b175474e89094c44da98b954eedeac495271d0f0x24a42fd28c976a61df5d00d0599c34c4f90748c8) for each asset.

The average Deposit APY over a period also includes Flash Loan fees.
