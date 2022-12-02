---
description: Aave's deployment on the Harmony
---

# Harmony

[Snapshot to deploy V2 on Harmony](https://snapshot.org/#/aave.eth/proposal/QmYYBedL9aRFdC5DUgjN3QMoYxvJhAUBb2sEyhFuVQZbLG) passed with a success. In anticipation of the Aave Protocol V3 launch, the Aave Protocol v2 deployment on Harmony was dropped in favour of the Aave Protocol V3 deployment.

Harmony is a sharded proof-of-stake blockchain, operated by over 100 external validators. It is fully EVM and Ethereum tooling compatible. Read more about [👉🏻 Harmony](https://www.harmony.one/)

Due to the Horizon bridge exploit, certain assets on the Harmony network are not at parity with Ethereum, which affects the Aave V3 Harmony market. Per the community, the [Harmony market has been frozen](https://snapshot.org/#/aave.eth/proposal/0x81a78109941e5e0ac6cb5ebf82597c839c20ad6821a8c3ff063dba39032533d4).

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
| WONE  | <ul><li>eMode: 0 (default)</li></ul> | Yes | No | Yes | No | 25% | 45% | 15% | - | 0 | 0 | 20% |

The reserve factor aka treasury collector contract can be found at [0xeaC16519923774Fd7723d3D5E442a1e2E46BA962](https://explorer.harmony.one/address/0xeac16519923774fd7723d3d5e442a1e2e46ba962)

### Price Feed

Chainlink oracles are available on Harmony based on [👉🏻 address repository](https://docs.chain.link/docs/harmony-price-feeds/).

### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://explorer.harmony.one/address/0xcF323Aad9E522B93F11c352CaA519Ad0E14eB40F) | [aHarAAVE](https://explorer.harmony.one/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sHarAAVE](https://explorer.harmony.one/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vHarAAVE](https://explorer.harmony.one/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) | [InterestRateStrategy](https://explorer.harmony.one/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521) |
| [DAI](https://explorer.harmony.one/address/0xEf977d2f931C1978Db5F6747666fa1eACB0d0339) | [aHarDAI](https://explorer.harmony.one/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sHarDAI](https://explorer.harmony.one/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vHarDAI](https://explorer.harmony.one/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| [InterestRateStrategy](https://explorer.harmony.one/address/0xa9f3c3cae095527061e6d270dbe163693e6fda9d) |
| [USDT](https://explorer.harmony.one/address/0x3C2B8Be99c50593081EAA2A724F0B8285F5aba8f) | [aHarUSDT](https://explorer.harmony.one/address/0x6ab707Aca953eDAeFBc4fD23bA73294241490620) | [sHarUSDT](https://explorer.harmony.one/address/0x70eFfc565DB6EEf7B927610155602d31b670e802) | [vHarUSDT](https://explorer.harmony.one/address/0xfb00AC187a8Eb5AFAE4eACE434F493Eb62672df7) | [InterestRateStrategy](https://explorer.harmony.one/address/0xf4a0039F2d4a2EaD5216AbB6Ae4C4C3AA2dB9b82) |
| [LINK](https://explorer.harmony.one/address/0x218532a12a389a4a92fC0C5Fb22901D1c19198aA) | [aHarLINK](https://explorer.harmony.one/address/0x191c10Aa4AF7C30e871E70C95dB0E4eb77237530) | [sHarLINK](https://explorer.harmony.one/address/0x89D976629b7055ff1ca02b927BA3e020F22A44e4) | [vHarLINK](https://explorer.harmony.one/address/0x953A573793604aF8d41F306FEb8274190dB4aE0e) | [InterestRateStrategy](https://explorer.harmony.one/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521) |
| [WONE](https://explorer.harmony.one/address/0xcF664087a5bB0237a0BAd6742852ec6c8d69A27a) | [aHarWONE](https://explorer.harmony.one/address/0x6d80113e533a2C0fe82EaBD35f1875DcEA89Ea97) | [sHarWONE](https://explorer.harmony.one/address/0xF15F26710c827DDe8ACBA678682F3Ce24f2Fb56E) | [vHarWONE](https://explorer.harmony.one/address/0x4a1c3aD6Ed28a636ee1751C69071f6be75DEb8B8) | [InterestRateStrategy](https://explorer.harmony.one/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521) |
| [USDC](https://explorer.harmony.one/address/0x985458E523dB3d53125813eD68c274899e9DfAb4) | [aHarUSDC](https://explorer.harmony.one/address/0x625E7708f30cA75bfd92586e17077590C60eb4cD) | [sHarUSDC](https://explorer.harmony.one/address/0x307ffe186F84a3bc2613D1eA417A5737D69A7007) | [vHarUSDC](https://explorer.harmony.one/address/0xFCCf3cAbbe80101232d343252614b6A3eE81C989) | [InterestRateStrategy](https://explorer.harmony.one/address/0xf4a0039F2d4a2EaD5216AbB6Ae4C4C3AA2dB9b82) |
| [WBTC](https://explorer.harmony.one/address/0x3095c7557bCb296ccc6e363DE01b760bA031F2d9) | [aHarWBTC](https://explorer.harmony.one/address/0x078f358208685046a11C85e8ad32895DED33A249) | [sHarWBTC](https://explorer.harmony.one/address/0x633b207Dd676331c413D4C013a6294B0FE47cD0e) | [vHarWBTC](https://explorer.harmony.one/address/0x92b42c66840C7AD907b4BF74879FF3eF7c529473) | [InterestRateStrategy](https://explorer.harmony.one/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521) |
| [WETH](https://explorer.harmony.one/address/0x6983D1E6DEf3690C4d616b13597A09e6193EA013) | [aHarWETH](https://explorer.harmony.one/address/0xe50fA9b3c56FfB159cB0FCA61F5c9D750e8128c8) | [sHarWETH](https://explorer.harmony.one/address/0xD8Ad37849950903571df17049516a5CD4cbE55F6) | [vHarWETH](https://explorer.harmony.one/address/0x0c84331e39d6658Cd6e6b9ba04736cC4c4734351) | [InterestRateStrategy](https://explorer.harmony.one/address/0x4aa694e6c06d6162d95be98a2df6a521d5a7b521) |

### Disclaimer
{% hint style=“info” %} Aave team do not hold any keys to the multisig controlling Aave V3 markets on Harmony {% endhint %}
During an initial bootstrapping phase, the Harmony deployment is controlled by a multisig (keys held by Harmony community) and follows the same security practices implemented during the governance transition period for Aave V1 and V2.
