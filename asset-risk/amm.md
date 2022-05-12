---
description: Aave's Automated Market Maker Market for Liquidity Pool Tokens
---

# AMM

The new Aave AMM Liquidity Pool enables liquidity providers (“LPs”) of Uniswap and Balancer to use their LP tokens as collateral in the Aave Protocol.&#x20;

It is the first of many markets of Aave, on Ethereum, and potentially also on different networks, allowing the community to explore “new frontiers” while segregating risk profiles within markets. The new market light deployment [has been audited by Peckshield](https://github.com/aave/protocol-v2/blob/feat/light-deployments/audits/Peckshield-aave-v2-light-16-03-2021.pdf).

### How do LP tokens work? <a href="#27f4" id="27f4"></a>

By providing liquidity, users automatically obtain LP tokens from the AMM. In most cases, LP tokens represent the crypto assets the user deposited into the AMM along with a proportional scale of the trading fees collected over time in the particular liquidity pool into which the user deposited assets. Because LP tokens typically accrue trading fees over the time the user’s assets remain in the liquidity pool, the LP tokens potentially accrue value over time as well. Uniswap V2 LP token holds a 50/50 ratio of the tokens. Balancer is one of the most innovative AMMs in the ecosystem. Their smart pool system broke the 50/50 ratio status quo and allowed for more sophisticated liquidity pools.

### Risks

LP tokens risks are proportional to the underlying components. LP tokens are subject to impermanent loss that emerges from the difference in volatility of the underlying assets and the rebalancing of the AMM pools. This additional risk, is mitigated by the diversification benefits of having various assets as well as the fee accrual.

![AMM Risk Map](<../.gitbook/assets/Screenshot 2021-03-16 at 12.03.01.png>)

Furthermore the structured nature of LP tokens, leads to more complex liquidations with an additional step to redeem the underlying assets on the corresponding platform. This results in higher gas costs with cascading effects in case of network congestion. To smooth the process, the **liquidation bonus is set at 15% for all LP tokens.**

At this time, users may borrow the following crypto assets: **DAI, USDC, ETH, wBTC** and **USDT**.

### Risk Parameters

| Asset                | Currency | Collateral | Loan to Value | Liquidation threshold | Liquidation bonus | Reserve Factor |
| -------------------- | -------- | ---------- | ------------- | --------------------- | ----------------- | -------------- |
| DAI                  | Yes      | Yes        | 75%           | 80%                   | 5%                | 10%            |
| USDC                 | Yes      | Yes        | 80%           | 85%                   | 5%                | 10%            |
| USDT                 | Yes      | No         |               |                       |                   |                |
| WBTC                 | Yes      | Yes        | 70%           | 75%                   | 10%               | 20%            |
| WETH                 | Yes      | Yes        | 80%           | 82.5%                 | 5%                | 10%            |
| Uniswap V2 AAVE/WETH | Yes      | Yes        | 60%           | 70%                   | 15%               | 5%             |
| Uniswap V2 BAT/WETH  | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Uniswap V2 DAI/WETH  | Yes      | Yes        | 60%           | 70%                   | 15%               | 10%            |
| Uniswap V2 DAI/USDC  | Yes      | Yes        | 60%           | 70%                   | 15%               | 10%            |
| Uniswap V2 WETH/CRV  | Yes      | Yes        | 50%           | 60%                   | 15%               | 15%            |
| Uniswap V2 LINK/WETH | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Uniswap V2 MKR/WETH  | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Uniswap V2 REN/WETH  | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Uniswap V2 SNX/WETH  | Yes      | Yes        | 40%           | 60%                   | 15%               | 20%            |
| Uniswap V2 UNI/WETH  | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Uniswap V2 USDC/WETH | Yes      | Yes        | 60%           | 70%                   | 15%               | 10%            |
| Uniswap V2 WBTC/WETH | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Uniswap V2 WBTC/USDC | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Uniswap V2 YFI/WETH  | Yes      | Yes        | 50%           | 60%                   | 15%               | 15%            |
| Balancer WBTC/WETH   | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |
| Balancer BAL/WETH    | Yes      | Yes        | 60%           | 70%                   | 15%               | 15%            |

### Borrow Interest Rate

**Stablecoins - DAI, USDC, USDT** can be borrowed at a variable rate with the following parameters:

* Uoptimal = 80%
* Base = 0%
* Slope 1 = 4%
* Slope 2 = 75%

![Stablecoin Borrow Rate Curve](<../.gitbook/assets/image (28).png>)

**ETH & WBTC** can be borrowed at a variable rate with the following parameters:

* Uoptimal = 65%
* Base = 0%
* Slope 1 = 8%
* Slope 2 = 100%

![ETH WBTC Borrow Rate Curve](<../.gitbook/assets/image (29).png>)

### Oracle

To give an accurate estimation of the value of the LPs tokens from both Uniswap & Balancer, the Aave Protocol leverages Chainlink’s decentralised oracle service. The smart-contract to calculate the value of the LP tokens has been [audited](https://consensys.net/diligence/audits/2020/08/aave-balancer-and-uniswap-v2-price-providers/) by ConsenSys Diligence.

### Safety Module

The AMM Liquidity Pools will not be covered by the Aave Safety Module at launch, but Aave Governance can decide to include these pools through the AIP process.

### Disclaimer

As the AMM Market has been launched recently, it is currently controlled by a multisig following the same security practices implemented during the governance transition period for Aave V1 and V2.
