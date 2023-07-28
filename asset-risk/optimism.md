---
description: Aave's deployment on the Optimism
---

# Optimism

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0xba58ab5e24dcaef5490fd8717320f74e3c85aea36811d421b48822d4069b6d45), V3 of the Aave Protocol has been deployed on Optimism. Optimism is a Layer 2 Optimistic Rollup network designed to utilize the strong security guarantees of Ethereum while reducing its cost and latency. Optimism is EVM equivalent, making the transition from L1 to L2 as seamless as possible

You can read more about optimism [👉 here](https://www.optimism.io/about)

### Risk Parameters

View reserve parameters on [live dashboard](https://config.fyi).

The reserve factor is accumulated to the [treasury controller contract](https://optimistic.etherscan.io/address/0xA77E4A084d7d4f064E326C0F6c0aCefd47A5Cb21#code)

### Price Feed

The price update frequency results from the liquidation strategy. We follow a margin method, in which prices are refreshed every time the deviation crosses a certain threshold. We use [Chainlink](https://chain.link)’s decentralised oracles for the price feeds.

The Optimism Chainlink oracles are available in the following [address repository](https://docs.chain.link/docs/optimism-price-feeds/).

| Pair Data Feed                                                            | Deviation Threshold | Oracle Contract Address                                                                                                          |
| :-----------------------------------------------------------------------: | :-----------------: | :------------------------------------------------------------------------------------------------------------------------------: |
| [DAI/USD](https://data.chain.link/optimism/mainnet/stablecoins/dai-usd)   | 0.1%                | [0x8dBa75e83DA73cc766A7e5a0ee71F656BAb470d6](https://optimistic.etherscan.io/address/0x8dBa75e83DA73cc766A7e5a0ee71F656BAb470d6) |
| [SUSD/USD](https://data.chain.link/optimism/mainnet/crypto-usd/susd-usd)  | 0.5%                | [0x7f99817d87baD03ea21E05112Ca799d715730efe](https://optimistic.etherscan.io/address/0x7f99817d87baD03ea21E05112Ca799d715730efe) |
| [USDC/USD](https://data.chain.link/optimism/mainnet/stablecoins/usdc-usd) | 0.1%                | [0x16a9FA2FDa030272Ce99B29CF780dFA30361E0f3](https://optimistic.etherscan.io/address/0x16a9FA2FDa030272Ce99B29CF780dFA30361E0f3) |
| [USDT/USD](https://data.chain.link/optimism/mainnet/stablecoins/usdt-usd) | 0.1%                | [0xECef79E109e997bCA29c1c0897ec9d7b03647F5E](https://optimistic.etherscan.io/address/0xECef79E109e997bCA29c1c0897ec9d7b03647F5E) |
| [AAVE/USD](https://data.chain.link/optimism/mainnet/crypto-usd/aave-usd)  | 0.2%                | [0x338ed6787f463394D24813b297401B9F05a8C9d1](https://optimistic.etherscan.io/address/0x338ed6787f463394D24813b297401B9F05a8C9d1) |
| [LINK/USD](https://data.chain.link/optimism/mainnet/crypto-usd/link-usd)  | 0.2%                | [0xCc232dcFAAE6354cE191Bd574108c1aD03f86450](https://optimistic.etherscan.io/address/0xCc232dcFAAE6354cE191Bd574108c1aD03f86450) |
| [BTC/USD](https://data.chain.link/optimism/mainnet/crypto-usd/btc-usd)    | 0.1%                | [0xD702DD976Fb76Fffc2D3963D037dfDae5b04E593](https://optimistic.etherscan.io/address/0xD702DD976Fb76Fffc2D3963D037dfDae5b04E593) |
| [ETH/USD](https://data.chain.link/optimism/mainnet/crypto-usd/eth-usd)    | 0.15%               | [0x13e3Ee699D1909E989722E753853AE30b17e08c5](https://optimistic.etherscan.io/address/0x13e3Ee699D1909E989722E753853AE30b17e08c5) |

### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://optimistic.etherscan.io/address/0x76fb31fb4af56892a25e32cfc43de717950c9278) | [aOptAAVE](https://optimistic.etherscan.io/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sOptAAVE](https://optimistic.etherscan.io/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vOptAAVE](https://optimistic.etherscan.io/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) | [InterestRateStrategy](https://optimistic.etherscan.io/address/0xee1bac9355eaafcd1b68d272d640d870bc9b4b5c#code) |
| [DAI](https://optimistic.etherscan.io/address/0xda10009cbd5d07dd0cecc66161fc93d7c9000da1) | [aOptDAI](https://optimistic.etherscan.io/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sOptDAI](https://optimistic.etherscan.io/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vOptDAI](https://optimistic.etherscan.io/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| [InterestRateStrategy](https://optimistic.etherscan.io/address/0xA9F3C3caE095527061e6d270DBE163693e6fda9D#code) |
| [USDT](https://optimistic.etherscan.io/address/0x94b008aa00579c1307b0ef2c499ad98a8ce58e58#code) | [aOptUSDT](https://optimistic.etherscan.io/address/0x6ab707aca953edaefbc4fd23ba73294241490620#code) | [sOptUSDT](https://optimistic.etherscan.io/address/0x70effc565db6eef7b927610155602d31b670e802#code) | [vOptUSDT](https://optimistic.etherscan.io/address/0xfb00ac187a8eb5afae4eace434f493eb62672df7#code) | [InterestRateStrategy](https://optimistic.etherscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [LINK](https://optimistic.etherscan.io/address/0x350a791Bfc2C21F9Ed5d10980Dad2e2638ffa7f6) | [aOptLINK](https://optimistic.etherscan.io/address/0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530) | [sOptLINK](https://optimistic.etherscan.io/address/0x89D976629b7055ff1ca02b927BA3e020F22A44e4#code) | [vOptLINK](https://optimistic.etherscan.io/address/0x953A573793604aF8d41F306FEb8274190dB4aE0e) | [InterestRateStrategy](https://optimistic.etherscan.io/address/0xee1bac9355eaafcd1b68d272d640d870bc9b4b5c#code) |
| [SUSD](https://optimistic.etherscan.io/address/0x8c6f28f2f1a3c87f0f938b96d27520d9751ec8d9) | [aOptSUSD](https://optimistic.etherscan.io/address/0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97) | [sOptSUSD](https://optimistic.etherscan.io/address/0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E#code) | [vOptSUSD](https://optimistic.etherscan.io/address/0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8) | [InterestRateStrategy](https://optimistic.etherscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [USDC](https://optimistic.etherscan.io/address/0x7f5c764cbc14f9669b88837ca1490cca17c31607) | [aOptUSDC](https://optimistic.etherscan.io/address/0x625E7708f30cA75bfd92586e17077590C60eb4cD) | [sOptUSDC](https://optimistic.etherscan.io/address/0x307ffe186F84a3bc2613D1eA417A5737D69A7007#code) | [vOptUSDC](https://optimistic.etherscan.io/address/0xFCCf3cAbbe80101232d343252614b6A3eE81C989) | [InterestRateStrategy](https://optimistic.etherscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [WBTC](https://optimistic.etherscan.io/address/0x68f180fcce6836688e9084f035309e29bf0a2095) | [aOptWBTC](https://optimistic.etherscan.io/address/0x078f358208685046a11C85e8ad32895DED33A249) | [sOptWBTC](https://optimistic.etherscan.io/address/0x633b207Dd676331c413D4C013a6294B0FE47cD0e#code) | [vOptWBTC](https://optimistic.etherscan.io/address/0x92b42c66840C7AD907b4BF74879FF3eF7c529473) | [InterestRateStrategy](https://optimistic.etherscan.io/address/0xee1bac9355eaafcd1b68d272d640d870bc9b4b5c#code) |
| [WETH](https://optimistic.etherscan.io/address/0x4200000000000000000000000000000000000006) | [aOptWETH](https://optimistic.etherscan.io/address/0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8) | [sOptWETH](https://optimistic.etherscan.io/address/0xD8Ad37849950903571df17049516a5CD4cbE55F6#code) | [vOptWETH](https://optimistic.etherscan.io/address/0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351) | [InterestRateStrategy](https://optimistic.etherscan.io/address/0xee1bac9355eaafcd1b68d272d640d870bc9b4b5c#code) |

### Disclaimer

{% hint style=“info” %} Aave team do not hold any keys to the multisig controlling Aave V3 markets on Optimism {% endhint %}

During an initial bootstrapping phase, the Optimism deployment is controlled by a Gnosis safe multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.
