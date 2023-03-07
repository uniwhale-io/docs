---
cover: .gitbook/assets/Uniwhale_Gitbook_Cover_1900x400 (1).png
coverY: 0
---

# 🧙♂ Unique Oracle Design

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Mitigate harmful candlestick wicks&#x20;

Uniwhale does not require active market making by market makers, but instead relies on oracle prices to execute trades.

Oracle-based trade execution is designed specifically to mitigate harmful candlestick wicks, which so often liquidates, often unfairly, perpetual futures traders.

<figure><img src=".gitbook/assets/2022-11-22 08.32.31.jpg" alt=""><figcaption><p>Harmful candlestick wicks can wipe out levered long/short positions right before a significant rally/drop</p></figcaption></figure>

Such harmful wicks can be caused by many factors, but mainly we are concerned that these are often the result of illiquid/wrong/manipulated prices/pricing sources.

Oracle-based trade execution mitigates such harmful candlestick wicks because the oracle prices are published based on aggregate data contributed by multiple data sources. This makes it almost impossible to create such illiquid/wrong/manipulated prices/pricing sources-driven wicks.

## Pyth Network

Uniwhale uses [Pyth Network](https://pyth.network) for its oracle prices. Pyth Network is an oracle that publishes financial market data to multiple blockchains. Market data is contributed by over 70 [first-party publishers](https://pyth.network/publishers/), including some of the biggest exchanges and market making firms in the world. Each price feed publishes a [robust aggregate](https://docs.pyth.network/how-pyth-works/price-aggregation) of publisher prices that updates multiple times per second.

Pyth Network is different from many other oracles in that it uses ["on-demand" price update model](https://docs.pyth.network/consume-data/on-demand), whose advantages over the more traditional "push" model, among many, we like are:&#x20;

* Gas efficiency: **** On-chain prices are only updated when they are needed.
* High update frequency: **** Pyth Network price feeds update once per second, which is faster than the blocktime of most blockchains.
* Low latency: Every transaction can use a recent off-chain price, instead of relying on the last on-chain update pushed by the oracle itself.
* Reliable in volatile conditions: On-demand model does not fail to land price updates in volatile market conditions, because price updates are incorporated into the valuable transactions themselves (and therefore can compete for bandwidth).

### Latency

Any protocols dependent on oracles must account for the difference in latency between on-chain oracles and off-chain sources (e.g. centralized exchanges). No on-chain oracle can match the latency of an off-chain source due to the added overhead for consensus and security. Therefore, protocols must assume that there will be players who see price changes slightly before the protocol does. [Pyth Network](https://docs.pyth.network/consume-data/best-practices#latency) describes this situation as follows:

`This situation is analogous to market making in traditional finance. Market makers place resting orders on exchanges with the hope of earning the bid/ask spread. When the “true price” moves, these market makers get picked off by adverse “smart flow” that is faster than they are. The smart flow is balanced by two-way flow, that is, people wanting to trade for other reasons besides a price change.`\


The last sentence of the above quote is also important, because this relates to a key assumption of an oracle-based execution venue - that the objective oracle-based execution can create a better two-way flow, whose benefits then far outweigh its shortcoming. We then [tune the bid/ask spread and offered liquidity](execution.md#risk-management) to limit adverse selection from smart traders while still interacting with two-way flow.

Further, we give ourselves a "last look" to decide which trades to accept, based on the following conditions:

* Price is not stale: last slot update is not too far behind the current slot;
* Price is not negative;
* Price is not too volatile: EMA/spot ratio is less than 5, and;
* Price is not too uncertain: confidence internal is less than 10%

If Price do not meet the above conditions, then the trade is rejected.

### Price Availability

While Pyth Network provides a good protection against returning a stale price, the main public endpoints for its price service, operated by the Pyth Data Association, are centralized and therefore create risks for the protocols using its service.

The price service listens to the Wormhole Network (which has built in redundancy and is therefore inherently more reliable) for Pyth price updates and is a critical component used by Uniwhale Exchange app to fetch on-demand price updates.

To mitigate this risk, Uniwhale Exchange is built on its own custom network of 8 price services, whose weighted average (using the slot-weighted/inverse-confidence weighted scheme like [EMA price aggregation](https://docs.pyth.network/how-pyth-works/ema-price-aggregation)) is then submitted for on-chain price update and trading.&#x20;

Our custom price service network therefore provide for maximum resilience and decentralization.

### Oracle network health

You can monitor the health of Pyth Network at [Dune](https://dune.com/cctdaniel/pyth-oracle).

## What the future holds

Our oracle infrastructure is built to provide manipulation-resistant prices for trading with focus on latency and price availability.

We, however, also recognize that our entire infrastructure, built around Pyth Network, relies on a single oracle protocol, however decentralized it may be.

As part of the product roadmap, we are building a custom oracle aggregator based on multiple protocols (including Pyth) to determine trading prices.

By aggregating and filtering prices across multiple oracle protocols, our oracle aggregator can provide a price that is even more reliable with multiple redundancies.

###



