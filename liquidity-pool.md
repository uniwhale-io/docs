---
cover: .gitbook/assets/Uniwhale_Gitbook_Cover_1900x400.png
coverY: 0
---

# Liquidity Pool

## Democratization **of orderbook liquidity**&#x20;

At Uniwhale, you can provide liquidity with a number of stablecoins (USDC, USDT, DAI, etc). The objective price oracle and single-sided liquidity protect liquidity providers from impermanent loss.

* Oracle-based price execution means zero slippage.
* Single-sided stablecoin liquidity means zero impermanent loss.

## Provide liquidity the way you want it and earn passive yield

You can provide liquidity to the orderbook, either directly by posting limit orders, or by pooling your assets with others into Liquidity Pool.

Uniwhale Liquidity Pool thus provides a convenient way to earn passive real yield (trading fees) from market making and leverage trading.

## Provide single-sided liquidity with stablecoins

The design of the Liquidity Pool allows the market making of the orderbook at a fixed / pre-determined fee, with zero slippage, benefitting both traders and liquidity providers.

Liquidity Pool uses our oracle aggregator to determine its mid-price and apply a fixed fee based on a pre-determined rule to create bid and ask, which are then used to fill the market limit orders on the orderbook.

The Liquidity Pool accepts a number of stablecoins. Liquidity Pool tokens can be minted using any of these stablecoins and burnt to redeem any of these. The price at which the Liquidity Pool token is minted or burnt is determined based on the total market value of the Liquidity Pool divided by the outstanding supply of the token.&#x20;

Since the counterparty of all trades is the Liquidity Pool, this is a zero-sum game between liquidity providers and traders: the traders’ profit and losses will be directly transferred from/to the Liquidity Pool (resulting in a price increase/decrease of the Liquidity Pool token).
