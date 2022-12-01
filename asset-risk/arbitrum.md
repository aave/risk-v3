---
description: Aave's deployment on the Arbitrum
---

# Arbitrum

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0x7c6261b04115e79c63cffb1602295836df36883fc76fc899bce3345c2beaeba3), V3 of the Aave Protocol has been deployed on Arbitrum One. Arbitrum is the leading Ethereum Rollup, with hundreds of live apps, including most top Ethereum apps and infrastructure. Arbitrum’s TVL accounts for 47.8% of TVL across all Ethereum L2s tracked by L2Beat. You can read more [👉🏻 here](https://portal.arbitrum.one)


### Risk Parameters

| Asset | eMode Params     | Borrow | Siloed | Collateral | Borrow Isolation | LTV | Liq. Thresh | Liq. Bonus | Debt Ceil | Supply Cap | Borrow Cap | Reserve Factor |
| ----- | ---------------- | --- | --- | ---------- | ----- | --- | ----------  | ---------- | --------- | ----- | ----- | -------------- |
| DAI   | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Yes | Yes | 75% | 80% |  5% | - | 2B | 0 | 10% |
| USDC  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Yes | Yes | 80% | 85% |  5% | - | 2B | 0 | 10% |
| USDT  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Only Isolation Mode | Yes | 75% | 80% |  5% | 5M | 2B | 0 | 10% |
| EURS  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Only Isolation Mode | No | 65% | 70% | 7.5% | 5M | 2B | 0 | 10% |
| AAVE  | <ul><li>eMode: 0 (default)</li></ul> | No  | No | Yes | No | 50% | 65% | 10% | - | 0 | 0 |  0% |
| LINK  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 70% | 75% | 7.5% | - | 0 | 0 | 20% |
| WBTC  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 70% | 75% | 10% | - | 0 | 0 | 20% |
| WETH  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 80% | 82.5% | 5% | - | 0 | 0 | 10% |

The reserve factor aka treasury collector contract can be found at [0xC3301b30f4EcBfd59dE0d74e89690C1a70C6f21B](https://arbiscan.io/address/0xc3301b30f4ecbfd59de0d74e89690c1a70c6f21b#code)

### Price Feed

The Arbitrum Chainlink oracles are available in the following [address repository](https://docs.chain.link/docs/arbitrum-price-feeds/).

| Pair Data Feed                                                            | Deviation Threshold | Oracle Contract Address                                                                                              |
| :-----------------------------------------------------------------------: | :-----------------: | :------------------------------------------------------------------------------------------------------------------: |
| [DAI/USD](https://data.chain.link/arbitrum/mainnet/stablecoins/dai-usd)   | 0.1%                | [0xc5c8e77b397e531b8ec06bfb0048328b30e9ecfb](https://arbiscan.io/address/0xc5c8e77b397e531b8ec06bfb0048328b30e9ecfb) |
| [EURS/USD](https://data.chain.link/arbitrum/mainnet/fiat/eur-usd)         | 0.1%                | [0xA14d53bC1F1c0F31B4aA3BD109344E5009051a84](https://arbiscan.io/address/0xA14d53bC1F1c0F31B4aA3BD109344E5009051a84) |
| [USDC/USD](https://data.chain.link/arbitrum/mainnet/stablecoins/usdc-usd) | 0.1%                | [0x50834f3163758fcc1df9973b6e91f0f0f0434ad3](https://arbiscan.io/address/0x50834f3163758fcc1df9973b6e91f0f0f0434ad3) |
| [USDT/USD](https://data.chain.link/arbitrum/mainnet/stablecoins/usdt-usd) | 0.1%                | [0x3f3f5df88dc9f13eac63df89ec16ef6e7e25dde7](https://arbiscan.io/address/0x3f3f5df88dc9f13eac63df89ec16ef6e7e25dde7) |
| [AAVE/USD](https://data.chain.link/arbitrum/mainnet/crypto-usd/aave-usd)  | 0.5%                | [0xad1d5344aade45f43e596773bcc4c423eabdd034](https://arbiscan.io/address/0xad1d5344aade45f43e596773bcc4c423eabdd034) |
| [LINK/USD](https://data.chain.link/arbitrum/mainnet/crypto-usd/link-usd)  | 0.2%                | [0x86e53cf1b870786351da77a57575e79cb55812cb](https://arbiscan.io/address/0x86e53cf1b870786351da77a57575e79cb55812cb) |
| [BTC/USD](https://data.chain.link/arbitrum/mainnet/crypto-usd/wbtc-usd)   | 0.05%               | [0x6ce185860a4963106506c203335a2910413708e9](https://arbiscan.io/address/0x6ce185860a4963106506c203335a2910413708e9) |
| [WETH/USD](https://data.chain.link/arbitrum/mainnet/crypto-usd/eth-usd)   | 0.05%               | [0x639fe6ab55c921f74e7fac1ee960c0b6293ba612](https://arbiscan.io/address/0x639fe6ab55c921f74e7fac1ee960c0b6293ba612) |



### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://arbiscan.io/address/0xba5ddd1f9d7f570dc94a51479a000e3bce967196) | [aArbAAVE](https://arbiscan.io/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sArbAAVE](https://arbiscan.io/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vArbAAVE](https://arbiscan.io/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |
| [DAI](https://arbiscan.io/address/0xda10009cbd5d07dd0cecc66161fc93d7c9000da1) | [aArbDAI](https://arbiscan.io/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sArbDAI](https://arbiscan.io/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vArbDAI](https://arbiscan.io/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| [InterestRateStrategy](https://arbiscan.io/address/0xA9F3C3caE095527061e6d270DBE163693e6fda9D#code) |
| [USDT](https://arbiscan.io/address/0xfd086bc7cd5c481dcc9c85ebe478a1c0b69fcbb9#code) | [aArbUSDT](https://arbiscan.io/address/0x6ab707aca953edaefbc4fd23ba73294241490620#code) | [sArbUSDT](https://arbiscan.io/address/0x70effc565db6eef7b927610155602d31b670e802#code) | [vArbUSDT](https://arbiscan.io/address/0xfb00ac187a8eb5afae4eace434f493eb62672df7#code) | [InterestRateStrategy](https://arbiscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [LINK](https://arbiscan.io/address/0xf97f4df75117a78c1a5a0dbb814af92458539fb4) | [aArbLINK](https://arbiscan.io/address/0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530) | [sArbLINK](https://arbiscan.io/address/0x89D976629b7055ff1ca02b927BA3e020F22A44e4#code) | [vArbLINK](https://arbiscan.io/address/0x953A573793604aF8d41F306FEb8274190dB4aE0e) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |
| [EURS](https://arbiscan.io/address/0xd22a58f79e9481d1a88e00c343885a588b34b68b) | [aArbEURS](https://arbiscan.io/address/0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97) | [sArbEURS](https://arbiscan.io/address/0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E#code) | [vArbEURS](https://arbiscan.io/address/0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8) | [InterestRateStrategy](https://arbiscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [USDC](https://arbiscan.io/address/0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8) | [aArbUSDC](https://arbiscan.io/address/0x625E7708f30cA75bfd92586e17077590C60eb4cD) | [sArbUSDC](https://arbiscan.io/address/0x307ffe186F84a3bc2613D1eA417A5737D69A7007#code) | [vArbUSDC](https://arbiscan.io/address/0xFCCf3cAbbe80101232d343252614b6A3eE81C989) | [InterestRateStrategy](https://arbiscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [WBTC](https://arbiscan.io/address/0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f) | [aArbWBTC](https://arbiscan.io/address/0x078f358208685046a11C85e8ad32895DED33A249) | [sArbWBTC](https://arbiscan.io/address/0x633b207Dd676331c413D4C013a6294B0FE47cD0e#code) | [vArbWBTC](https://arbiscan.io/address/0x92b42c66840C7AD907b4BF74879FF3eF7c529473) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |
| [WETH](https://arbiscan.io/address/0x82aF49447D8a07e3bd95BD0d56f35241523fBab1) | [aArbWETH](https://arbiscan.io/address/0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8) | [sArbWETH](https://arbiscan.io/address/0xD8Ad37849950903571df17049516a5CD4cbE55F6#code) | [vArbWETH](https://arbiscan.io/address/0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |

### Disclaimer
{% hint style=“info” %} Aave team do not hold any keys to the multisig controlling Aave V3 markets on Arbitrum {% endhint %}

During an initial bootstrapping phase, the Arbitrum deployment is controlled by a multisig (keys held by Arbitrum community) and follows the same security practices implemented during the governance transition period for Aave V1 and V2.