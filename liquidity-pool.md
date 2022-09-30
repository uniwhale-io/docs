# Liquidity Pool

## Provide the liquidity the way you want it and earn

At uniwhale.io, market makers can provide liquidity to the orderbook, either directly by posting limit orders, or by pooling their assets into Liquidity Pool.

Liquidity Pool thus provides a convenient way for many to earn trading fees by providing liquidity.

### Mint / Burn of Liquidity Pool token

The Liquidity Pool consists of a basket of assets used for trading. Liquidity Pool token can be minted using any asset in the basket and burnt to redeem any of the assets. The price at which the Liquidity Pool token is minted or burnt is determined based on the total market value of the Liquidity Pool divided by the outstanding supply of the token.

## Zero price impact trading

The design of the Liquidity Pool allows that liquidity is provided at a fixed / pre-determined fee, with zero slippage, benefitting both traders and liquidity providers.

Liquidity Pool uses Price Oracle to determine its mid-price and apply a fixed fee based on a pre-determined rule to create its bid and ask, which are then used to fill the market limit orders on the orderbook.

### Oracle-based mid-price calculation

Liquidity Protocol uses Red Stone Price Oracle, which provides fast and cost-efficient price oracles for on-chain contracts.

Keepers constantly refreshes the oracle prices and update the Liquidity Pool.

Liquidity Pool uses the trailing average and percentile of the oracle prices to determine its mid-price.

### Dynamic fee calculation

When a particular asset is in heavy demand, its weight within the Liquidity Pool may decrease, and, vice versa.

The fee is adjusted based on the prevailing weight to ensure Liquidity Pool holds a balanced basket of assets

### Market Limit Order

Market limit orders are filled by Keepers when the Oracle Price reaches the limit price.

### Market Order

Market orders are filled by Keepers at the Oracle Price.
