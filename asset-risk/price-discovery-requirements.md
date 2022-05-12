# Price Discovery

The price update frequency results from the liquidation strategy. We follow a margin method, in which prices are refreshed every time the deviation crosses a certain threshold. We use [Chainlink](https://chain.link)’s decentralised oracles for the price feeds, the full adress repository is available [here](https://docs.chain.link/docs/ethereum-addresses/) and summarised below.



| Name                  | Symbol | Price updated every | Address                                                                                        |
| --------------------- | ------ | :-----------------: | ---------------------------------------------------------------------------------------------- |
| Ampleforth            | AMPL   |          2%         | https://feeds.chain.link/ampl-eth                                                              |
| Binance USD           | BUSD   |          1%         | [https://feeds.chain.link/busd-eth](https://feeds.chain.link/busd-eth)                         |
| DAI                   | DAI    |          1%         | [https://feeds.chain.link/dai-eth](https://feeds.chain.link/dai-eth)                           |
| Gemini Dollars        | GUSD   |                     | [https://feeds.chain.link/eth-usd](https://feeds.chain.link/eth-usd) fixed 1$                  |
| Paxos Standard        | PAX    |          2%         | [https://feeds.chain.link/pax-eth](https://feeds.chain.link/pax-eth)                           |
| Rai Reflex Index      | RAI    |          2%         | [https://feeds.chain.link/rai-eth](https://feeds.chain.link/rai-eth)                           |
| Synthetix USD         | SUSD   |          1%         | [https://feeds.chain.link/susd-eth](https://feeds.chain.link/susd-eth)                         |
| True USD              | TUSD   |          1%         | [https://feeds.chain.link/tusd-eth](https://feeds.chain.link/tusd-eth)                         |
| USDC                  | USDC   |          1%         | [https://feeds.chain.link/usdc-eth](https://feeds.chain.link/usdc-eth)                         |
| Tether                | USDT   |          1%         | [https://feeds.chain.link/usdt-eth](https://feeds.chain.link/usdt-eth)                         |
| Aave                  | AAVE   |          2%         | [https://feeds.chain.link/aave-eth](https://feeds.chain.link/aave-eth)                         |
| Balancer              | BAL    |          2%         | [https://data.chain.link/bal-eth](https://data.chain.link/bal-eth)                             |
| Basic Attention Token | BAT    |          2%         | [https://feeds.chain.link/bat-eth](https://feeds.chain.link/bat-eth)                           |
| Curve                 | CRV    |          2%         | [https://data.chain.link/crv-eth](https://data.chain.link/crv-eth)                             |
| Enjin                 | ENJ    |          2%         | [https://feeds.chain.link/enj-eth](https://feeds.chain.link/enj-eth)                           |
| Ethereum              | ETH    |          1%         | [https://feeds.chain.link/eth-usd](https://feeds.chain.link/eth-usd)                           |
| Kyber Network         | KNC    |          2%         | [https://feeds.chain.link/knc-eth](https://feeds.chain.link/knc-eth)                           |
| Chainlink             | LINK   |          1%         | [https://feeds.chain.link/link-eth](https://feeds.chain.link/link-eth)                         |
| Decentraland          | MANA   |          2%         | [https://feeds.chain.link/mana-eth](https://feeds.chain.link/mana-eth)                         |
| Maker                 | MKR    |          1%         | [https://feeds.chain.link/mkr-eth](https://feeds.chain.link/mkr-eth)                           |
| Republic Protocol     | REN    |          2%         | [https://feeds.chain.link/ren-eth](https://feeds.chain.link/ren-eth)                           |
| Ren Filecoin          | RenFIL |          2%         | [https://data.chain.link/fil-eth](https://data.chain.link/ethereum/mainnet/crypto-eth/fil-eth) |
| Synthetix             | SNX    |          2%         | [https://feeds.chain.link/snx-eth](https://feeds.chain.link/snx-eth)                           |
| Sushi                 | SUSHI  |          2%         | [https://data.chain.link/sushi-eth](https://data.chain.link/sushi-eth)                         |
| Uniswap               | UNI    |          2%         | [https://feeds.chain.link/uni-eth](https://feeds.chain.link/uni-eth)                           |
| Wrapped BTC           | WBTC   |          2%         | [https://feeds.chain.link/btc-eth](https://feeds.chain.link/btc-eth)                           |
| Yearn YFI             | YFI    |          2%         | [https://feeds.chain.link/yfi-eth](https://feeds.chain.link/yfi-eth)                           |
| 0x                    | ZRX    |          2%         | [https://feeds.chain.link/zrx-eth](https://feeds.chain.link/zrx-eth)                           |

For more details on the price oracle and its backups please check the[ Price Oracle](https://docs.aave.com/developers/the-core-protocol/price-oracle) section of the developer documentation.
