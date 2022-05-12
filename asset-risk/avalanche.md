---
description: Aave's deployment on the Avalanche C-Chain
---

# Avalanche

Following the [Aave DAO snapshot approval](https://snapshot.org/#/aave.eth/proposal/QmbGh1VP1w51PfBWkEmNquD95NJhJ8Eaqma6PP8psP9HGy), the Aave Protocol has been deployed on Avalanche. Avalanche is one of the fastest smart contracts platforms in the blockchain industry, as measured by time-to-finality, and has the most validators securing its activity of any proof-of-stake protocol. Avalanche’s C-Chain is an instance of the EVM running with Avalanche’s consensus.

### Risk Parameters

| Asset | Borrowing | Collateral | Loan to Value | Liquidation threshold | Liquidation penalty | Reserve Factor |
| ----- | --------- | ---------- | ------------- | --------------------- | ------------------- | -------------- |
| AAVE  | No        | Yes        | 40%           | 65%                   | 10%                 |                |
| DAI   | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| USDC  | Yes       | Yes        | 75%           | 80%                   | 5%                  | 10%            |
| USDT  | Yes       | No         |               |                       |                     | 10%            |
| AVAX  | Yes       | Yes        | 50%           | 65%                   | 10%                 | 15%            |
| WBTC  | Yes       | Yes        | 60%           | 75%                   | 5%                  | 20%            |
| WETH  | Yes       | Yes        | 80%           | 82.5%                 | 5%                  | 10%            |

The reserve factor collector contract can be found at [0x467b92aF281d14cB6809913AD016a607b5ba8A36](https://avascan.info/blockchain/c/address/0x467b92aF281d14cB6809913AD016a607b5ba8A36)

### Price Feed

Chainlink oracles are available on Avalanche based on [this address repository](https://docs.chain.link/docs/avalanche-price-feeds/).

### Disclaimer

During an initial bootstrapping phase, the Avalanche deployment is controlled by a multisig. This multisig is held by guardians recently elected by the Aave DAO and follows the same security practices implemented during the governance transition period for Aave V1 and V2.

