---
description: Aave's Market on the Polygon sidechain
---

# Polygon

Aave's first exploration of New Frontiers was V2 market launch on [Polygon](https://polygon.technology). A scalable sidechain of Ethereum that allows fast and nearly-free transactions, with a nascent ecosystem of applications such as community favourite [Aavegotchi](https://aavegotchi.com), decentralised exchange [Quickswap](https://quickswap.exchange/#/swap) as well as [Chainlink](https://chain.link) oracles.

Nearly a hundred validators secure Polygon's Proof-of-Stake algorithm with back ups every 30 minutes on the Ethereum blockchain.

Following huge success of V2 markets, Aave Protocol V3 has been deployed on Polygon.

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

The reserve factor collector contract can be found at [0x73D435AFc15e35A9aC63B2a81B5AA54f974eadFe](https://polygonscan.com/address/0x73D435AFc15e35A9aC63B2a81B5AA54f974eadFe)

### Price Feed

Chainlink oracles are available on Polygon based on [this address repository](https://docs.chain.link/docs/matic-addresses/).

### Cross chain governance

Both Aave V2 and V3 markets are controlled via Aave Governance via Aave Cross Chain Governance bridge.