---
description: Aave's deployment on the Avalanche C-Chain
---

# Avalanche

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/0x0f682decaf1657b36110beb6914a89dc16b305b163d7a75c22848f059ee9bd24), new Aave Protocol V3 markets has been deployed on Avalanche. Avalanche is one of the fastest smart contracts platforms in the blockchain industry, as measured by time-to-finality, and has the most validators securing its activity of any proof-of-stake protocol. Avalanche’s C-Chain is an instance of the EVM running with Avalanche’s consensus.

### Risk Parameters

| Asset | Borrowing | Collateral | Loan to Value | Liquidation threshold | Liquidation penalty | Reserve Factor |
| ----- | --------- | ---------- | ------------- | --------------------- | ------------------- | -------------- |
| AAVE  | No        | Yes        | 40%           | 65%                   | 10%                 |                |
| DAI   | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| LINK  |
| USDC  | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| USDT  | Yes       | No         |               |                       |                     | 10%            |
| WAVAX | Yes       | Yes        | 50%           | 65%                   | 10%                 | 15%            |
| WBTC  | Yes       | Yes        | 60%           | 75%                   | 5%                  | 20%            |
| WETH  | Yes       | Yes        | 80%           | 82.5%                 | 5%                  | 10%            |

The reserve factor aks treasury collector contract can be found at [0xaCbE7d574EF8dC39435577eb638167Aca74F79f0](https://snowtrace.io/address/0xaCbE7d574EF8dC39435577eb638167Aca74F79f0)

### Price Feed

Chainlink oracles are available on Avalanche based on [this address repository](https://docs.chain.link/docs/avalanche-price-feeds/).

### Disclaimer

During an initial bootstrapping phase, the Avalanche deployment is controlled by a multisig and follows the same security practices implemented during the governance transition period for Aave V1 and V2.