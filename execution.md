# Trading



<figure><img src=".gitbook/assets/section_trade (1).png" alt=""><figcaption></figcaption></figure>

## Trade up to 200X

We offer perpetual futures with up to 200X leverage on BTC, ETH, and many mainstream crypto assets.

## Keep your assets safe

We do not custody your assets. Your assets stay with you and the margins posted are locked in a dedicated smart contract.

## Margining

All positions are margined in BUSD. Both isolated and portfolio margining will be supported.&#x20;

You can add and remove margins to outstanding positions. When margins are updated to an outstanding position, the relevant liquidation price is also adjusted.

Multiple stablecoins are accepted as eligible margins. These will be swapped automatically to BUSD.

## Order type supported

You can trade either Market Order or Market Limit Order. Both order types can also have either Stop Loss, Profit Target, or both.

### Market Order

Market orders are filled at the best price offered by the [Liquidity Pool](liquidity-pool.md).

### Market Limit Order (coming soon)

Market limit orders are filled when the limit prices match the best price offered by the [Liquidity Pool](liquidity-pool.md).

### Stop Loss

Stop Loss price can be added to Market Order or Market Limit Order, which will trigger an automatic close of the position if the condition is satisfied.

### Profit Target

Profit Target price can be added to the Market Order or Market Limit Order, which will trigger an automatic close of the position if the condition is satisfied.

## Fee and Market Impact

Prices offered by the [Liquidity Pool](liquidity-pool.md) embed two types of transaction costs - Fee and Market Impact.

`Long/Short Open Price = Oracle Price x (1 +/- Fee +/- Market Impact)`

`Long/Short Close Price = Oracle Price x (1 -/+ Fee -/+ Market Impact)`

### Fee

Fee is 0.10%.

### Market Impact

Market Impact is calculated dynamically as a function of outstanding positions on the platform and the position size. It is a deterministic charge simulating the impact a new position would have on the market.

`Market Impact (%) = (long/short outstanding positions on the platform + Position size) / 1% depth above/below`

`1% depth above/below` is benchmarked to the corresponding liquidity at leading exchanges and regularly updated.

## Funding and Rollover Fee

Outstanding positions are subject to Funding Fee and Rollover Fee.&#x20;

### Funding Fee

Funding Fee is a dynamic fee charged per block-height that is based on the long/short outstanding position imbalance on the platform and is charged on the position size (i.e. your margin multiplied by the leverage).&#x20;

Funding Fee can be positive or negative, depending on your position relative to the position imbalance on the platform. Generally speaking, you are paid Funding Fee to take a contrarian view, and pay Funding Fee to take a consensus view.&#x20;

Funding Fee protects the platform and the liquidity providers by helping balance the long/short outstanding positions.

`Long Funding Fee Per Block (%) = Base Fee Per Block x (long outstanding position on the platform - short outstanding position on the platform) / long outstanding position on the platform`

`Short Funding Fee Per Block (%) = Base Fee Per Block x (short outstanding position on the platform - long outstanding position on the platform) / short outstanding position on the platform`

`Base Fee Per Block` is different for each crypto asset and is updated periodically.

The definitions above mean the total Long Funding Fee per block always equals the total Short Funding Fee per block, i.e. this is a transmission mechanism by which traders with consensus view pay traders with contrarian view. Therefore, no Funding Fee is paid to the platform or the liquidity providers.

### Rollover Fee

Rollover Fee is a fixed fee charged per block-height on your margin. Because it is charged on your margin, the higher the leverage, the less significant the Rollover Fee is to your overall position. Rollover Fee protects the platform and the liquidity providers by helping level the risk of lower leverage positions with that of higher leverage positions.

`Rollover Fee per Block (%) = Base Fee Per Block x position margin`

`Base Fee Per Block` is different for each crypto asset and is updated periodically.

## Opening a position

<figure><img src=".gitbook/assets/Screenshot 2022-12-18 at 10.58.26 AM.png" alt=""><figcaption></figcaption></figure>

Opening a position will transfer the required margin to a dedicated on-chain contract, whose sole purpose is to hold trader margins.

[Liquidity Pool](liquidity-pool.md) which acts as the central counterparty and clearinghouse to all positions.

To open a position, you need to enter the margin you want to put up together with the leverage you are looking for.

You can post margin in many stablecoins, which will then be automatically swapped into BUSD using a third-party DEX (e.g. PancakeSwap), with the maximum amount of the stablecoin to meet the BUSD margin requirement specified by you.

### Slippage setting

Your execution price is deterministically calculated (see [Fee and Market Impact](execution.md#fee-and-market-impact)) based on the latest oracle price, but, especially during a fast moving market, there can be a gap between the screen price and the actual execution price (primarily due to changes in oracle price and outstanding positions on the platform).&#x20;

To mitigate this risk, you can specify Slippage when opening a position, so that the actual execution meets your execution price requirement.

## Closing a position

<figure><img src=".gitbook/assets/Screenshot 2022-12-18 at 11.06.06 AM.png" alt=""><figcaption></figcaption></figure>

Closing a position will calculate the PnL based on the best price offered by the Liquidity Pool and transfer it to the trader, together with the margin posted.&#x20;

You may request the PnL to be transferred in a stablecoin other than BUSD, in which case the PnL (together with the margin) will be swapped into the requested stablecoin using a third-party DEX (e.g. PancakeSwap), with the minimum amount of the stablecoin specified by you, and transferred to you.

You can not lose more than the margin posted.&#x20;

### Limit Price or Market Price

Your execution price is deterministically calculated (see [Fee and Market Impact](execution.md#fee-and-market-impact)) based on the latest oracle price, but, especially during a fast moving market, there can be a gap between the screen price and the actual execution price (primarily due to changes in oracle price and outstanding positions on the platform).&#x20;

To mitigate this risk, you can specify Limit Price when closing a position, so that the actual execution meets your execution price requirement. Specifying a Market Price will simply accept the actual execution price.

## Liquidation

Outstanding positions are subject to liquidation if the relevant liquidation price is breached according to the price oracle ("Index Price").

Outstanding positions eligible for liquidation are liquidated at the earliest chance, to protect the users and the platform.

Liquidation closes the relevant position. It is subject to a liquidation penalty. In order to avoid the liquidation penalty, traders are advised to close a position before liquidation is triggered.

## Risk management

Trading at uniwhale is subject to the following constraints:

* Leverage cannot exceed a cap.
* The number of open positions for each pair a trader can carry is capped.
* The number of open positions across pairs a trade can carry is capped.
* The total margin across pairs a trader can carry is capped.
* There is a minimum position (after leverage) required.
* A position is subject to the maximum percentage PnL, determined as a function of your margin and leverage (see [Maximum Percentage PnL](execution.md#maximum-percentage-pnl)).
* The maximum possible PnL of all open positions (long and short) across the platform cannot exceed the prevailing market value of Liquidity Pool.

### Maximum Percentage PnL

At Uniwhale, we must ensure that the platform always stays solvent as positions are opened and closed. That means the counterparty to all the trades, ie. the Liquidity Pool, must be able to meet the maximum possible PnL of all open positions (long and short) across the platform.

Because the maximum possible PnL of long/short open positions, by default, is unlimited/very large, respectively, we apply so-called "Maximum Percentage PnL" to each position, which limits the maximum possible PnL of each position and therefore allows us to determine the maximum possible PnL of all open positions.

To determine Maximum Percentage PnL, we take into consideration the leverage of a position, and the higher the leverage a position has, the higher its Maximum Percentage PnL subject to a cap and a floor, i.e.

`Maximum Percentage PnL = Max(Floor, Min(Cap, Leverage / Maximum Percentage PnL Factor))`

The above makes sense because generally you would expect a higher potential return with a higher leverage than with a lower leverage.&#x20;

It also allows the Liquidity Pool to run a far better capital efficiency because the pool then allocates relatively (per leverage) more capital to those with higher leverage than those with lower leverage.

