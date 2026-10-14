# Algorithm methodology

## Overview

The initial AHorizon strategy is a long-only moving-average trend model. It evaluates whether an asset's closing price is sufficiently above its moving average to justify a candidate entry after estimated trading costs.

This is a methodology description, not investment advice or a promise of future results.

## Trend calculation

For a moving-average window of `N` daily observations:

```text
Moving average = sum of the most recent N closing prices / N
```

A price above the moving average indicates a positive trend. A price at or below the moving average indicates that the strategy should not maintain a long target.

## Fee-aware entry rule

AHorizon estimates the proportional cost of buying and later selling:

```text
Estimated round-trip friction =
    two-sided trading fees
  + full bid/ask spread
  + two-sided estimated slippage
  + two-sided currency-conversion cost, when applicable
```

The strategy adds a minimum expected-edge margin to that estimate:

```text
Required entry edge = estimated round-trip friction + safety margin
```

A new long entry is considered only when the closing price exceeds the moving average by the required entry edge.

The cost hurdle applies to new entries. It is not used to delay an exit when the trend condition is no longer satisfied.

## Position sizing

Candidate orders are constrained by applicable controls, which may include:

- Maximum position value.
- Target allocation.
- Maximum order value.
- Maximum order percentage of equity.
- Maximum total exposure.
- Required cash reserve.
- Daily order limits.
- Broker quantity and precision requirements.

The strictest applicable limit determines the maximum permitted order. Rounding is performed conservatively so an order does not exceed its approved size.

## Execution assumptions

The execution model can account for:

- Tiered or proportional commissions.
- Minimum ticket charges.
- Bid/ask spread.
- Slippage.
- Currency conversion.
- Quantity increments and minimum order sizes.
- Partial fills and unfilled limit orders.

Actual broker charges and execution quality may differ from modeled assumptions.

## Testing methodology

The strategy is evaluated using historical data and paper trading before supervised live testing. Tests may include out-of-sample periods, walk-forward evaluation, higher-cost assumptions, delayed signals, missing data, and simulated outages.

Backtests cannot fully reproduce live trading. Important limitations include data quality, changing market regimes, latency, liquidity, taxes, corporate actions, broker behavior, and future fee changes.

## Current limitations

- The initial model is deliberately simple and long-only.
- It may perform poorly in sideways or rapidly reversing markets.
- Fee estimates cannot predict exact future execution costs.
- Limit orders may fill partially or not at all.
- No algorithm can eliminate the possibility of loss.

