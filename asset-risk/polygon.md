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

## Related Smart Contracts

|      | Token                                                                                                               | aToken                                                                                                              | Stable Debt Token                                                                                                   | Variable Debt Token                                                                                                 | Interest Rate Strategy                                                                                                |
| ---- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| DAI  | [0x6b175474e89094c44da98b954eedeac495271d0f](https://etherscan.io/token/0x6b175474e89094c44da98b954eedeac495271d0f) | [0x028171bCA77440897B824Ca71D1c56caC55b68A3](https://etherscan.io/token/0x028171bCA77440897B824Ca71D1c56caC55b68A3) | [0x778A13D3eeb110A4f7bb6529F99c000119a08E92](https://etherscan.io/token/0x778A13D3eeb110A4f7bb6529F99c000119a08E92) | [0x6C3c78838c761c6Ac7bE9F59fe808ea2A6E4379d](https://etherscan.io/token/0x6C3c78838c761c6Ac7bE9F59fe808ea2A6E4379d) | [0xfffE32106A68aA3eD39CcCE673B646423EEaB62a](https://etherscan.io/address/0xfffE32106A68aA3eD39CcCE673B646423EEaB62a) |
| sUSD | [0x57ab1ec28d129707052df4df418d58a2d46d5f51](https://etherscan.io/token/0x57ab1ec28d129707052df4df418d58a2d46d5f51) | [0x6C5024Cd4F8A59110119C56f8933403A539555EB](https://etherscan.io/token/0x6C5024Cd4F8A59110119C56f8933403A539555EB) |                                                                                                                     | [0xdC6a3Ab17299D9C2A412B0e0a4C1f55446AE0817](https://etherscan.io/token/0xdC6a3Ab17299D9C2A412B0e0a4C1f55446AE0817) | [0x3082D0a473385Ed2cbd1f16087ab8b7BF79f0355](https://etherscan.io/address/0x3082D0a473385Ed2cbd1f16087ab8b7BF79f0355) |
| USDC | [0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48](https://etherscan.io/token/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48) | [0xBcca60bB61934080951369a648Fb03DF4F96263C](https://etherscan.io/token/0xBcca60bB61934080951369a648Fb03DF4F96263C) | [0xE4922afAB0BbaDd8ab2a88E0C79d884Ad337fcA6](https://etherscan.io/token/0xE4922afAB0BbaDd8ab2a88E0C79d884Ad337fcA6) | [0x619beb58998eD2278e08620f97007e1116D5D25b](https://etherscan.io/token/0x619beb58998eD2278e08620f97007e1116D5D25b) | [0x8Cae0596bC1eD42dc3F04c4506cfe442b3E74e27](https://etherscan.io/address/0x8Cae0596bC1eD42dc3F04c4506cfe442b3E74e27) |
| USDT | [0xdac17f958d2ee523a2206206994597c13d831ec7](https://etherscan.io/token/0xdac17f958d2ee523a2206206994597c13d831ec7) | [0x3Ed3B47Dd13EC9a98b44e6204A523E766B225811](https://etherscan.io/token/0x3Ed3B47Dd13EC9a98b44e6204A523E766B225811) | [0xe91D55AB2240594855aBd11b3faAE801Fd4c4687](https://etherscan.io/token/0xe91D55AB2240594855aBd11b3faAE801Fd4c4687) | [0x531842cEbbdD378f8ee36D171d6cC9C4fcf475Ec](https://etherscan.io/token/0x531842cEbbdD378f8ee36D171d6cC9C4fcf475Ec) | [0x515E87cb3fec986050F202a2bbfa362A2188bc3F](https://etherscan.io/address/0x515E87cb3fec986050F202a2bbfa362A2188bc3F) |
| AAVE | [0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9](https://etherscan.io/token/0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9) | [0xFFC97d72E13E01096502Cb8Eb52dEe56f74DAD7B](https://etherscan.io/token/0xFFC97d72E13E01096502Cb8Eb52dEe56f74DAD7B) |                                                                                                                     |                                                                                                                     |                                                                                                                       |
| CRV  | [0xd533a949740bb3306d119cc777fa900ba034cd52](https://etherscan.io/token/0xd533a949740bb3306d119cc777fa900ba034cd52) | [0x8dAE6Cb04688C62d939ed9B68d32Bc62e49970b1](https://etherscan.io/token/0x8dAE6Cb04688C62d939ed9B68d32Bc62e49970b1) |                                                                                                                     | [0x00ad8eBF64F141f1C81e9f8f792d3d1631c6c684](https://etherscan.io/token/0x00ad8eBF64F141f1C81e9f8f792d3d1631c6c684) | [0xE3a3DE71B827cB73663A24cDB6243bA7F986cC3b](https://etherscan.io/address/0xE3a3DE71B827cB73663A24cDB6243bA7F986cC3b) |
| LINK | [0x514910771af9ca656af840dff83e8264ecf986ca](https://etherscan.io/token/0x514910771af9ca656af840dff83e8264ecf986ca) | [0xa06bC25B5805d5F8d82847D191Cb4Af5A3e873E0](https://etherscan.io/token/0xa06bC25B5805d5F8d82847D191Cb4Af5A3e873E0) | [0xFB4AEc4Cc858F2539EBd3D37f2a43eAe5b15b98a](https://etherscan.io/token/0xFB4AEc4Cc858F2539EBd3D37f2a43eAe5b15b98a) | [0x0b8f12b1788BFdE65Aa1ca52E3e9F3Ba401be16D](https://etherscan.io/token/0x0b8f12b1788BFdE65Aa1ca52E3e9F3Ba401be16D) | [0xED6547b83276B076B771B88FcCbD68BDeDb3927f](https://etherscan.io/address/0xED6547b83276B076B771B88FcCbD68BDeDb3927f) |
| WBTC | [0x2260fac5e5542a773aa44fbcfedf7c193bc2c599](https://etherscan.io/token/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599) | [0x9ff58f4fFB29fA2266Ab25e75e2A8b3503311656](https://etherscan.io/token/0x9ff58f4fFB29fA2266Ab25e75e2A8b3503311656) | [0x51B039b9AFE64B78758f8Ef091211b5387eA717c](https://etherscan.io/token/0x51B039b9AFE64B78758f8Ef091211b5387eA717c) | [0x9c39809Dec7F95F5e0713634a4D0701329B3b4d2](https://etherscan.io/token/0x9c39809Dec7F95F5e0713634a4D0701329B3b4d2) | [0xf41E8F817e6C399d1AdE102059c454093b24f35B](https://etherscan.io/token/0xf41E8F817e6C399d1AdE102059c454093b24f35B)   |
| WETH | [0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2](https://etherscan.io/token/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2) | [0x030bA81f1c18d280636F32af80b9AAd02Cf0854e](https://etherscan.io/token/0x030bA81f1c18d280636F32af80b9AAd02Cf0854e) | [0x4e977830ba4bd783C0BB7F15d3e243f73FF57121](https://etherscan.io/token/0x4e977830ba4bd783C0BB7F15d3e243f73FF57121) | [0xF63B34710400CAd3e044cFfDcAb00a0f32E33eCf](https://etherscan.io/token/0xF63B34710400CAd3e044cFfDcAb00a0f32E33eCf) | [0x4ce076b9dD956196b814e54E1714338F18fde3F4](https://etherscan.io/token/0x4ce076b9dD956196b814e54E1714338F18fde3F4)   |

