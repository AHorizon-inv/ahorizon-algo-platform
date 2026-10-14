# Security overview

AHorizon follows a least-privilege approach to broker connections and live-trading activation.

## Broker permissions

AHorizon broker credentials should allow only the account queries and trading operations required by the platform. Withdrawal permission must not be granted.

## Account protection

The platform uses password protection, multi-factor authentication, encrypted storage for broker credentials, session protections, re-authentication for sensitive actions, and role-based access controls.

## Live-trading controls

Live trading is separated from broker connection setup. Activation requires additional verification and acknowledgement steps. Customers can pause their own automation.

## Reporting a security issue

Do not report a suspected vulnerability in a public GitHub issue.

Email `contact@ahorizon.ca` with:

- A description of the issue.
- Steps required to reproduce it.
- The potential impact.
- Any relevant non-sensitive logs or screenshots.

Do not include passwords, authentication codes, API secrets, private keys, recovery codes, personal identity documents, or customer financial information.

Implementation details and production infrastructure are intentionally excluded from this public repository.

