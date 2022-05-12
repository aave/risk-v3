---
description: Aave's Market on the Polygon sidechain
---

# Polygon

Aave's first exploration of New Frontiers is [Polygon](https://polygon.technology) (_formerly known as MATIC). A_ scalable sidechain of Ethereum that allows fast and nearly-free transactions, with a nascent ecosystem of applications such as community favourite [Aavegotchi](https://aavegotchi.com), decentralised exchange [Quickswap](https://quickswap.exchange/#/swap) as well as [Chainlink](https://chain.link) oracles.&#x20;

Nearly a hundred validators secure Polygon's Proof-of-Stake algorithm with back ups every 30 minutes on the Ethereum blockchain.&#x20;

### Risk Parameters

| Asset | Borrowing | Collateral | Loan to Value | Liquidation threshold | Liquidation penalty | Reserve Factor |
| ----- | --------- | ---------- | ------------- | --------------------- | ------------------- | -------------- |
| AAVE  | No        | Yes        | 50%           | 65%                   | 10%                 |                |
| DAI   | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| USDC  | Yes       | Yes        | 80%           | 85%                   | 5%                  | 10%            |
| USDT  | Yes       | No         |               |                       |                     | 10%            |
| MATIC | Yes       | Yes        | 50%           | 65%                   | 10%                 | 20%            |
| WBTC  | Yes       | Yes        | 70%           | 75%                   | 10%                 | 20%            |
| WETH  | Yes       | Yes        | 80%           | 82.5%                 | 5%                  | 10%            |

The reserve factor collector contract can be found at [0x7734280a4337f37fbf4651073db7c28c80b339e9](https://debank.com/profile/0x7734280a4337f37fbf4651073db7c28c80b339e9?chain=matic)

### Price Feed

Chainlink oracles are available on Polygon based on [this address repository](https://docs.chain.link/docs/matic-addresses/).

### Disclaimer

As the Polygon Market has been launched recently, it is currently controlled by a multisig until a specific governance bridge for Polygon is built. The multisig follows the same security practices implemented during the governance transition period for Aave V1 and V2.

