---
description: Aave's Market on the Polygon sidechain
---

# Polygon
The community’s first exploration of new frontiers (i.e., networks) for the Aave Protocol was V2 market launch on Polygon. A scalable sidechain of Ethereum that allows for fast and low fee transactions with a nascent ecosystem of applications including community favourite [Aavegotchi](https://aavegotchi.com), decentralised exchange [Quickswap](https://quickswap.exchange/#/swap) as well as [Chainlink](https://chain.link) oracles.

Nearly a hundred validators secure Polygon's Proof-of-Stake algorithm with back ups occurring every 30 minutes on the Ethereum blockchain.

Following huge success of V2 markets, V3 of the Aave Protocol has been deployed on Polygon.

### Risk Parameters

| Asset | eMode Params     | Borrow | Siloed | Collateral | Borrow Isolation | LTV | Liq. Thresh | Liq. Bonus | Debt Ceil | Supply Cap | Borrow Cap | Reserve Factor |
| ----- | ---------------- | --- | --- | ---------- | ----- | --- | ----------  | ---------- | --------- | ----- | ----- | -------------- |
| DAI   | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Yes | Yes | 75% | 80% |  5% | - | 2B | 0 | 10% |
| USDC  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Yes | Yes | 82.5% | 85% |  4% | - | 2B | 0 | 10% |
| USDT  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Only Isolation Mode | Yes | 75% | 80% |  5% | 5M | 2B | 0 | 10% |
| EURS  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | Only Isolation Mode | No | 65% | 70% | 7.5% | 5M | 2B | 0 | 10% |
| agEUR  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | No | No | 0% | 0% | 0% | - | - | - | 20% |
| jEUR  | <ul><li>category: 1 </li><li>LTV: 97%</li><li>liq. Thresh: 97.5</li><li>Liq. Bonus: 2%</li></ul> | Yes | No | No | No | 0% | 0% | 0% | - | - | - | 20% |
| AAVE  | <ul><li>eMode: 0 (default)</li></ul> | No  | No | Yes | No | 60% | 70% | 7.5% | - | 0 | 0 |  0% |
| LINK  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 50% | 65% | 7.5% | - | 0 | 0 | 20% |
| WBTC  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 70% | 75% | 6.5% | - | 0 | 0 | 20% |
| WETH  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 80% | 82.5% | 5% | - | 0 | 0 | 10% |
| WMATIC | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 65% | 70% | 10% | - | 0 | 0 | 20% |
| CRV   | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 75% | 80% |  5% | - | 0 | 0 | 10% |
| SUSHI | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 20% | 45% | 10% | - | 0 | 0 | 20% |
| GHST | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 25% | 45% | 15% | - | 0 | 0 | 20% |
| DPI | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 20% | 45% | 10% | - | 0 | 0 | 20% |
| BAL | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 20% | 45% | 10% | - | 0 | 0 | 20% |

The reserve factor collector contract can be found at [0x73D435AFc15e35A9aC63B2a81B5AA54f974eadFe](https://polygonscan.com/address/0x73D435AFc15e35A9aC63B2a81B5AA54f974eadFe)

### Price Feed

Chainlink oracles are available on Polygon based on [this address repository](https://docs.chain.link/docs/matic-addresses/).

| Price Pair | Deviation Threshold | Chainlink Feed |
| :--------: | :-----------------: | :------------: |
|  MATIC/USD |      0.1%           | https://data.chain.link/polygon/mainnet/crypto-usd/matic-usd |
|  AAVE/USD  |      0.5%           | https://data.chain.link/polygon/mainnet/crypto-usd/aave-usd |
|  DAI/USD   |      0.1%           | https://data.chain.link/polygon/mainnet/crypto-usd/dai-usd |
|  USDT/USD  |      0.1%           | https://data.chain.link/polygon/mainnet/crypto-usd/usdt-usd |
|  LINK/USD  |      0.5%           | https://data.chain.link/polygon/mainnet/crypto-usd/link-usd |
|  USDC/USD  |      0.1%           | https://data.chain.link/polygon/mainnet/crypto-usd/usdc-usd |
|  AGEUR/USD |      0.1%           | https://data.chain.link/polygon/mainnet/crypto-usd/ageur-usd |
|  BTC/USD   |      0.1%           | https://data.chain.link/polygon/mainnet/crypto-usd/btc-usd |
|  ETH/USD   |      0%           | https://data.chain.link/polygon/mainnet/crypto-usd/eth-usd |
|  CRV/USD   |      0.5%           | https://data.chain.link/polygon/mainnet/crypto-usd/crv-usd |
|  SUSHI/USD |      0.5%           | https://data.chain.link/polygon/mainnet/crypto-usd/sushi-usd |

### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://polygonscan.com/address/0xd6df932a45c0f255f85145f286ea0b292b21c90b) | [aPolAAVE](https://polygonscan.com/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sPolAAVE](https://polygonscan.com/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vPolAAVE](https://polygonscan.com/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [DAI](https://polygonscan.com/address/0x8f3cf7ad23cd3cadbd9735aff958023239c6a063) | [aPolDAI](https://polygonscan.com/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sPolDAI](https://polygonscan.com/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vPolDAI](https://polygonscan.com/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| [InterestRateStrategy](https://polygonscan.com/address/0xa9f3c3cae095527061e6d270dbe163693e6fda9d#code) |
| [USDT](https://polygonscan.com/address/0xc2132d05d31c914a87c6611c10748aeb04b58e8f#code) | [aPolUSDT](https://polygonscan.com/address/0x6ab707Aca953eDAeFBc4fD23bA73294241490620#code) | [sPolUSDT](https://polygonscan.com/address/0x70eFfc565DB6EEf7B927610155602d31b670e802#code) | [vPolUSDT](https://polygonscan.com/address/0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7#code) | [InterestRateStrategy](https://polygonscan.com/address/0x41b66b4b6b4c9dab039d96528d1b88f7baf8c5a4#code) |
| [LINK](https://polygonscan.com/address/0x53e0bca35ec356bd5dddfebbd1fc0fd03fabad39) | [aPolLINK](https://polygonscan.com/address/0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530) | [sPolLINK](https://polygonscan.com/address/0x89D976629b7055ff1ca02b927BA3e020F22A44e4#code) | [vPolLINK](https://polygonscan.com/address/0x953A573793604aF8d41F306FEb8274190dB4aE0e) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [WMATIC](https://polygonscan.com/address/0x0d500b1d8e8ef31e21c99d1db9a6444d3adf1270) | [aPolWMATIC](https://polygonscan.com/address/0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97) | [sPolWMATIC](https://polygonscan.com/address/0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E#code) | [vPolWMATIC](https://polygonscan.com/address/0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [USDC](https://polygonscan.com/address/0x2791bca1f2de4661ed88a30c99a7a9449aa84174) | [aPolUSDC](https://polygonscan.com/address/0x625E7708f30cA75bfd92586e17077590C60eb4cD) | [sPolUSDC](https://polygonscan.com/address/0x307ffe186F84a3bc2613D1eA417A5737D69A7007#code) | [vPolUSDC](https://polygonscan.com/address/0xFCCf3cAbbe80101232d343252614b6A3eE81C989) | [InterestRateStrategy](https://polygonscan.com/address/0x41b66b4b6b4c9dab039d96528d1b88f7baf8c5a4#code) |
| [AGEUR](https://polygonscan.com/address/0xe0b52e49357fd4daf2c15e02058dce6bc0057db4) | [aPolAGEUR](https://polygonscan.com/address/0x8437d7c167dfb82ed4cb79cd44b7a32a1dd95c77) | [sPolAGEUR](https://polygonscan.com/address/0x40b4baecc69b882e8804f9286b12228c27f8c9bf#code) | [vPolAGEUR](https://polygonscan.com/address/0x3ca5fa07689f266e907439afd1fbb59c44fe12f6) | [InterestRateStrategy](https://polygonscan.com/address/0x41b66b4b6b4c9dab039d96528d1b88f7baf8c5a4#code) |
| [EURS](https://polygonscan.com/address/0xe111178a87a3bff0c8d18decba5798827539ae99) | [aPolEURS](https://polygonscan.com/address/0x38d693ce1df5aadf7bc62595a37d667ad57922e5) | [sPolEURS](https://polygonscan.com/address/0x8a9fde6925a839f6b1932d16b36ac026f8d3fbdb#code) | [vPolEURS](https://polygonscan.com/address/0x5d557b07776d12967914379c71a1310e917c7555) | [InterestRateStrategy](https://polygonscan.com/address/0x41b66b4b6b4c9dab039d96528d1b88f7baf8c5a4#code) |
| [WBTC](https://polygonscan.com/address/0x1bfd67037b42cf73acf2047067bd4f2c47d9bfd6) | [aPolWBTC](https://polygonscan.com/address/0x078f358208685046a11C85e8ad32895DED33A249) | [sPolWBTC](https://polygonscan.com/address/0x633b207Dd676331c413D4C013a6294B0FE47cD0e#code) | [vPolWBTC](https://polygonscan.com/address/0x92b42c66840C7AD907b4BF74879FF3eF7c529473) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [WETH](https://polygonscan.com/address/0x7ceb23fd6bc0add59e62ac25578270cff1b9f619) | [aPolWETH](https://polygonscan.com/address/0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8) | [sPolWETH](https://polygonscan.com/address/0xD8Ad37849950903571df17049516a5CD4cbE55F6#code) | [vPolWETH](https://polygonscan.com/address/0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [CRV](https://polygonscan.com/address/0x172370d5cd63279efa6d502dab29171933a610af) | [aPolCRV](https://polygonscan.com/address/0x513c7e3a9c69ca3e22550ef58ac1c0088e918fff) | [sPolCRV](https://polygonscan.com/address/0x08cb71192985e936c7cd166a8b268035e400c3c3#code) | [vPolCRV](https://polygonscan.com/address/0x77ca01483f379e58174739308945f044e1a764dc) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [SUSHI](https://polygonscan.com/address/0x0b3f868e0be5597d5db7feb59e1cadbb0fdda50a) | [aPolSUSHI](https://polygonscan.com/address/0xc45a479877e1e9dfe9fcd4056c699575a1045daa) | [sPolSUSHI](https://polygonscan.com/address/0x78246294a4c6fbf614ed73ccc9f8b875ca8ee841#code) | [vPolSUSHI](https://polygonscan.com/address/0x34e2ed44ef7466d5f9e0b782b5c08b57475e7907) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [GHST](https://polygonscan.com/address/0x385eeac5cb85a38a9a07a70c73e0a3271cfb54a7) | [aPolGHST](https://polygonscan.com/address/0x8eb270e296023e9d92081fdf967ddd7878724424) | [sPolGHST](https://polygonscan.com/address/0x3ef10dff4928279c004308ebadc4db8b7620d6fc#code) | [vPolGHST](https://polygonscan.com/address/0xce186f6cccb0c955445bb9d10c59cae488fea559) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [JEUR](https://polygonscan.com/address/0x4e3decbb3645551b8a19f0ea1678079fcb33fb4c) | [aPolJEUR](https://polygonscan.com/address/0x6533afac2e7bccb20dca161449a13a32d391fb00) | [sPolJEUR](https://polygonscan.com/address/0x6b4b37618d85db2a7b469983c888040f7f05ea3d#code) | [vPolJEUR](https://polygonscan.com/address/0x44705f578135cc5d703b4c9c122528c73eb87145) | [InterestRateStrategy](https://polygonscan.com/address/0x41b66b4b6b4c9dab039d96528d1b88f7baf8c5a4#code) |
| [DPI](https://polygonscan.com/address/0x85955046df4668e1dd369d2de9f3aeb98dd2a369) | [aPolDPI](https://polygonscan.com/address/0x724dc807b04555b71ed48a6896b6f41593b8c637) | [sPolDPI](https://polygonscan.com/address/0xdc1fad70953bb3918592b6fcc374fe05f5811b6a#code) | [vPolDPI](https://polygonscan.com/address/0xf611aeb5013fd2c0511c9cd55c7dc5c1140741a6) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |
| [BAL](https://polygonscan.com/address/0x9a71012b13ca4d3d0cdc72a177df3ef03b0e76a3) | [aPolBAL](https://polygonscan.com/address/0x8ffdf2de812095b1d19cb146e4c004587c0a0692) | [sPolBAL](https://polygonscan.com/address/0xa5e408678469d23efdb7694b1b0a85bb0669e8bd#code) | [vPolBAL](https://polygonscan.com/address/0xa8669021776bc142dfca87c21b4a52595bcbb40a) | [InterestRateStrategy](https://polygonscan.com/address/0x03733f4e008d36f2e37f0080ff1c8df756622e6f#code) |

### Cross chain governance

Both Aave V2 and V3 markets are controlled via the Aave Governance via Aave Cross Chain Governance bridge.
