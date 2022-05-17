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

### Disclaimer

During an initial bootstrapping phase, the Arbitrum deployment is controlled by a multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.

### Related Smart Contracts

| Token   | AToken | Stable Debt Token  | Variable Debt Token  | Interest Rate Strategy |
| :-----: | :----: | :----------------: | :------------------: | :--------------------: |
| [AAVE](https://arbiscan.io/address/0xba5ddd1f9d7f570dc94a51479a000e3bce967196) | [aArbAAVE](https://arbiscan.io/address/0xf329e36C7bF6E5E86ce2150875a84Ce77f477375) | [sArbAAVE](https://arbiscan.io/address/0xfAeF6A702D15428E588d4C0614AEFb4348D83D48) | [vArbAAVE](https://arbiscan.io/address/0xE80761Ea617F66F96274eA5e8c37f03960ecC679) |
| [DAI](https://arbiscan.io/address/0xda10009cbd5d07dd0cecc66161fc93d7c9000da1) | [aArbDAI](https://arbiscan.io/address/0x82E64f49Ed5EC1bC6e43DAD4FC8Af9bb3A2312EE) | [sArbDAI](https://arbiscan.io/address/0xd94112B5B62d53C9402e7A60289c6810dEF1dC9B) | [vArbDAI](https://arbiscan.io/address/0x8619d80FB0141ba7F184CbF22fd724116D9f7ffC)| 