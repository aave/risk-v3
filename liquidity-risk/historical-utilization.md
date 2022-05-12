---
description: Dive into the historical utilisation of Aave's assets
---

# Historical Utilisation

Each currency reserve is characterised by its utilisation rate $$U$$ :

&#x20;$$U \hspace{1mm} = \hspace{1mm} Total Borrows \hspace{2mm} / \hspace{2mm}Total Liquidity$$&#x20;

$$U$$monitors which share of the reserve’s total capital is borrowed at time $$t$$.

As $$U$$gets closer to 100%, the capital becomes scarcer until no more liquidity is available when $$U = 100\%$$. This situation can be problematic if depositors wish to withdraw their liquidity, but no funds are available.&#x20;

Still high utilisation results in high returns for depositors. Its therefore essential to maximise utilisation while protecting liquidity.

The interest rate model is calibrated around an optimal utilisation rate $$U_{optimal}$$per reserve that reflects market conditions.

The historical utilisation rate helps us track the risk emerging from the lack of liquidity. This analysis is based on the maximal daily Utilisation, a conservative metric proxy for liquidity. Given the recent release of V2, this historical analysis is still based on Aave V1.\
\
Since inception, across the assets of the Aave Market, full utilisation was reached only 1% of days since inception. The table below shows the Aave Market statistics on the maximum daily utilisation as at the 24th of November 2020.&#x20;

| Statistic | % of time |
| --------: | --------- |
|    = 100% | 1%        |
|     > 95% | 2.8%      |
|     > 90% | 4.6%      |
|     > 80% | 11.4%     |
|     > 50% | 26%       |
|     < 25% | 52.6%     |
|     < 10% | 38.5%     |
|      < 5% | 28.7%     |

## Stablecoins

Stablecoins are the preferred currency for borrowing, and their reserves are among the most utilised. The chart below shows the historical utilisation of Aave’s stablecoin reserves.

![Aave Market Stablecoin Utilisation](<../.gitbook/assets/image (26).png>)

Most stablecoin reserves show utilisation in the top part of the chart, above 60%; full utilisation is reached each time the lines touch the 100%. DAI and sUSD reach full utilisation 1.2% to 5% of days. These reserves, are among the smallest ones, leading to more sensitivity to large transactions with volatility in utilisation. As of the 24th of November 2020, the sUSD reserve is $1.7m: a $170k deposit/withdrawal or borrow/repay can shift the utilisation rate by 10%. Following high utilisation the interest rate parameters of DAI, BUSD and sUSD were lowered in September and October, which has improved liquidity with no full utilisation of stablecoins in the last month.

| Statistic |    BUSD   |    DAI    |    sUSD   |    TUSD   |  USDC  |    USDT   |
| :-------: | :-------: | :-------: | :-------: | :-------: | :----: | :-------: |
|    Max    |    100%   |    100%   |    100%   |    100%   |  100%  |    100%   |
|   = 100%  |    0.3%   |    1.2%   |     5%    |     0%    |   0%   |     0%    |
|   > 95%   |    2.5%   |    6.8%   |   13.4%   |    2.8%   |  2.8%  |    4.3%   |
|   > 90%   |    4.3%   |   15.2%   |   19.3%   |    18%    | **9%** | **11.5%** |
|   > 80%   | **21.1%** | **39.1%** | **46.9%** | **18.1%** |  25.8% |   33.2%   |
|   > 50%   |   46.9%   |    86%    |   78.2%   |   43.5%   |  71.7% |   71.4%   |
|   < 25%   |   15.5%   |     0%    |   11.8%   |    32%    |  4.3%  |   10.9%   |
|   < 10%   |    4.3%   |     0%    |     4%    |     5%    |  0.3%  |    0.3%   |
|    < 5%   |    0.6%   |     0%    |    0.9%   |    0.3%   |  0.3%  |    0.3%   |

The stablecoin reserves are mostly utilised, $$U > 50\%$$, most of the time. For each of the assets, utilisation seems to hover around the Uoptimal, in bold, indicating the interest rate model is efficient at protecting liquidity. Occurrences of utilisation above 95% are rare throughout all reserves. The most utilised markets are DAI, sUSD, USDC and USDT with a utilisation above 90% more than 10% of the days.

## Other Assets

The other currencies integrated in the Aave portfolio have been selected for the quality of their product. Their upside potential is significant which may explain why users seem less inclined to borrow them as apparent in the chart of historical utilisation rates below.

![Aave Market Volatile Assets Utilisation](<../.gitbook/assets/image (27).png>)

The utilisation of volatile assets looks completely different from the stablecoins, most currencies being concentrated on lower utilisation. There has been an increase in utilisation over the summer driven by the launch of liquidity tokens such as Compound Governance token which rewards liquidity providers. One can observe a utilisation drop assets when incentives disappear, for example for BAT. This trend is expected to continue with new liquidity tokens bound to emerge. The optimal utilisation of assets used as collateral needs to be kept low to keep a liquidity margin in the reserves.

SNX stands out as the token with the highest utilisation. The SNX reserve reaches full utilisation 9.3% of the days. Indeed the Synthetix system is based on staking where holders lock SNX tokens to mint synths. Those with large stakes are able to profit even when borrowing SNX with interest. This also impacts sUSD which are minted in exchange of locking SNX.

Overall utilisation of the volatile assets is nearly always (> 85% of days) below 25% for all assets except SNX, YFI and REN. This shows confidence in the growth of the Aave Market Assets. It is worth noting that borrowing has not been enabled for governance tokens AAVE and UNI.

The table below shows statistics on maximum daily utilisation of Aave's primary market assets.&#x20;

| Statistic |  BAT  |  ETH  |  KNC  |  LEND |  LINK |  MANA |  MKR  |  REN  |  REP  |  SNX  |  WBTC |  YFI  |  ZRX  |
| :-------: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|    Max    |  100% | 80.4% |  100% | 17.6% | 43.4% | 82.6% |  100% | 45.7% | 57.3% |  100% |  100% | 65.7% | 64.9% |
|   = 100%  |  0.3% |   0%  |  3.1% |   0%  |   0%  |   0%  |  0.3% |   0%  |   0%  |  9.3% |  0.3% |   0%  |   0%  |
|   > 95%   |  0.3% |   0%  |  5.6% |   0%  |   0%  |   0%  |  1.2% |   0%  |   0%  | 13.7% |  0.3% |   0%  |   0%  |
|   > 90%   |  1.6% |   0%  |  6.8% |   0%  |   0%  |   0%  |  1.2% |   0%  |   0%  | 15.2% |  0.3% |   0%  |   0%  |
|   > 80%   |  2.2% |  0.3% |  8.1% |   0%  |   0%  |  0.6% |  1.2% |   0%  |   0%  | 19.6% |  0.6% |   0%  |   0%  |
|   > 50%   |  9.6% |   4%  | 10.6% |   0%  |   0%  |  9.9% |  2.2% |   0%  |  2.2% | 54.7% |  1.6% |  0.3% |  1.9% |
|   < 25%   | 81.4% | 77.6% | 81.1% |  100% |  95%  | 76.4% | 85.4% | 32.3% | 86.3% | 11.5% | 97.2% | 19.6% | 81.1% |
|   < 10%   | 55.3% | 52.8% |  72%  | 98.1% | 84.5% | 67.1% | 72.4% | 25.8% | 64.2% |  0.3% | 89.8% | 12.1% | 49.4% |
|    < 5%   | 26.7% | 11.8% | 52.8% | 96.3% | 14.6% | 51.2% | 14.6% | 10.2% | 57.1% |   0%  | 64.9% | 10.6% | 38.8% |

## Results

Aave’s historical utilisation rates show us that each asset has a different liquidity risk profile evolving with market opportunities and the volume of the reserve. Overall, besides newly launched reserves, reserves that systematically reach 100% utilisation have specific characteristics that make them prone to it. Synthetix assets (SNX and sUSD), or tokens prone to liquidity mining, generate passive income which may outweigh the costs of borrowing. Furthermore, rational investor may suddenly borrow out Aave's reserve to seize market opportunities leading to full utilisation.&#x20;

Overall, Aave’s liquidity is adequate, validating the protocol’s incentives. For the reserves that experience full utilisation, alternative sources of liquidity could enable users to redeem their deposits anytime, if not on Aave, on other liquidity pools such as Uniswap or Balancer.
