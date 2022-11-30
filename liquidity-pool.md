---
cover: .gitbook/assets/Uniwhale_Gitbook_Cover_1900x400 (2) (2).png
coverY: 0
---

# Liquidity Pool

## Democratization **of orderbook liquidity**&#x20;

Liquidity Pool democratizes orderbook liquidity by pooling liquidity providers into a single liquidity.

Based on the pooled liquidity, Liquidity Pool acts as the central counterparty and clearinghouse to all positions.

You can provide liquidity with a number of stablecoins (USDC, USDT, DAI, etc).

Oracle-based price execution means zero slippage.

Single-sided stablecoin liquidity means zero impermanent loss.

## Provide liquidity the way you want it and earn passive yield

You can provide liquidity to the orderbook, either directly by posting limit orders, or by pooling your assets with others into Liquidity Pool.

Liquidity Pool thus provides a convenient way to earn passive real yield (trading fees) from market making and leverage trading.

## Provide single-sided liquidity with stablecoins

The design of the Liquidity Pool allows the market making of the orderbook at a fixed / pre-determined fee, with zero slippage, benefitting both traders and liquidity providers.

Liquidity Pool uses our oracle aggregator to determine its mid-price and apply a fixed fee based on a pre-determined rule to create bid and ask, which are then used to fill the market limit orders on the orderbook. See [Fee and Market Impact](execution.md#fee-and-market-impact).

The Liquidity Pool accepts a number of stablecoins. Liquidity Pool tokens can be minted using any of these stablecoins and burnt to redeem any of these. The price at which the Liquidity Pool token is minted or burnt is determined based on the total market value of the Liquidity Pool divided by the outstanding supply of the token.&#x20;

Since the counterparty of all trades is the Liquidity Pool, this is a zero-sum game between liquidity providers and traders: the traders’ profit and losses will be directly transferred from/to the Liquidity Pool (resulting in a price increase/decrease of the Liquidity Pool token).

### Adding liquidity

You can provide liquidity to Uniwhale Exchange either with USDC or with other stablecoins. If other stablecoins are provided, they are swapped into USDC using a third-party DEX (e.g. Pancake Swap), with the minimum amount of USDC (i.e. maximum slippage) specified by you.

The number of Liquidity Pool tokens minted in return is proportional to the amount of USDC you provide relative to the USDC balance Liquidity Pool holds.

### Removing liquidity

You can remove liquidity from Uniwhale Exchange any time either in USDC or in other stablecoins. If in other stablecoins, the relevant USDC is swapped into the stablecoin using a third-party DEX (e.g. Pancake Swap), with the mininum amount of the stablecoin (i.e. maximum slippage) specified by you.

Because Liquidity Pool balance must be sufficiently collateralized to meet all its obligations (see [Risk management](execution.md#risk-management)), the maximum liquidity you can remove at any time is restricted to the excess balance available (i.e. the difference between the Liqudity Pool balance and the collateral requirement).

The amount of USDC or the stablecoin received in return is proportional to the amount of the Liquidity Pool tokens burnt relative to the outstanding supply of the token.
