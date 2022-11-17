# Liquidity Pool

## Access to **the democracy of orderbook liquidity**&#x20;

<mark style="color:green;">Uniwhale allows users to provide liquidity by using multi-stable coins(USDC/USDT/DAI). The accurate price oracle and single-sided liquidity make sure liquidity providers get away from unnecessary impermanent loss.</mark>

* <mark style="color:green;">Oracle-based liquidity pool to enable zero slippage</mark>&#x20;
* <mark style="color:green;">Single-sided liquidity enables 0 impermanent loss.</mark>

## Provide liquidity the way you want it and #EARN PASSIVE YIELD(risk-neutral)

<mark style="color:green;">You can provide liquidity to the orderbook, either directly by posting limit orders, or by pooling your assets with others into Liquidity Pool.</mark>

Uniwhale Liquidity Pool thus provides a convenient way to earn <mark style="color:red;">**Passive Real Yield**</mark> (trading fees) from market making and leverage trading.

#### Oracle-based Liquidity Pool&#x20;

The Oracle-based Liquidity Pool consists of a basket of mainstream assets used for trading. Liquidity Pool tokens can be minted using any asset in the basket and burnt to redeem any of the assets. The price at which the Liquidity Pool token is minted or burnt is determined based on the total market value of the Liquidity Pool divided by the outstanding supply of the token.

## How to provide stable coin liquidity

The design of the Oracle-based Liquidity Pool allows liquidity provided at a fixed / pre-determined fee, with zero slippage, benefitting both traders and liquidity providers.

Liquidity Pool uses Price Oracle to determine its mid-price and apply a fixed fee based on a pre-determined rule to create its bid and ask, which are then used to fill the market limit orders on the orderbook.

####

#### Dynamic fee calculation

<mark style="color:green;">When a particular asset is in heavy demand, its weight within the Liquidity Pool may decrease, and, vice versa.</mark>

<mark style="color:green;">The fee is adjusted based on the prevailing weight to ensure Liquidity Pool holds a balanced basket of assets</mark>

#### Market Limit Order

Market limit orders are filled by Keepers when the matching price reaches the limit price.

#### Market Order

Market orders are filled by Keepers at the best price offered by the Uniwhale match engine.
