---
description: Aave's deployment on the Fantom
---

# Fantom

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0x4a8ff1d3876390cde6b43fc93c0135de67fb6aa68a23e8eefeb770fe95735932), the Aave Protocol V3 has been deployed on Fantom. Fantom is an EVM-compatible L1 chain that offers fast finality, low transaction fees and has the [6th largest TVL according to DefiLlama](https://defillama.com/chains).

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

The reserve factor aks treasury collector contract can be found at [0xc0F0cFBbd0382BcE3B93234E4BFb31b2aaBE36aD](https://avascan.info/blockchain/c/address/0xc0F0cFBbd0382BcE3B93234E4BFb31b2aaBE36aD)

### Price Feed

Chainlink oracles are available on Fantom based on [👉🏻 address repository](https://docs.chain.link/docs/fantom-price-feeds/).

### Disclaimer

During an initial bootstrapping phase, the Fantom deployment is controlled by a multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.