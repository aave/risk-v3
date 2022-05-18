---
description: Aave's deployment on the Arbitrum
---

# Arbitrum

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0x7c6261b04115e79c63cffb1602295836df36883fc76fc899bce3345c2beaeba3), the Aave Protocol V3 has been deployed on Arbitrum One.Arbitrum is the leading Ethereum Rollup, with hundreds of live apps including most top Ethereum apps and infrastructure. Arbitrum's TVL accounts for 47.8% of TVL across all Ethereum L2s tracked by L2Beat. You can read more [👉🏻 here](https://portal.arbitrum.one)


### Risk Parameters

| Asset | Borrowing | Collateral | Loan to Value | Liquidation threshold | Liquidation penalty | Reserve Factor |
| ----- | --------- | ---------- | ------------- | --------------------- | ------------------- | -------------- |
| AAVE  | No        | Yes        | 40%           | 65%                   | 10%                 |                |
| DAI   | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| LINK  |
| SUSHI | Yes       | No         |               |                       |                     | 10%            |
| USDC  | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| USDT  | Yes       | No         |               |                       |                     | 10%            |
| WBTC  | Yes       | Yes        | 60%           | 75%                   | 5%                  | 20%            |
| WETH  | Yes       | Yes        | 80%           | 82.5%                 | 5%                  | 10%            |
| WFTM  | Yes       | Yes        | 50%           | 65%                   | 10%                 | 15%            |

The reserve factor aks treasury collector contract can be found at [0xC3301b30f4EcBfd59dE0d74e89690C1a70C6f21B](https://arbiscan.io/address/0xc3301b30f4ecbfd59de0d74e89690c1a70c6f21b#code)

### Price Feed

Chainlink oracles are available on Arbitrum based on [👉🏻 address repository](https://docs.chain.link/docs/arbitrum-price-feeds/).

### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://arbiscan.io/address/0xba5ddd1f9d7f570dc94a51479a000e3bce967196) | [aArbAAVE](https://arbiscan.io/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sArbAAVE](https://arbiscan.io/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vArbAAVE](https://arbiscan.io/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |
| [DAI](https://arbiscan.io/address/0xda10009cbd5d07dd0cecc66161fc93d7c9000da1) | [aArbDAI](https://arbiscan.io/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sArbDAI](https://arbiscan.io/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vArbDAI](https://arbiscan.io/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| [InterestRateStrategy](https://arbiscan.io/address/0xA9F3C3caE095527061e6d270DBE163693e6fda9D#code) |
| [USDT](https://arbiscan.io/address/0xfd086bc7cd5c481dcc9c85ebe478a1c0b69fcbb9#code) | [aArbUSDT]() | [sArbUSDT]() | [vArbUSDT]() | [rateStrategyStableOne](https://arbiscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [LINK](https://arbiscan.io/address/0xf97f4df75117a78c1a5a0dbb814af92458539fb4) | [aArbLINK](https://arbiscan.io/address/0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530) | [sArbLINK](https://arbiscan.io/address/0x89D976629b7055ff1ca02b927BA3e020F22A44e4#code) | [vArbLINK](https://arbiscan.io/address/0x953A573793604aF8d41F306FEb8274190dB4aE0e) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |
| [EURS](https://arbiscan.io/address/0xd22a58f79e9481d1a88e00c343885a588b34b68b) | [aArbEURS](https://arbiscan.io/address/0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97) | [sArbEURS](https://arbiscan.io/address/0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E#code) | [vArbEURS](https://arbiscan.io/address/0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8) | [InterestRateStrategy](https://arbiscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [USDC](https://arbiscan.io/address/0xFF970A61A04b1cA14834A43f5dE4533eBDDB5CC8) | [aArbUSDC](https://arbiscan.io/address/0x625E7708f30cA75bfd92586e17077590C60eb4cD) | [sArbUSDC](https://arbiscan.io/address/0x307ffe186F84a3bc2613D1eA417A5737D69A7007#code) | [vArbUSDC](https://arbiscan.io/address/0xFCCf3cAbbe80101232d343252614b6A3eE81C989) | [InterestRateStrategy](https://arbiscan.io/address/0x41B66b4b6b4c9dab039d96528D1b88f7BAF8C5A4#code) |
| [WBTC](https://arbiscan.io/address/0x2f2a2543B76A4166549F7aaB2e75Bef0aefC5B0f) | [aArbWBTC](https://arbiscan.io/address/0x078f358208685046a11C85e8ad32895DED33A249) | [sArbWBTC](https://arbiscan.io/address/0x633b207Dd676331c413D4C013a6294B0FE47cD0e#code) | [vArbWBTC](https://arbiscan.io/address/0x92b42c66840C7AD907b4BF74879FF3eF7c529473) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |
| [WETH](https://arbiscan.io/address/0x82aF49447D8a07e3bd95BD0d56f35241523fBab1) | [aArbWETH](https://arbiscan.io/address/0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8) | [sArbWETH](https://arbiscan.io/address/0xD8Ad37849950903571df17049516a5CD4cbE55F6#code) | [vArbWETH](https://arbiscan.io/address/0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351) | [InterestRateStrategy](https://arbiscan.io/address/0x9b34E3e183c9b0d1a08fF57a8fb59c821616295f#code) |

### Disclaimer

During an initial bootstrapping phase, the Arbitrum deployment is controlled by a multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.

