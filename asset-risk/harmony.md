---
description: Aave's deployment on the Harmony
---

# Harmony

[Snapshot to deploy V2 on Harmony](https://snapshot.org/#/aave.eth/proposal/QmYYBedL9aRFdC5DUgjN3QMoYxvJhAUBb2sEyhFuVQZbLG) passed with a success. But with V3 launch soon deployments were postponed.

Now the Aave Protocol V3 has been deployed on Harmony. Harmony is a sharded proof-of-stake blockchain, operated by over 100 external validators. It is fully EVM and Ethereum tooling compatible. Read more about [👉🏻 Harmony](https://www.harmony.one/)

### Risk Parameters

| Asset | Borrowing | Collateral | Loan to Value | Liquidation threshold | Liquidation penalty | Reserve Factor |
| ----- | --------- | ---------- | ------------- | --------------------- | ------------------- | -------------- |
| AAVE  | No        | Yes        | 40%           | 65%                   | 10%                 |                |
| CRV   | Yes       | No         |               |                       |                     | 10%            |
| DAI   | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| LINK  |
| SUSHI | Yes       | No         |               |                       |                     | 10%            |
| USDC  | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| USDT  | Yes       | No         |               |                       |                     | 10%            |
| WBTC  | Yes       | Yes        | 60%           | 75%                   | 5%                  | 20%            |
| WETH  | Yes       | Yes        | 80%           | 82.5%                 | 5%                  | 10%            |
| WFTM  | Yes       | Yes        | 50%           | 65%                   | 10%                 | 15%            |

The reserve factor aks treasury collector contract can be found at [0xeaC16519923774Fd7723d3D5E442a1e2E46BA962](https://explorer.harmony.one/address/0xeac16519923774fd7723d3d5e442a1e2e46ba962)

### Price Feed

Chainlink oracles are available on Harmony based on [👉🏻 address repository](https://docs.chain.link/docs/harmony-price-feeds/).

### Disclaimer

During an initial bootstrapping phase, the Harmony deployment is controlled by a multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.