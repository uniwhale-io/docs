---
cover: .gitbook/assets/Uniwhale_Gitbook_Cover_1900x400 (2) (2).png
coverY: 0
---

# Liquidity Pool

## Democratization **of orderbook liquidity**&#x20;

Liquidity Pool democratizes orderbook liquidity by pooling liquidity providers into a single liquidity.

Based on the pooled liquidity, Liquidity Pool acts as the central counterparty and clearinghouse to all positions.

You can provide liquidity with a number of stablecoins (coming soon).

Oracle-based price execution means zero slippage.

Single-sided stablecoin liquidity means zero impermanent loss.

## Background

Our single-sided liquidity pool as the central counterparty to all positions at Uniwhale Exchange and its valuation proposition to liquidity providers are founded on the well-established academic research that demonstrates, over time, market makers win over short-term traders.

There are a number of academic literatures on this topic (for example, [Jordan and Diltz](https://www.jstor.org/stable/4480531) and [Barber et al.](https://faculty.haas.berkeley.edu/odean/papers/Day%20Traders/Day%20Trading%20and%20Learning%20110217.pdf))

In their paper, Barber et al. summarizes:

`the aggregate performance of day traders is negative, that the vast majority of day traders are unprofitable, and many persist despite an extensive experience of losses`

The above is then illustrated clearly in the chart below.

<figure><img src=".gitbook/assets/Screenshot 2022-12-13 at 3.37.32 PM.png" alt=""><figcaption><p>Do Day Traders Rationally Learn About Their Ability? Barber et al.</p></figcaption></figure>

Compared to providing liquidity to AMMs, we make it possible for liquidity providers to provide liquidity against a pattern of trading that has been extensively analysed by the academia to show that liquidity providers will win.

An important point to note, however, is that this does not mean traders necessarily have to lose, quite the opposite. Liquidity providers take positions against all trades, whereas a trader takes one (or more) of the opposite of those positions. So liquidity providers are betting against the market, whereas a trader is betting against a specific event. So long as the market behaves as expected, the liquidity providers win (as the history demonstrates above). So long as specific events behave as expected, the trader wins.

## Provide liquidity the way you want it and earn passive yield

You can provide liquidity to the orderbook, either directly by posting limit orders, or by pooling your assets with others into Liquidity Pool.

Liquidity Pool thus provides a convenient way to earn passive real yield (trading fees) from market making and leverage trading.

## Provide single-sided liquidity with stablecoins

The design of the Liquidity Pool allows the market making of the orderbook at a fixed / pre-determined fee, with zero slippage, benefitting both traders and liquidity providers.

Liquidity Pool uses our oracle aggregator to determine its mid-price and apply a fixed fee based on a pre-determined rule to create bid and ask, which are then used to fill the market limit orders on the orderbook. See [Fee and Market Impact](execution.md#fee-and-market-impact).

The Liquidity Pool accepts a number of stablecoins (coming soon). Liquidity Pool tokens can be minted using any of these stablecoins and burnt to redeem any of these. The price at which the Liquidity Pool token is minted or burnt is determined based on the total market value of the Liquidity Pool divided by the outstanding supply of the token.&#x20;

Since the counterparty of all trades is the Liquidity Pool, this is a zero-sum game between liquidity providers and traders: the traders’ profit and losses will be directly transferred from/to the Liquidity Pool (resulting in a price increase/decrease of the Liquidity Pool token).

### Adding liquidity

You can provide liquidity to Uniwhale Exchange either with USDT or with other stablecoins (coming soon). If other stablecoins are provided, they are swapped into USDT using a third-party DEX (e.g. Uniswap), with the minimum amount of USDT (i.e. maximum slippage) specified by you.

The number of Liquidity Pool tokens minted in return is proportional to the amount of USDT you provide relative to the USDT balance Liquidity Pool holds.

### Removing liquidity

You can remove liquidity from Uniwhale Exchange at any time either in USDT or in other stablecoins (coming soon). If in other stablecoins, the relevant BUSD is swapped into the stablecoin using a third-party DEX (e.g. Uniswap), with the minimum amount of the stablecoin (i.e. maximum slippage) specified by you.

Because the Liquidity Pool balance must be sufficiently collateralized to meet all its obligations (see [Risk management](execution.md#risk-management)), the maximum liquidity you can remove at any time is restricted to the excess balance available (i.e. the difference between the Liquidity Pool balance and the collateral requirement).

The amount of BUSD or the stablecoin received in return is proportional to the amount of the Liquidity Pool tokens burnt relative to the outstanding supply of the token.
