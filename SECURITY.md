# Security Policy

TradingForge Terminal connects to live brokerage and exchange accounts. A flaw here can cost someone
money, so please report one privately rather than publicly.

## Reporting a vulnerability

**Use [Report a vulnerability](https://github.com/TradingForge/TFT-releases/security/advisories/new)** —
a private channel only you and the maintainers can see.
If that page is unavailable, email **tradingforge@gmail.com** with `SECURITY` in the subject.

**Please do not open a public issue or discussion for a security problem.** Every published version stays
installed on users' machines until they update; a public report tells everyone what to exploit while those
installations are still vulnerable.

## Your data stays on your machine

**TradingForge operates no server, and the Terminal sends us nothing.** There is no telemetry, no
analytics and no account registration. Your credentials, positions, trade history, Expert Advisors and
logs live only in the Terminal's `Workdir` on your own PC; API keys and passwords are stored encrypted
and are never uploaded anywhere.

The Terminal makes network connections only for:

- **Your broker or exchange** — the account you connected, over its own API
- **MetaTrader 4 accounts** — during login the MT4 connectivity library also contacts its vendor's
  login-id service (`loginid-mt4.mtapi.io`), resolving it through Cloudflare DNS-over-HTTPS. This is part
  of how MT4 connectivity works and is not operated by us
- **Update checks** — a request to this GitHub repository for the current version; it carries no
  information about you or your accounts
- **Notifications** — Telegram or email, only if you configure them yourself
- **Your own Expert Advisors** — anything they request, and only if you allow web requests in the options

## What we consider in scope

- The Terminal itself, the installer, and the built-in update mechanism
- Handling of stored credentials, API keys and log contents
- Anything that lets one account's data or actions reach another

Out of scope: bugs in Expert Advisors you or third parties wrote, broker and exchange APIs themselves,
and anything that requires an attacker to already control the machine the Terminal runs on.

## What to expect

This is a small team and the product is in beta, so these are intentions rather than guarantees:

- We aim to acknowledge a report within a few days
- Confirmed issues are fixed in the next release; severe ones get a release of their own
- Release notes describe security fixes only in general terms until users have had time to update,
  and the specifics follow afterwards
- We will credit you if you want to be credited

There is no paid bug bounty.

## Supported versions

Only the **latest release** receives fixes. Older versions are not patched — update first, then report if
the problem persists.
