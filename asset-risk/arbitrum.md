---
description: Aave's deployment on the Arbitrum
---

# Arbitrum

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0x7c6261b04115e79c63cffb1602295836df36883fc76fc899bce3345c2beaeba3), the Aave Protocol V3 has been deployed on Arbitrum One.Arbitrum is the leading Ethereum Rollup, with hundreds of live apps including most top Ethereum apps and infrastructure. Arbitrum's TVL accounts for 47.8% of TVL across all Ethereum L2s tracked by L2Beat. You can read more [👉🏻 here](https://portal.arbitrum.one)


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

The reserve factor aks treasury collector contract can be found at [0xC3301b30f4EcBfd59dE0d74e89690C1a70C6f21B](https://arbiscan.io/address/0xc3301b30f4ecbfd59de0d74e89690c1a70c6f21b#code)

### Price Feed

Chainlink oracles are available on Arbitrum based on [👉🏻 address repository](https://docs.chain.link/docs/arbitrum-price-feeds/).

### Disclaimer

During an initial bootstrapping phase, the Arbitrum deployment is controlled by a multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.