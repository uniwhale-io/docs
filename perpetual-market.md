# Perpetual Market

## Trade up to \[100]x

uniwhale.io offers perpetual futures with up to \[100]x leverage on a number of pairs including BTC-USD and ETH-USD.

All positions are margined in USD. Only isolated margining is currently offered with a plan to offer portfolio margining in the future.

Initiating positions will transfer the required margin to Exchange on-chain contract, which acts as the central counterparty and clearing house to all positions.

The initial margin is calculated based on the matched prices ("Mark Price").

Outstanding positions are subject to liquidation which may be triggered if the relevant liquidation price is breached according to the Price Oracle ("Index Price").

Keepers constantly monitor the positions to ensure positions eligible for liquidation are liquidated at the earliest chance, to protect the users and the platform.

If the position is liquidated and the user closes out the position, the settlement amount is determined based on the matched prices and is transferred by the Exchange to the user.

## Zero Fee to post orders

uniwhale.io, at its core, is about signed off-chain messages settled on-chain, which allows the CeFi-like orderbook experience for both traders and market makers.

Built as a classic central limit order book, signed orders are queued and matched for on-chain settlement.

Because these orders are created and signed off-chain, they require no gas fee.

The speed and latency of the order maching engine is also not constrained by the settlement blockchain, allowing horizontal scalability.

## Lightning quick on-chain settlement

The orders matched by the order matching engine are sent to the Exchange on-chain contract, which validates these orders and settles them on-chain.

By building on Sui, which boasts horizontally scalable, instant, finality with low fees, the settlement of trades is cost-efficient and quick.
