---
description: Aave's deployment on the Optimism
---

# Optimism

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0xba58ab5e24dcaef5490fd8717320f74e3c85aea36811d421b48822d4069b6d45), the Aave Protocol V3 has been deployed on Optimism. Optimism is a Layer 2 Optimistic Rollup network designed to utilize the strong security guarantees of Ethereum while reducing its cost and latency. Optimism is EVM equivalent, making the transition from L1 to L2 as seamless as possible.

You can read more about optimism [👉 here](https://www.optimism.io/about)

### Risk Parameters

| Asset | Borrowing | Collateral | Borrow in Isolation | Loan to Value | Liquidation threshold | Liquidation penalty | Debt Ceiling | Supply Cap | Borrow Cap | Reserve Factor |
| ----- | --------- | ---------- | ------------------- | ------------- | --------------------- | ------------------- | ------------ | ---------- | ---------- | -------------- |
| AAVE  | No        |  yes       |          no         |  50%          |  65%                  |  10%                |       -      |    0       |     -      |       0%       | 
| DAI   | Yes       |   yes      | yes                 |      75%      |          80%          |         5%          |       -      |     2B     |     0      |       10%      |
| jSDC  | Yes       | no         | yes                 |  80%          |  85%                  | 5%                  |       -      |     2B     |     0      |       10%      |
| SUSD  | Yes       | Yes        | yes                 |    -          |  -                    |        -            |       -      |     2B     |     0      |       10%      |
| USDT  | Yes       | In Isolation mode | yes          |    75%        |  80%                  |        5%           |       5M     |     2B     |     0      |       10%      |
| WBTC  | Yes       | Yes        | no                  |  70%          | 75%                   | 10%                 |  -           |     0      |    0       |    20%         |
| WETH  | Yes       | Yes        | no                  |  80%          | 82.5%                 | 5%                  |  -           |     0      |    0       |    10%         |

The reserve factor aks treasury collector contract can be found at [0xA77E4A084d7d4f064E326C0F6c0aCefd47A5Cb21](https://optimistic.etherscan.io/address/0xA77E4A084d7d4f064E326C0F6c0aCefd47A5Cb21#code)

### Price Feed
The price update frequency results from the liquidation strategy. We follow a margin method, in which prices are refreshed every time the deviation crosses a certain threshold. We use [Chainlink](https://chain.link)’s decentralised oracles for the price feeds.

Chainlink oracles are available on Optimism based on [👉🏻 address repository](https://docs.chain.link/docs/optimism-price-feeds/).

### Disclaimer

During an initial bootstrapping phase, the Optimism deployment is controlled by a Gnosis safe multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.
