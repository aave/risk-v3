# Risks per Asset

This section showcases the results of the [risk assessment methodology](methodology.md) and analyses the results for each of the currencies considered.

## Asset Risk Map

The [risk assessment methodology](methodology.md) applied to our historical data computes the risk ratings per asset as shown in the table below. This September 2021 update reflects the recent market volatility as well as large growth in use with some tokens doubling their holders and number of transactions.

![Asset Risk Map as of 24/09/2021](<../.gitbook/assets/Screenshot 2021-09-24 at 17.30.26.png>)

## Risk Analysis per Asset

### Stablecoins

### BUSD

[BUSD](https://www.binance.com/en/busd) is one of the latest stablecoins launched by a partnership between [Paxos](https://www.paxos.com), expert in stable coins, and [Binance](https://www.binance.com), one of the biggest exchanges and a major player in the industry. Aave is the first integration of BUSD in a DeFi money market, bridging our ecosystem with CeFi.

[**BUSD Smart contract**](https://ethplorer.io/address/0x4fabb145d64652a948d72533023f6e7a623c7c53#pageSize=100) **Risk: B**

The BUSD contract launched in September 2019 has a decent number of transactions, many transactions are likely to happen off-chain on the Binance exchange. However, Aave has performed a thorough verification of the smart contract that appears identical to the [PAX smart contract](https://ethplorer.io/address/0x8e870d67f660d95d5be530380d0ec0bd388289e1?from=search#pageSize=100) launched in September 2018 with nearly a million transactions. Still, since the smart contract has experienced little use, BUSD cannot be used as collateral at present time.

**BUSD Counterparty Risk: B-**

BUSD is backed by real USD so it is centralised with a centralisation risk factor at D+ disqualifying it as a collateral. The administrative features are explicit with Paxos as custodian and issuer. A monthly audit attests to the consistency of the USD bank reserves versus the on-chain supply of USD. Finally, BUSD is compliant and has been approved by the New York State Department of Financial Services (NYDFS).

[**BUSD Market**](https://coinmarketcap.com/currencies/binance-usd/) **Risk: A**

The market capitalisation is quite high with a fast growth these last few months. The trading volume for BUSD has picked up with billions a day in the last month, mostly driven by Binance. As a stablecoin backed by USD, the volatility is very low.

### DAI

[DAI](https://makerdao.com/en/) is the first decentralised stablecoin built on the Ethereum network. It is minted by creating a Collateralised Debt Position (CDP) and staking a certain amount of ETH. Every CDP must be overcollateralised by at least 150% of the minted DAI. Below this threshold, the CDP gets liquidated.

[**DAI Smart contract**](https://ethplorer.io/address/0x6b175474e89094c44da98b954eedeac495271d0f#pageSize=100) **Risk: B+**

SAI is active since December 2017 and has remained fully operational. In November 2019 the contract has evolved for DAI to hold a basket of currencies instead of just Ethereum. Given its wide use in the DeFi space, the contract already holds over 5 million transactions which mitigates the risk rising from its young age.

**DAI Counterparty Risk: C+**

DAI is the stablecoin of Maker DAO which has been functioning efficiently since inception. Anyone can mint DAI by opening a CPD. The Maker team also has some control over the minting. Following the [Black Thursday crash of March 2020](https://defipulse.com/blog/defi-status-report-black-thursday/), there was some deficit in the backing of DAI which required the minting of additional MKR. Additionally, there are some concerns related to the centralisation of the price feed, with oracles failing to keep the prices up to date during the said Black Thursday.

[**DAI Market**](https://coinmarketcap.com/currencies/multi-collateral-dai/) **Risk: A-**

DAI has billions in  market capitalisation with around half a billion of average daily volume spread across the top exchanges. It has been robust throughout its whole life, sustaining multiple ETH price drops. The volatility is low, yet the DAI peg suffers regularly from high demand. Additional collaterals are since been added, among which USDC to stabilise the price.

### GUSD

[GUSD](https://gemini.com/dollar) is issued by Gemini Trust Company. It has been created for practical use in innovative applications, among which to facilitate Gemini’s institutional solutions and exchange operations.

[**GUSD Smart contract**](https://ethplorer.io/address/0x056fd409e1d7a124bd7017459dfea2f387b6d5cd#pageSize=100\&transfers=847) **Risk: C+**

GUSD was launched in September 2018 – at the same time then USDC – yet it has only experienced 120k blockchain transactions.

The GUSD smart contract only supports 2 decimals meaning that interest accrual can only occur for more than 1 cent.

**GUSD Counterparty Risk: B-**

As it is backed by real US dollars, GUSD is centralised. Moreover it has few holders with most of the transactions off-chain on the centralised Gemini environment.

An independent accountant’s audit report is published at the end of each month on the website. GUSD is regulated bringing trust to the token. Still, the infrastructure is based on the Ethereum blockchain where regulators have little power.

[G**USD Market**](https://www.coingecko.com/en/coins/gemini-dollar) **Risk: B**

GUSD has a small market capitalisation at less than $50m with a small trading volume. The price has diverged from 1$ a few times in the last 3 months with up to 3% price variation.

GUSD cannot be used as collateral.

### SUSD

[Synthetix](https://www.synthetix.io) is a decentralised synthetic asset platform on Ethereum that provides onchain exposure to real world assets. sUSD is the dollars pegged synthetic asset backed by the network token.

[**sUSD Smart contract**](https://ethplorer.io/address/0x57ab1e02fee23774580c119740129eac7081e9d3?from=search#pageSize=100) **Risk: B**

sUSD was launched in June 2018. It is slowly gaining market share in the competitive stablecoin market with only a small number of transactions.

**sUSD Counterparty Risk: C-**

sUSD is built on a decentralised infrastructure but some security reports have highlighted undocumented functions in the Synthetix contracts that might present a security risk. With a centralisation factor at C- sUSD cannot be used as collateral.&#x20;

[**sUSD Market**](https://coinmarketcap.com/currencies/susd/) **Risk: B**

Right now, there isn’t much liquidity available for sUSD on the market and the usage within the DeFi workspace is pretty limited with a small market capitalisation. As a result, sUSD has suffered a [manipulation on the Kyber exchange](https://www.theblockcrypto.com/post/56207/bzx-attacked-again-645k-in-eth-estimated-to-be-lost) resulting in its price rising up to 2.45$. More recently, the Basis Cash farming has driven the price of sUSD to 1.08$. Still the volatility is small with its value is stable around 1 dollar backed by the Synthetix Network Token.

### TUSD

[TrueUSD](https://www.trusttoken.com) is supported by the company TrustToken, which is periodically audited by 3rd parties. Right now, TrueUSD’s usage and diffusion in the DeFi space is limited. Still it is supported by multiple centralised crypto lending operators.

[**TUSD Smart contract**](https://ethplorer.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7#pageSize=100) **Risk: B+**

TUSD is active since May 2018 with this contract deployed in January 2019 holding over nearly a million transactions.

**TUSD Counterparty Risk: D+**

As it’s backed by real US dollars, TUSD is centralised. The technology to mint new TUSD against USD is open source and you can check the real time on chain proof of funds via a chainlink oracle

[**TUSD Market**](https://coinmarketcap.com/currencies/trueusd/) **Risk: B+**

TUSD is widely available in different exchanges with a high volume and market capitalisation. It is a low volatility stablecoin backed by real USD.

### USDC

[USDC](https://www.centre.io/usdc) is primarily promoted by Coinbase and supported by the CENTRE consortium. Together with DAI, it has been the most used stablecoin in the DeFi ecosystem following a strong push from Coinbase who provides liquidity to projects.

[**USDC Smart contract**](https://ethplorer.io/address/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48#pageSize=100) **Risk: A-**

USDC has only been active since September 2018 with already over ten million transactions.

**USDC Counterparty Risk: B**

As it’s backed by real US dollars as well as other high quality reserve assets (since recently0, USDC is centralised. The technology to mint new USDC and hold the backing USD value is based on a legal framework. It is currently maintained by the CENTRE consortium which is a trusted entity in the ecosystem and audited monthly by Grant Thornton. Furthermore, USDC is the first regulated cryptocurrency bringing a lot of legitimacy to the space. Still, the infrastructure is based on the Ethereum blockchain where regulators have little power.

[**USDC Market**](https://coinmarketcap.com/currencies/usd-coin/) **Risk: A**

There is a high trading volume for USDC reaching billions a day, with many pairs in multiple exchanges and a high market capitalisation. The token is used in multiple DeFi platforms both as collateral and principal. USDC is a stablecoin backed by real USD leading to low volatility.

### USDT

[Tether](https://tether.to) is the oldest USD backed stablecoin. It initially started as an independent currency built on the Omni blockchain, and progressively moved on the Ethereum blockchain, presumably to take advantage of the DeFi ecosystem.

[**USDT Smart contract**](https://ethplorer.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7?from=search#pageSize=100) **Risk: A**

USDT is the first stablecoin in operation since November 2014 and on this Ethereum contract since November 2017. With nearly 20 million transactions, USDT is one of the most used coins.

**USDT Counterparty Risk: C-**&#x20;

Tether is centralised, fully controlled by Tether Limited, which is in turn controlled by BitFinex. The procedure to redeem the underlying asset in exchange for USDT is also unclear.

There are [multiple legal investigations](https://en.wikipedia.org/wiki/Bitfinex) on these two companies regarding USDT. Specifically, there has been accusation of illegally manipulating the price of Bitcoin using non backed USDT, as well as legal claims on the usage of the collateralised funds by both Tether Limited and BitFinex. This brings USDT's trust risk factor down to D+ disqualifying it as a collateral.

However, since the beginning of 2020, the company has tried to gain back some trust, disclosing an audit and appropriate collateralisation.

[**USDT Market**](https://coinmarketcap.com/currencies/tether/) **Risk: A+**

USDT is widely available in different exchanges and is the stablecoin with the highest volume. The value of USDT is stable around 1 dollar as it is backed by USD.

### Other Assets

### AAVE

[Aave](https://aave.com)’s native token LEND recently migrated to AAVE to enable more functionalities, with the process ongoing.

[**AAVE Smart contract Risk**](https://ethplorer.io/address/0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9#pageSize=100)**: B-**

The AAVE token was launched the 2nd of October with no deadline to migrate from LEND. The token is picking up with nearly 150k transactions and 15k holders.

**AAVE Counterparty Risk: B+**

Aave Protocol holds decentralisation as a core value, being fully open source. It is the token of the Aaave DAO fully governed by AAVE holders.

****[**AAVE Market** ](https://www.coingecko.com/fr/pi%C3%A8ces/aave)**Risk: B-**

The LEND markets have now migrated to AAVE, with already around $200m of daily volume. Since inception the AAVE token has witnessed high levels of volatility

### BAL

BAL is the governance token of the Balancer decentralized exchange thats allows liquidity pools with multiple tokens, custom allocations and fees. Smart pools in Balancer can be used for programmable liquidity, this solution is currently being implemented for Aave’s Safety Module. Balancer’s Dex currently holds $800m of TVL.

[BAL **Smart contract**](https://ethplorer.io/address/0xba100000625a3754423978a60c9317c58a424e3d#chart=candlestick) **Risk: B**

Since its launch in June BAL has reached half a million transactions driven by liquidity mining distribution program which may lead to inflation. The smart contract has been well battle tested, audited twice and has a good test coverage.

BAL **Counterparty Risk: B**

Balancer is a permissionless Dex with a large community of BAL holders that vote on proposals. Furthermore anyone can create a custom Balancer Pool.

[BAL **Market**](https://www.coingecko.com/en/coins/balancer) **Risk: B-**

The BAL token has experienced less volatility than the rest of the DeFi market since its inception but remains quite volatile. The token is traded on the top centralised exchanges with good volume.

### BAT

[Basic Attention Token](https://basicattentiontoken.org) is an Ethereum based token that was created alongside its native platform, the Brave browser, with more than 5 million monthly users. BAT’s main use case is to reward publishers and content creators through tips on the browser, or as payment currency for the Brave advertisement system.

[**BAT Smart contract**](https://ethplorer.io/address/0x0d8775f648430679a709e98d2b0cb6250d2887ef#pageSize=100) **Risk: B+**

BAT is in operations since 2017, the contract deployed in May holds nearly 3 million transactions.

**BAT Counterparty Risk: B+**

The platform is decentralised and the main product, Brave, is open source. It is based on a non-crypto native product, having managed to build a strong community with over 350,000 holders.

[**BAT Market**](https://coinmarketcap.com/currencies/basic-attention-token/) **Risk: B-**

BAT is one of the established projects on Ethereum and beyond the digital currency space, available on many exchanges with high liquidity. The token price has shown little volatility in the last year.

### CRV

CRV is the governance token of the Curve DAO behind the Curve Stablecoin Exchange the third biggest DEX on Ethereum with $1B of TVL. Curve offers an optimised model for stablecoin trading and revenue sharing incentives with fees from the >$10B in cumulative trading volume.

#### [CRV Smart Contract](https://ethplorer.io/address/0xd533a949740bb3306d119cc777fa900ba034cd52#pageSize=100) Risk: B-

CRV token was introduced to Curve in August 2020 through liquidity mining. The code has 3 audits from [ToB](https://www.curve.fi/curve\_audits/curve-dao-ToB-final.pdf), [Quantstamp](https://www.curve.fi/curve\_audits/curve-dao-quantstamp.pdf) and [MixBytes](https://www.curve.fi/curve\_audits/curve-voting-aragon-mixbytes.pdf). It is central in the DAO operations enabling stakers to boost their yields with the locking of CRV. This model has generated half a billion transactions in half a year, with around 15,000 holders.

#### CRV Counterparty Risk: B

The Curve DAO operates as a fully decentralised organisation with community proposals and votes. The ecosystem is funded by fees of the Curve Exchange generated by the $40m of daily volume.

#### [CRV Market](https://www.coingecko.com/en/coins/curve-dao-token) Risk: B-

Curve is one of the leading DeFi projects. The token is available on top exchanges with nearly $100m market capitalisation and nearly as much average daily volume though a large share of of CRV's supply is locked. CRV experienced volatility in the last month with the rest of the market having yet to recover.

### ENJ

[Enjin](https://enjin.io) aims to connect virtual worlds by empowering the management, minting and trade of blockchain assets. Enjin coin is the utility token of the platform and can be used as collateral to mint new digital assets in their standard ERC-1555.

[**Smart Contract**](https://ethplorer.io/address/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c#pageSize=100) **Risk: B+**&#x20;

Enjin is active and traded since October 2017. It has nearly a million transactions.&#x20;

**Counterparty Risk: B+**

Enjin is a decentralised protocol offering some open source permissionless products (wallet, marketplace, token minting). The community is quite large, with over 75,000 holders.&#x20;

[**Market**](https://www.coingecko.com/en/coins/enjin-coin) **Risk: B-**

ENJ has $170 million of market capitalisation and a decent amount of liquidity in big exchanges. Enjin has grown a lot in 2020 leading to high volatility in the price of the token (like the rest of the ecosystem).&#x20;

### **KNC**

[Kyber](https://kyber.network) is an onchain liquidity protocol that can be used for a variety of inter-token use cases such as payments, portfolio rebalancing, currency exchanges. KNC, is mostly used for referrals and fee management. It implements a deflationary economy. Kyber is building protocol governance on top of the infrastructure based on the KNC token.

[**KNC Smart contract**](https://ethplorer.io/address/0xdd974d5c2e2928dea5f71b9825b8b646686bd200#pageSize=100) **Risk: B+**

Kyber is active and traded since September 2017. It has over 1 billion transactions.

**KNC Counterparty Risk: B+**

Kyber is a decentralised protocol, non-custodial and open source with nearly 100,000 holders.

[**KNC Market**](https://coinmarketcap.com/currencies/kyber-network/) **Risk: C+**

Kyber’s decentralised exchange provides an important number of KNC token pairs with good volume (even on centralised exchanges) and decent market capitalisation. KNC’s price has been rather volatile with a recent spike driven by a new version of the protocol.

### LINK

[ChainLink](https://chain.link) is a protocol that aims to provide a base infrastructure for decentralised oracles. The goal is to allow contracts to fetch data from the real world in a decentralised, tamper-proof manner. The use cases of LINK include payments of oracle fees and staking as a security mechanism to prevent tamper and fraud.

[**LINK Smart contract**](https://ethplorer.io/address/0x514910771af9ca656af840dff83e8264ecf986ca#pageSize=100) **Risk: B+**

ChainLink has been active since 2017 deploying this smart contract in September. Its adoption has boomed in 2019, driven by the reliability of its oracles, with now over 6 million transactions.

**LINK Counterparty Risk: B+**

ChainLink is non-custodial and open source, with nearly 300,000 holders, hence presents low centralisation risk.

[**LINK Market**](https://coinmarketcap.com/currencies/chainlink/) **Risk: B+**

LINK has become increasingly relevant becoming one of the most successful Ethereum projects. It is widely available on exchanges and increasingly popular on DeFi platforms. The trading volume is very high. LINK’s price has seen a sharp increase in 2020 and we can anticipate that the volatility will continue.

### MANA

[Decentraland](https://decentraland.org) is a virtual world on the Ethereum blockchain. Users are able to purchase land with the project’s token MANA, and the ledger is kept on the Ethereum blockchain, which indisputably demonstrates the ownership of the land. The virtual world just opened in February 2020.

[**MANA Smart contract**](https://ethplorer.io/address/0x0f5d2fb29fb7d3cfee444a200298f468908cc942#pageSize=100) **Risk: B+**

MANA has been active since June 2017. It is a well-known currency, with nearly half a million transactions.

**MANA Counterparty Risk: C+**

Decentraland is decentralised and completely open source, with over 50,000 holders. Some part of the protocol, such as the price oracle, hold some centralisation risk.

[**MANA Market**](https://coinmarketcap.com/currencies/decentraland/) **Risk: B-**

The price of MANA has been rather volatile early in the last year as the full project was deployed. It is a well-known currency, with a decent level of liquidity on the market, listed in multiple high-profile exchanges.

### MKR

[MKR](https://makerdao.com/en/) is the utility and governance token used in the [MakerDAO](https://makerdao.com/en/) platform responsible for the emission of DAI. MKR is mainly used to repay the stability fee, and for governance purpose. MKR’s monetary policy is based on a deflationary economy.

[**MRK Smart contract**](https://ethplorer.io/address/0x9f8f72aa9304c8b593d555f12ef6589cc3a579a2#pageSize=100) **Risk: B+**

MKR was launched in 2016, before DAI, with this contract deployed in September 2017. It is widely available on exchanges and increasingly popular in DeFi platforms accounting for nearly 1 billion transactions.

**MKR Counterparty Risk: C**

The MKR token is part of the MakerDAO ecosystem and is decentralised and non-custodial. The token is used for governance votes based on the concept of anchor votes led by some whales. Some votes have even been taken over by whales with single addresses representing up to 94% of the voting power. On the [Black Thursday crash of March 2020](https://defipulse.com/blog/defi-status-report-black-thursday/), the Maker system struggled to cope with price crashes and market congestion, leading to a multimillion deficit in the system. The Foundation, supported by governance funded the deficit by auctioning new MKR tokens. This auction has not lead to the reimbursement of vault holders who lost all their collateral, some are now attacking the foundation with a [class action](https://www.theblockcrypto.com/post/61797/maker-foundation-class-action-lawsuit-black-thursday).

[**MKR Market**](https://coinmarketcap.com/currencies/maker/) **Risk: B-**

MKR is one of the most successful Ethereum projects, supported by a big community with a big market capitalisation. It is available on most exchanges, with decent volume and little volatility.

### REN&#x20;

[Ren Project](https://renproject.io) connects blockchains and tokens through its trustless decentralised virtual machine that generates RenBTC. The REN protocol team has delivered this year launching renBTC well suited to become an industry standard. The blockchain bridge experience such as [bridge.renproject.io](https://bridge.renproject.io) and [wbtc.cafe](https://wbtc.cafe) are seamless.

****[**Smart Contract**](https://ethplorer.io/address/0x408e41876cccdc0f92210600ef50372656052a38?from=search#pageSize=100) **Risk: B**

Republic token is active and traded since December 2017 but has only recently launched with full functionalities. It has nearly 500 thousand transactions.&#x20;

**Counterparty Risk: B +**

Ren holds decentralisation and privacy at its core offering one of the most permissionless and transparent tools to tokenise assets from another blockchains. It’s got a community of 25,000 holders that can gain revenue by staking in dark nodes.

****[**Market**](https://www.coingecko.com/en/coins/enjin-coin) **Risk: B-**

REN has $300 million of market capitalisation and a decent amount of liquidity in big exchanges. Its recently witnessed some volatility with the launch of its core functionalities.&#x20;

### SNX

[Synthetix](https://www.synthetix.io) is a decentralised synthetic asset platform that provides trackers of multiple currencies including USD, EUR, GBP, as well as cryptocurrencies like BTC, ETH and BNB which are backed by Synthetix Network Tokens SNX locked in the respective contract.

[**SNX Smart contract**](https://ethplorer.io/address/0xc011a72400e58ecd99ee497cf89e3775d4bd732f) **Risk: B+**

SNX was first launched in March 2018 quickly building a community but reaching 200 thousand transactions.

**SNX Counterparty Risk: C+**

SNX is built on a decentralised infrastructure that has stayed robust while continuously innovating. Some security reports have highlighted undocumented functions in the Synthetix contracts that give some control to system maintainers and might present a security risk. If things go wrong it may be necessary to act fast and so these functions can be justified for the time being.

[**SNX Market**](https://coinmarketcap.com/currencies/synthetix-network-token/) **Risk: B-**

SNX price has shown strong growth in the last year. In parallel, the liquidity on exchanges has remained limited.

SNX holds the Synthetix ecosystem together as collateral with a collateralisation rate of 750%; it is transposed to Aave at the same level with a LTV of 15%.

### UNI&#x20;

UNI is the governance token of Uniswap Protocol, the DEX with the highest volume. It was distributed to users and liquidity providers gathering a diverse crowd of governors. The Uniswap DAO is now the DAO with the highest value under management.&#x20;

#### [UNI Smart Contract Risk](https://ethplorer.io/address/0x1f9840a85d5af5bf1d1762f925bdaddc4201f984?from=search#pageSize=100): B-&#x20;

The UNI token is audited and has been impressively battle tested, nearly 1.3 million transactions, for such a short life. The smart contract uses some of COMP’s token code which has been tested by the markets.&#x20;

#### UNI Counterparty Risk: B+&#x20;

UNI is a permissionless token launched in some of the fairest ways witnessed. The Uniswap team, which has an impressive track record, will be giving up power over the protocol gradually over the next months.&#x20;

#### UNI Market Risk: B

The UNI token has been really well received by the community. The price quickly increased from nothing then falling back down 50% leading to high volatility but also a large market capitalisation.&#x20;

### WBTC

[Wrapped Bitcoin](https://www.wbtc.network) is an attempt to bring Bitcoin to the Ethereum blockchain, by tokenising real bitcoin. The project responds to a real market demand since Bitcoin is the first and most successful cryptocurrency. The project was born in 2018 by the joint efforts of major players in the space: [Kyber Network](https://kyber.network), the [Ren Project](https://renproject.io) and [BitGo](https://www.bitgo.com).

[**WBTC Smart contract**](https://ethplorer.io/address/0x2260fac5e5542a773aa44fbcfedf7c193bc2c599#pageSize=100) **Risk: B+**

WBTC has only been available since January 2019 having yet to gain significant traction with just over 700 thousand transactions and $2.4 billion market capitalisation.

**WBTC Counterparty Risk: C**

WBTC is centralised with bitcoins custodially locked on the Bitcoin blockchain. The custody is performed by [BitGo](https://www.bitgo.com), a leader in blockchain custodian technologies.

[**WBTC Market**](https://coinmarketcap.com/currencies/wrapped-bitcoin/) **Risk: B+**

WBTC is not easily available, accessible on some DeFi platforms with a low volume. Redemption of WBTC for the underlying asset requires KYC and a merchant license by the WBTC consortium, and the liquidity on the market is relatively low. WBTC has suffered market [manipulation on Kyber exchange](https://www.trustnodes.com/2020/02/17/flashloan-haxor-sent-wbtcs-price-to-4000-on-kyber) leading to a 60% drop in price. Still WBTC tracks the price of BTC which is not too volatile compared to other currencies considered.

Since WBTC is backed by the first and most successful digital currency BTC we consider some of these risks mitigated by BTC’s wider market which we use as market feed for the protocol’s oracle.

### WETH

[Ethereum](https://ethereum.org) is not an ERC-20 token, leading to some missing functionality. [Wrapped ETH](https://weth.io) solves these compatibility issues with an ETH backed token which has gained traction within DeFi.&#x20;

[**WETH Smart contract**](https://ethplorer.io/address/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2) **Risk: A-**

Wrapped Ethereum emerged a couple of years after Ethereum. It has shown great use within the ecosystem reaching nearly 25 million transactions and over 100 thousand holders.

**WETH Counterparty Risk: A**

The process to wrap Ethereum is permissionless. Anyone can trade ETH with the[ relay smart contract](https://radarrelay.com) to get WETH. Similarly WETH can be unwrapped to get the ETH back. &#x20;

[**WETH Market** ](https://www.coingecko.com/en/coins/weth)**Risk: B+**

Wrapped Ethereum has a $3 billion market cap, among the highest market capitalisation and trading volumes of ERC tokens. Furthermore the price is pegged to Ethereum’s as it is redeemable for it. For this reason we consider the risks of WETH mitigate by ETH.

### XSUSHI

SushiSwap is a DEX forked of Uniswap that grew very fast, now at $1.6B of TVL, thanks to generous liquidity mining incentives. It is now part of the Yearn conglomerate with many new upcoming features.

xSUSHI is the staked SUSHI that receives .5% of the fees with 10 to 40% APY a great property for a collateral. The redeeming process from xSUSHI to SUSHI is permissionless allowing the analysis to focus on SUSHI.

[X**SUSHI Smart contract** ](https://ethplorer.io/address/0x8798249c2e607446efb7ad49ec89dd1865ff4272) **Risk: C-**

SUSHI was launched late August by a fork of the Uniswap Exchange with XSUSHI the fee accrual token launched in September. Shortly after launch, the key developer stole the development funds, eventually returning them. The network managed secure support from some industry leaders and has grown fast in these few month reaching two dozen users and over a billion transactions.

**XSUSHI Counterparty Risk: B**

Sushi is a permissionless blockchain protocol where token holders vote on incentives and upgrades. Anyone can create new Sushi markets.

[**SUSHI Market** ](https://www.coingecko.com/en/coins/sushi)**Risk: B-**

SUSHI has a good market capitalisation with a high volume. The price has suffered from extreme volatility since inception, suffering from large drops in value which is problematic for a collateral, requiring prudent parameters. This was driven by internal drama which also deeply affected community trust, now on the mend.

### YFI&#x20;

[Yearn](https://yearn.finance) is an ecosystem of financial products governed by the YFI token. The smart platform offers different optimised strategies based on DeFi primitives such as Aave, gaining immense traction and attracting nearly a billion dollars of AUM in just over a month.&#x20;

The governance token YFI is distributed to users who provide liquidity for the various products. The token holders discuss strategies and vote on policies in the governance forum while the technical side is led by Andrey Cronje.&#x20;

#### YFI [Smart contract Risk](https://etherscan.io/token/0x0bc529c00C6401aEF6D220BE8C6Ea1667F6Ad93e): B-+

The YFI smart contract was deployed on the 17th of July yet it already holds more transactions and holders than some other assets of portfolio. The simple ERC20 implementation with permissions only to the governance contract controlled by the YFI holders leads to a reduced technical risk&#x20;

#### YFI Counterparty Risk: B

YFI is fully decentralised, its distribution to Yearn liquidity providers is among the fairest and most transparent. The community is already strong of 6,000 holders.&#x20;

#### YFI Market Risk: B-

It is incredible to see the market metrics reached by YFI in just over a month. The monthly average 24h volume reaches nearly $700m. This has been accompanied by some of the most extreme price volatility observed even within the industry with the price surging from 50$ to 35,000$ leading to a high volatility risk.&#x20;

### ZRX

[0x](https://0x.org) allows fast and efficient currencies exchanges on Ethereum, in a secure and non-custodial manner through a system of relayers. The token, ZRX, is mostly used for governance and as a utility token throughout the platform.

[**ZRX Smart contract**](https://ethplorer.io/address/0xe41d2489571d322189246dafa5ebde1f4699f498#pageSize=100) **Risk: B+**

0x is one of the oldest projects on Ethereum, helping exchange ERC tokens since October 2016. The latest contract deployed in August 2017 now holds over 1.5 million transactions.

**ZRX Counterparty Risk: B+**

The project is completely decentralised and can continue to function even if the 0x team ceases to exist. It has a strong community with nearly 170,000 holders.

[**ZRX Market**](https://coinmarketcap.com/currencies/0x/) **Risk: B-**

It is traded on many exchanges and has a decent volume and rather low volatility.

## Asset Links

| Project      | Whitepaper                                                                                                                                       | Document portal                                                                                     | Source code                                                   | Ethereum address contract                                                                                                                 | Audit                                                                                                                              | Twitter                                                                |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| BUSD         | https://www.allcryptowhitepapers.com/binance-usd-whitepaper/                                                                                     | <p>https://www.binance.com/fr/busd<br><br> https://research.binance.com/en/projects/binance-usd</p> | https://github.com/binance-chain                              | 0x4fabb145d64652a948d72533023f6e7a623c7c53                                                                                                |                                                                                                                                    | [https://twitter.com/binance](https://twitter.com/binance)             |
| DAI          | https://makerdao.com/en/whitepaper                                                                                                               | https://docs.makerdao.com/                                                                          | https://github.com/makerdao                                   | 0x6b175474e89094c44da98b954eedeac495271d0f                                                                                                | https://github.com/makerdao/audits                                                                                                 | [https://twitter.com/makerdao](https://twitter.com/makerdao)           |
| GUSD         | https://www.gemini.com/static/dollar/gemini-dollar-whitepaper.pdf                                                                                | https://www.gemini.com/dollar                                                                       | https://github.com/gemini/dollar                              | 0x056fd409e1d7a124bd7017459dfea2f387b6d5cd                                                                                                | https://www.gemini.com/static/dollar/gemini-dollar-trailofbits-audit.pdf                                                           | https://twitter.com/gemini                                             |
| SUSD         | https://www.synthetix.io/uploads/synthetix\_litepaper.pdf                                                                                        | https://docs.synthetix.io/                                                                          | https://github.com/Synthetixio?language=tex                   | 0x6C85C5198C3CC4dB1b87Cb43b2674241a30f4845                                                                                                | https://docs.synthetix.io/contracts/audits/                                                                                        | [https://twitter.com/synthetix\_io](https://twitter.com/synthetix\_io) |
| TUSD         | https://www.trusttoken.com/about/                                                                                                                | https://www.trusttoken.com/                                                                         | https://github.com/trusttoken/smart-contracts                 | <p>Token address : 0x0000000000085d4780B73119b644AE5ecd22b376<br><br> Controller address : 0x0000000000075EfBeE23fe2de1bd0b7690883cc9</p> | https://drive.google.com/file/d/1pnrH72IHfdZClGy0GEMPwV-HdYk2gHN1/view                                                             | https://twitter.com/TrustToken                                         |
| USDC         | https://www.coinbase.com/usdc                                                                                                                    | https://www.centre.io/usdc                                                                          | https://github.com/coinbase                                   | 0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48                                                                                                | https://www.centre.io/usdc-transparency                                                                                            | https://twitter.com/centre\_io                                         |
| USDT         | https://tether.to/wp-content/uploads/2016/06/TetherWhitePaper.pdf                                                                                | https://tether.to/                                                                                  | https://github.com/shipshapecode/tether                       | 0xdac17f958d2ee523a2206206994597c13d831ec7                                                                                                |                                                                                                                                    | https://twitter.com/Tether\_to/                                        |
| Other Assets |                                                                                                                                                  |                                                                                                     |                                                               |                                                                                                                                           |                                                                                                                                    |                                                                        |
| AAVE         | [https://github.com/aave/protocol-v2/blob/master/aave-v2-whitepaper.pdf](https://github.com/aave/protocol-v2/blob/master/aave-v2-whitepaper.pdf) | <p>https://docs.aave.com/portal/<br><br> https://docs.aave.com/developers/</p>                      | https://github.com/aave                                       | 0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9                                                                                                | https://docs.aave.com/developers/security-and-audits                                                                               | https://twitter.com/aaveaave?lang=fr                                   |
| BAT          | https://basicattentiontoken.org/BasicAttentionTokenWhitePaper-4.pdf                                                                              | https://basicattentiontoken.org/faq/#meaning                                                        | https://github.com/brave-intl/basic-attention-token-crowdsale | 0x0d8775f648430679a709e98d2b0cb6250d2887ef                                                                                                | https://callisto.network/basic-attention-token-bat-security-audit/  https://blog.openzeppelin.com/basic-attention-token-bat-audit/ | https://twitter.com/attentiontoken                                     |
| CRV          | https://www.curve.fi/curve\_whitepapers/CurveDAO.pdf                                                                                             | https://resources.curve.fi/                                                                         | https://github.com/curvefi                                    | 0xD533a949740bb3306d119CC777fa900bA034cd52                                                                                                | https://dao.curve.fi/audits                                                                                                        | https://twitter.com/curvefinance?lang=en                               |
| ENJ          | https://docs.enjin.io/                                                                                                                           | https://docs.enjin.io/                                                                              | https://github.com/enjin/contracts                            | 0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c                                                                                                | https://s3.amazonaws.com/files.enjin.com/81/enjin-coin-audit.pdf                                                                   | https://twitter.com/enjin                                              |
| ETH          | https://ethereum.org/en/whitepaper/                                                                                                              | https://ethereum.org/en/developers/docs/                                                            | https://github.com/ethereum                                   | none                                                                                                                                      |                                                                                                                                    | https://twitter.com/ethereum                                           |
| KNC          | https://files.kyber.network/Kyber\_Protocol\_22\_April\_v0.1.pdf                                                                                 | https://developer.kyber.network/docs/Katalyst-Intro/                                                | https://github.com/kybernetwork                               | 0xdd974d5c2e2928dea5f71b9825b8b646686bd200                                                                                                | https://blog.kyber.network/                                                                                                        | https://twitter.com/kybernetwork                                       |
| LEND         | https://github.com/aave/aave-protocol/blob/master/docs/Aave\_Protocol\_Whitepaper\_v1\_0.pdf                                                     | https://docs.aave.com/developers/                                                                   | https://github.com/aave                                       | 0x80fB784B7eD66730e8b1DBd9820aFD29931aab03                                                                                                | https://docs.aave.com/developers/security-and-audits                                                                               | https://twitter.com/aaveaave?lang=fr                                   |
| LINK         | https://link.smartcontract.com/whitepaper                                                                                                        | https://docs.chain.link/docs                                                                        | https://github.com/smartcontractkit/chainlink                 | 0x514910771af9ca656af840dff83e8264ecf986ca                                                                                                | https://blog.chain.link/                                                                                                           | https://twitter.com/chainlink                                          |
| MANA         | https://decentraland.org/whitepaper.pdf                                                                                                          | https://docs.decentraland.org/                                                                      | https://github.com/decentraland                               | 0x0f5d2fb29fb7d3cfee444a200298f468908cc942                                                                                                | https://decentraland.org/blog                                                                                                      | https://twitter.com/decentraland                                       |
| MKR          | https://makerdao.com/en/whitepaper                                                                                                               | https://docs.makerdao.com/                                                                          | https://github.com/makerdao                                   | 0x9f8f72aa9304c8b593d555f12ef6589cc3a579a2                                                                                                | https://github.com/makerdao/audits                                                                                                 | [https://twitter.com/MakerDAO](https://twitter.com/MakerDAO)           |
| REN          | https://renproject.io/litepaper.pdf                                                                                                              | https://docs.renproject.io/ren/                                                                     | https://github.com/renproject                                 | 0x408e41876cccdc0f92210600ef50372656052a38                                                                                                | https://github.com/renproject/ren/wiki/Audits                                                                                      | [https://twitter.com/renprotocol](https://twitter.com/renprotocol)     |
| SNX          | https://docs.synthetix.io/litepaper/                                                                                                             | https://docs.synthetix.io/libraries/synthetix/                                                      | https://github.com/Synthetixio/synthetix                      | 0xc011a73ee8576fb46f5e1c5751ca3b9fe0af2a6f                                                                                                | https://docs.synthetix.io/contracts/audits/                                                                                        | https://twitter.com/synthetix\_io                                      |
| UNI          | https://www.uni-c.io/wp/UNI-Whitepaper\_EN.pdf                                                                                                   | https://uniswap.org/docs/v2/                                                                        | https://github.com/Uniswap                                    | 0x1f9840a85d5af5bf1d1762f925bdaddc4201f984                                                                                                | https://uniswap.org/audit.html                                                                                                     | https://twitter.com/UniswapProtocol                                    |
| WBTC         | https://wbtc.network/assets/wrapped-tokens-whitepaper.pdf                                                                                        | https://wbtc.network/                                                                               | https://github.com/WrappedBTC/bitcoin-token-smart-contracts   | 0x2260fac5e5542a773aa44fbcfedf7c193bc2c599                                                                                                | https://wbtc.network/dashboard/audit                                                                                               | https://twitter.com/WrappedBTC                                         |
| WETH         | https://weth.io/                                                                                                                                 | https://openbase.com/js/advanced-weth/documentation                                                 | https://github.com/Uniswap/advanced-weth                      | 0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2                                                                                                |                                                                                                                                    | none                                                                   |
| YFI          | https://yfnetworkdefi.com/wp-content/uploads/2020/10/Yearn-Finance-Network-Whitepaper2.1.pdf                                                     | https://docs.yearn.finance/                                                                         | https://github.com/iearn-finance                              | 0x0bc529c00c6401aef6d220be8c6ea1667f6ad93e                                                                                                | https://github.com/iearn-finance/yearn-audits                                                                                      | https://twitter.com/iearnfinance                                       |
| ZRX          | https://0x.org/pdfs/0x\_white\_paper.pdf                                                                                                         | https://0x.org/docs/guides                                                                          | https://github.com/0xProject                                  | 0xe41d2489571d322189246dafa5ebde1f4699f498                                                                                                | https://github.com/ConsenSys/0x-audit-report-2018-12/blob/master/0x-audit-2018-12-final.md                                         | https://twitter.com/0x\_Zrx                                            |

## Risk Monitoring



![Asset Risk Map as at 10/08/2021](<../.gitbook/assets/Screenshot 2021-08-10 at 15.54.30.png>)



![Asset Risk Map 24/02/2021](<../.gitbook/assets/Screenshot 2021-02-24 at 12.02.06.png>)

![Asset Risk Map 14/01/2021](<../.gitbook/assets/Screenshot 2021-01-14 at 17.34.51.png>)



![Asset Risk Map 1/12/2020](<../.gitbook/assets/Screenshot 2020-12-02 at 14.14.51.png>)



![Asset Risk Map as at 27/10/2020](<../.gitbook/assets/Screenshot 2020-10-28 at 14.09.32.png>)

Mid July to end of August 2020 has sustained extreme growth for Aave both in terms of the balance of assets within the protocol as well as the price of those assets. This has been followed by consolidation in October and the listing of new tokens such as the migrated AAVE.&#x20;

Small reduction in smart contract risk and counterparty risk due to an increase increased adoption of the assets in Aave’s Primary market leading to more tested smart contract and a more decentralised governance. &#x20;

Overall decrease in market risk driven by increased market cap and volume but accompanied by increased volatility risk. &#x20;

Between April and July the cryptocurrency market has experienced growth. The assets in Aave's portfolio have seen their market capitalisation explode as well as their usage. The parallel effect is an increase in volatility which is a crucial risk factor for the protocol.

![Asset risk map as of 1/4/2020](<../.gitbook/assets/01.04.20 Asset Risk Map.png>)
