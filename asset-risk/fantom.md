---
description: Aave's deployment on the Fantom
---

# Fantom

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0x4a8ff1d3876390cde6b43fc93c0135de67fb6aa68a23e8eefeb770fe95735932), the Aave Protocol V3 has been deployed on Fantom. Fantom is an EVM-compatible L1 chain that offers fast finality, low transaction fees and has the [6th largest TVL according to DefiLlama](https://defillama.com/chains).

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
| WFTM  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 25% | 45% | 15% | - | 0 | 0 | 20% |
| CRV   | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 75% | 80% |  5% | - | 0 | 0 | 10% |
| SUSHI | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 20% | 45% | 10% | - | 0 | 0 | 20% |

The reserve factor aks treasury collector contract can be found at [0xc0F0cFBbd0382BcE3B93234E4BFb31b2aaBE36aD](https://ftmscan.com/address/0xc0F0cFBbd0382BcE3B93234E4BFb31b2aaBE36aD)

### Price Feed

Chainlink oracles are available on Fantom based on [👉🏻 address repository](https://docs.chain.link/docs/fantom-price-feeds/).

| Price Pair | Deviation Threshold | Chainlink Feed |
| :--------: | :-----------------: | :------------: |
|  FTM/USD   |      0.1%           | https://data.chain.link/fantom/mainnet/crypto-usd/ftm-usd |
|  AAVE/USD  |      0.5%           | https://data.chain.link/fantom/mainnet/crypto-usd/aave-usd |
|  DAI/USD   |      0.1%           | https://data.chain.link/fantom/mainnet/crypto-usd/dai-usd |
|  USDT/USD  |      0.1%           | https://data.chain.link/fantom/mainnet/crypto-usd/usdt-usd |
|  LINK/USD  |      0.5%           | https://data.chain.link/fantom/mainnet/crypto-usd/link-usd |
|  USDC/USD  |      0.1%           | https://data.chain.link/fantom/mainnet/crypto-usd/usdc-usd |
|  BTC/USD   |      0.1%           | https://data.chain.link/fantom/mainnet/crypto-usd/btc-usd |
|  ETH/USD   |      0.1%           | https://data.chain.link/fantom/mainnet/crypto-usd/eth-usd |
|  CRV/USD   |      0.5%           | https://data.chain.link/fantom/mainnet/crypto-usd/crv-usd |
|  SUSHI/USD |      0.5%           | https://data.chain.link/fantom/mainnet/crypto-usd/sushi-usd |

### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://ftmscan.com/address/0x6a07a792ab2965c72a5b8088d3a069a7ac3a993b) | [aFanAAVE](https://ftmscan.com/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sFanAAVE](https://ftmscan.com/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vFanAAVE](https://ftmscan.com/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) | [InterestRateStrategy](https://ftmscan.com/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521#code) |
| [DAI](https://ftmscan.com/address/0x8D11eC38a3EB5E956B052f67Da8Bdc9bef8Abf3E) | [aFanDAI](https://ftmscan.com/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sFanDAI](https://ftmscan.com/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vFanDAI](https://ftmscan.com/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| [InterestRateStrategy](https://ftmscan.com/address/0xa9f3c3cae095527061e6d270dbe163693e6fda9d#code) |
| [USDT](https://ftmscan.com/address/0x049d68029688eabf473097a2fc38ef61633a3c7a#code) | [aFanUSDT](https://ftmscan.com/address/0x6ab707Aca953eDAeFBc4fD23bA73294241490620#code) | [sFanUSDT](https://ftmscan.com/address/0x70eFfc565DB6EEf7B927610155602d31b670e802#code) | [vFanUSDT](https://ftmscan.com/address/0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7#code) | [InterestRateStrategy](https://ftmscan.com/address/0xf4a0039F2d4a2EaD5216AbB6Ae4C4C3AA2dB9b82#code) |
| [LINK](https://ftmscan.com/address/0xb3654dc3d10ea7645f8319668e8f54d2574fbdc8) | [aFanLINK](https://ftmscan.com/address/0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530) | [sFanLINK](https://ftmscan.com/address/0x89D976629b7055ff1ca02b927BA3e020F22A44e4#code) | [vFanLINK](https://ftmscan.com/address/0x953A573793604aF8d41F306FEb8274190dB4aE0e) | [InterestRateStrategy](https://ftmscan.com/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521#code) |
| [WFTM](https://ftmscan.com/address/0x21be370d5312f44cb42ce377bc9b8a0cef1a4c83) | [aFanWFTM](https://ftmscan.com/address/0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97) | [sFanWFTM](https://ftmscan.com/address/0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E#code) | [vFanWFTM](https://ftmscan.com/address/0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8) | [InterestRateStrategy](https://ftmscan.com/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521#code) |
| [USDC](https://ftmscan.com/address/0x04068da6c83afcfa0e13ba15a6696662335d5b75) | [aFanUSDC](https://ftmscan.com/address/0x625E7708f30cA75bfd92586e17077590C60eb4cD) | [sFanUSDC](https://ftmscan.com/address/0x307ffe186F84a3bc2613D1eA417A5737D69A7007#code) | [vFanUSDC](https://ftmscan.com/address/0xFCCf3cAbbe80101232d343252614b6A3eE81C989) | [InterestRateStrategy](https://ftmscan.com/address/0xf4a0039F2d4a2EaD5216AbB6Ae4C4C3AA2dB9b82#code) |
| [WBTC](https://ftmscan.com/address/0x321162cd933e2be498cd2267a90534a804051b11) | [aFanWBTC](https://ftmscan.com/address/0x078f358208685046a11C85e8ad32895DED33A249) | [sFanWBTC](https://ftmscan.com/address/0x633b207Dd676331c413D4C013a6294B0FE47cD0e#code) | [vFanWBTC](https://ftmscan.com/address/0x92b42c66840C7AD907b4BF74879FF3eF7c529473) | [InterestRateStrategy](https://ftmscan.com/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521#code) |
| [WETH](https://ftmscan.com/address/0x74b23882a30290451a17c44f4f05243b6b58c76d) | [aFanWETH](https://ftmscan.com/address/0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8) | [sFanWETH](https://ftmscan.com/address/0xD8Ad37849950903571df17049516a5CD4cbE55F6#code) | [vFanWETH](https://ftmscan.com/address/0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351) | [InterestRateStrategy](https://ftmscan.com/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521#code) |
| [CRV](https://ftmscan.com/address/0x1e4f97b9f9f913c46f1632781732927b9019c68b) | [aFanCRV](https://ftmscan.com/address/0x513c7e3a9c69ca3e22550ef58ac1c0088e918fff) | [sFanCRV](https://ftmscan.com/address/0x08cb71192985e936c7cd166a8b268035e400c3c3#code) | [vFanCRV](https://ftmscan.com/address/0x77ca01483f379e58174739308945f044e1a764dc) | [InterestRateStrategy](https://ftmscan.com/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521#code) |
| [SUSHI](https://ftmscan.com/address/0xae75a438b2e0cb8bb01ec1e1e376de11d44477cc) | [aFanSUSHI](https://ftmscan.com/address/0xc45a479877e1e9dfe9fcd4056c699575a1045daa) | [sFanSUSHI](https://ftmscan.com/address/0x78246294a4c6fbf614ed73ccc9f8b875ca8ee841#code) | [vFanSUSHI](https://ftmscan.com/address/0x34e2ed44ef7466d5f9e0b782b5c08b57475e7907) | [InterestRateStrategy](https://ftmscan.com/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521#code) |

### Disclaimer

During an initial bootstrapping phase, the Fantom deployment is controlled by a multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.
