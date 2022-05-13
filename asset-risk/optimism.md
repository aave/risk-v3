---
description: Aave's deployment on the Optimism
---

# Optimism

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0xba58ab5e24dcaef5490fd8717320f74e3c85aea36811d421b48822d4069b6d45), the Aave Protocol V3 has been deployed on Optimism. Optimism is a Layer 2 Optimistic Rollup network designed to utilize the strong security guarantees of Ethereum while reducing its cost and latency. Optimism is EVM equivalent, making the transition from L1 to L2 as seamless as possible.

You can read more about optimism [👉 here](https://www.optimism.io/about)

### Risk Parameters

| Asset | Borrowing | Collateral | Loan to Value | Liquidation threshold | Liquidation penalty | Reserve Factor |
| ----- | --------- | ---------- | ------------- | --------------------- | ------------------- | -------------- |
| AAVE  | No        | Yes        | 40%           | 65%                   | 10%                 |                |
| DAI   | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| LINK  |
| SUSD  | Yes       | No         |               |                       |                     | 10%            |
| USDC  | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| USDT  | Yes       | No         |               |                       |                     | 10%            |
| WBTC  | Yes       | Yes        | 60%           | 75%                   | 5%                  | 20%            |
| WETH  | Yes       | Yes        | 80%           | 82.5%                 | 5%                  | 10%            |

The reserve factor aks treasury collector contract can be found at [0xA77E4A084d7d4f064E326C0F6c0aCefd47A5Cb21](https://optimistic.etherscan.io/address/0xA77E4A084d7d4f064E326C0F6c0aCefd47A5Cb21#code)

### Price Feed

Chainlink oracles are available on Optimism based on [👉🏻 address repository](https://docs.chain.link/docs/optimism-price-feeds/).

### Disclaimer

During an initial bootstrapping phase, the Optimism deployment is controlled by a Gnosis safe multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.
