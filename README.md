# AHorizon Algorithmic Trading Platform

AHorizon is a fee-aware algorithmic trading platform for testing and supervising automated strategies across stocks, ETFs, and cryptocurrency.

The platform is being developed around four principles:

- Start with paper trading before using real money.
- Keep customers in control of their own broker accounts.
- Include estimated fees, spread, and slippage in trading decisions.
- Apply strict risk limits and explicit activation steps to live trading.

## Current integrations

- Interactive Brokers for eligible stocks and ETFs, including eligible fractional shares.
- Kraken Pro for cryptocurrency trading.
- A paper-trading environment for testing without real funds.

## Fee-aware decisions

AHorizon requires a candidate entry signal to exceed estimated round-trip trading friction plus an additional safety margin. The calculation can include entry and exit fees, bid/ask spread, slippage, and currency-conversion costs.

This filter is intended to avoid trades whose modeled advantage is too small to cover expected costs. It does not guarantee that a trade will be profitable or that actual costs will match estimates.

## Customer workflow

1. Create an AHorizon account and enable multi-factor authentication.
2. Explore the portal and test the strategy in paper mode.
3. Connect a personally controlled broker or exchange account.
4. Complete a read-only connection check.
5. Review the strategy, modeled costs, and risk limits.
6. Use a supervised, limited pilot before considering scheduled execution.

Connecting a broker does not automatically activate live trading. AHorizon is designed without broker withdrawal permission.

## Documentation

- [Platform overview](docs/PLATFORM_OVERVIEW.md)
- [Algorithm methodology](docs/ALGORITHM_METHODOLOGY.md)
- [Security overview](SECURITY.md)
- [Risk disclaimer](DISCLAIMER.md)

## Project status

AHorizon is under active development and evaluation. This public repository contains product and methodology documentation. The production source code, deployment configuration, and security-sensitive implementation remain private.

## Contact

- Website: [ahorizon.ca](https://ahorizon.ca)
- Application: [app.ahorizon.ca](https://app.ahorizon.ca)
- Email: contact@ahorizon.ca

Copyright © 2026 AHorizon. All rights reserved.

