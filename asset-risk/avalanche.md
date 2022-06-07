---
description: Aave's deployment on the Avalanche C-Chain
---

# Avalanche

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0x0f682decaf1657b36110beb6914a89dc16b305b163d7a75c22848f059ee9bd24), V3 of the Aave Protocol has been deployed on Avalanche. Avalanche is one of the fastest smart contracts platforms in the blockchain industry, as measured by time-to-finality, and has the most validators securing its activity out of any proof-of-stake protocol. Avalanche’s C-Chain is an instance of the EVM running with Avalanche’s consensus.

### Risk Parameters

| Asset | eMode Params     | Borrow | Siloed | Collateral | Borrow Isolation | LTV | Liq. Thresh | Liq. Bonus | Debt Ceil | Supply Cap | Borrow Cap | Reserve Factor |
| ----- | ---------------- | --- | --- | ---------- | ----- | --- | ----------  | ---------- | --------- | ----- | ----- | -------------- |
| DAI   | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Yes | Yes | 75% | 80% |  5% | - | 2B | 0 | 10% |
| USDC  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Yes | Yes | 82.5% | 85% |  4% | - | 2B | 0 | 10% |
| USDT  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Only Isolation Mode | Yes | 75% | 80% |  5% | 5M | 2B | 0 | 10% |
| AAVE  | <ul><li>eMode: 0 (default)</li></ul> | No  | No | Yes | No | 60% | 70% | 7.5% | - | 0 | 0 |  0% |
| LINK  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 50% | 65% | 7.5% | - | 0 | 0 | 20% |
| WBTC  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 70% | 75% | 6.5% | - | 0 | 0 | 20% |
| WETH  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 80% | 82.5% | 5% | - | 0 | 0 | 10% |
| WAVAX | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 65% | 70% | 10% | - | 0 | 0 | 20% |

The reserve factor aka treasury collector contract can be found at [0xaCbE7d574EF8dC39435577eb638167Aca74F79f0](https://snowtrace.io/address/0xaCbE7d574EF8dC39435577eb638167Aca74F79f0)

### Price Feed

Chainlink oracles are available on Avalanche based on [this address repository](https://docs.chain.link/docs/avalanche-price-feeds/).

| Price Pair | Deviation Threshold | Chainlink Feed |
| :--------: | :-----------------: | :------------: |
|  AVAX/USD  |      0.1%           | https://data.chain.link/avalanche/mainnet/crypto-usd/avax-usd |
|  AAVE/USD  |      0.5%           | https://data.chain.link/avalanche/mainnet/crypto-usd/aave-usd |
|  DAI/USD   |      0.5%           | https://data.chain.link/avalanche/mainnet/crypto-usd/dai-usd |
|  USDT/USD  |      0.1%           | https://data.chain.link/avalanche/mainnet/crypto-usd/usdt-usd |
|  LINK/USD  |      0.5%           | https://data.chain.link/avalanche/mainnet/crypto-usd/link-usd |
|  USDC/USD  |      0.5%           | https://data.chain.link/avalanche/mainnet/crypto-usd/usdc-usd |
|  BTC/USD   |      0.1%           | https://data.chain.link/avalanche/mainnet/crypto-usd/btc-usd |
|  ETH/USD   |      0.1%           | https://data.chain.link/avalanche/mainnet/crypto-usd/eth-usd |

### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://snowtrace.io/address/0x63a72806098bd3d9520cc43356dd78afe5d386d9) | [aAvaAAVE](https://snowtrace.io/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sAvaAAVE](https://snowtrace.io/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vAvaAAVE](https://snowtrace.io/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) | [InterestRateStrategy](https://snowtrace.io/address/0x79a906e8c998d2fb5C5D66d23c4c5416Fe0168D6#code) |
| [DAI](https://snowtrace.io/address/0xd586E7F844cEa2F87f50152665BCbc2C279D8d70) | [aAvaDAI](https://snowtrace.io/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sAvaDAI](https://snowtrace.io/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vAvaDAI](https://snowtrace.io/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| [InterestRateStrategy](https://snowtrace.io/address/0xfab05a6aF585da2F96e21452F91E812452996BD3#code) |
| [USDT](https://snowtrace.io/address/0x9702230A8Ea53601f5cD2dc00fDBc13d4dF4A8c7#code) | [aAvaUSDT](https://snowtrace.io/address/0x6ab707Aca953eDAeFBc4fD23bA73294241490620#code) | [sAvaUSDT](https://snowtrace.io/address/0x70eFfc565DB6EEf7B927610155602d31b670e802#code) | [vAvaUSDT](https://snowtrace.io/address/0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7#code) | [InterestRateStrategy](https://snowtrace.io/address/0xf4a0039F2d4a2EaD5216AbB6Ae4C4C3AA2dB9b82#code) |
| [LINK](https://snowtrace.io/address/0x5947BB275c521040051D82396192181b413227A3) | [aAvaLINK](https://snowtrace.io/address/0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530) | [sAvaLINK](https://snowtrace.io/address/0x89D976629b7055ff1ca02b927BA3e020F22A44e4#code) | [vAvaLINK](https://snowtrace.io/address/0x953A573793604aF8d41F306FEb8274190dB4aE0e) | [InterestRateStrategy](https://snowtrace.io/address/0x79a906e8c998d2fb5C5D66d23c4c5416Fe0168D6#code) |
| [WAVAX](https://snowtrace.io/address/0xB31f66AA3C1e785363F0875A1B74E27b85FD66c7) | [aAvaWAVAX](https://snowtrace.io/address/0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97) | [sAvaWAVAX](https://snowtrace.io/address/0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E#code) | [vAvaWAVAX](https://snowtrace.io/address/0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8) | [InterestRateStrategy](https://snowtrace.io/address/0x79a906e8c998d2fb5C5D66d23c4c5416Fe0168D6#code) |
| [USDC](https://snowtrace.io/address/0xB97EF9Ef8734C71904D8002F8b6Bc66Dd9c48a6E) | [aAvaUSDC](https://snowtrace.io/address/0x625E7708f30cA75bfd92586e17077590C60eb4cD) | [sAvaUSDC](https://snowtrace.io/address/0x307ffe186F84a3bc2613D1eA417A5737D69A7007#code) | [vAvaUSDC](https://snowtrace.io/address/0xFCCf3cAbbe80101232d343252614b6A3eE81C989) | [InterestRateStrategy](https://snowtrace.io/address/0xf4a0039F2d4a2EaD5216AbB6Ae4C4C3AA2dB9b82#code) |
| [WBTC](https://snowtrace.io/address/0x50b7545627a5162F82A992c33b87aDc75187B218) | [aAvaWBTC](https://snowtrace.io/address/0x078f358208685046a11C85e8ad32895DED33A249) | [sAvaWBTC](https://snowtrace.io/address/0x633b207Dd676331c413D4C013a6294B0FE47cD0e#code) | [vAvaWBTC](https://snowtrace.io/address/0x92b42c66840C7AD907b4BF74879FF3eF7c529473) | [InterestRateStrategy](https://snowtrace.io/address/0x79a906e8c998d2fb5C5D66d23c4c5416Fe0168D6#code) |
| [WETH](https://snowtrace.io/address/0x49D5c2BdFfac6CE2BFdB6640F4F80f226bc10bAB) | [aAvaWETH](https://snowtrace.io/address/0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8) | [sAvaWETH](https://snowtrace.io/address/0xD8Ad37849950903571df17049516a5CD4cbE55F6#code) | [vAvaWETH](https://snowtrace.io/address/0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351) | [InterestRateStrategy](https://snowtrace.io/address/0x79a906e8c998d2fb5C5D66d23c4c5416Fe0168D6#code) |

### Disclaimer

{% hint style=“info” %} Aave team do not hold any keys to the multisig controlling Aave V3 markets on Avalanche {% endhint %}

During an initial bootstrapping phase, the Avalanche deployment is controlled by a multisig (keys held by Avalanche community) and follows the same security practices implemented during the governance transition period for Aave V1 and V2.
