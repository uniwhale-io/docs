# Best Execution

## Trade up to 200X

We offer perpetual futures with up to 200X leverage on BTC, ETH, and more mainstream crypto assets directly from your wallet.

All positions are margined in USD. Both <mark style="color:red;">**Isolated Margining**</mark> and <mark style="color:red;">**Portfolio Margining**</mark> will be supported.

Initiating positions will transfer the required margin to Exchange on-chain contract, which acts as the central counterparty and clearing house to all positions.

The initial margin is calculated based on the matched prices ("Mark Price").

Outstanding positions are subject to liquidation which may be triggered if the relevant liquidation price is breached according to the Price Oracle ("Index Price").

Keepers constantly monitor the positions to ensure positions eligible for liquidation are liquidated at the earliest chance, to protect the users and the platform.

If the position is liquidated and you close out the position, the settlement amount is determined based on the matched prices and is transferred by the Exchange to you.

## Best Price Oracles

<mark style="color:green;">We, at the core, are about signed off-chain messages settled on-chain, which allows the CeFi-like orderbook experience for both traders and market makers.</mark>

<mark style="color:green;">Built as a classic central limit order book, signed orders are queued and matched for on-chain settlement.</mark>

<mark style="color:green;">Because these orders are created and signed off-chain, they require no gas fee.</mark>

<mark style="color:green;">The speed and latency of the order-matching engine are also not constrained by the settlement blockchain, allowing horizontal scalability.</mark>

## Lightning-quick on-chain settlement

The orders matched by the order matching engine are sent to the Exchange on-chain contract, which validates these orders and settles them on-chain.

By building on EVM, which boasts horizontally scalable, instant, finality with low fees, the settlement of trades is cost-efficient and lightning-quick.
