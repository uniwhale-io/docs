# Unique Oracle Design

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Mitigate harmful candlestick wicks&#x20;

Uniwhale is building an oracle aggregator based on multiple service providers to determine trading prices.

The oracle aggregator is designed specifically to mitigate harmful candlestick wicks, which so often liquidates, often unfairly, perpetual futures traders.

<figure><img src=".gitbook/assets/2022-11-22 08.32.31.jpg" alt=""><figcaption><p>Harmful candlestick wicks can wipe out levered long/short positions right before a significant rally/drop</p></figcaption></figure>

Such harmful wicks can be caused by many factors, but mainly we are concerned that these are often the result of illiquid/wrong/manipulated prices/pricing sources.

By aggregating and filtering oracle prices across multiple service providers, our oracle aggregator can provide an oracle price that reflects better the true market activities.

