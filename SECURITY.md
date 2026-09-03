# Security

## We are not responsible for your trading

TradingForge Terminal is a tool. Every order it places is placed because you or your Expert Advisor
asked for it. Trading involves substantial risk of loss and is not suitable for every investor, and
automated trading can lose money faster than manual trading.

You are responsible for what your Expert Advisors do, for the settings you give them, and for the
accounts you connect. Test on a demo or testnet account first.

## We collect nothing

**TradingForge operates no server, and the Terminal sends us nothing.** No telemetry, no analytics, no
account registration. Your credentials, positions, trade history, Expert Advisors and logs live only in
the Terminal's `Workdir` on your own PC; API keys and passwords are stored encrypted and are never
uploaded anywhere.

The Terminal connects to the network only for:

- **Your broker or exchange** — the account you connected, over its own API
- **Update checks** — a request to this repository for the current version; it carries no information
  about you or your accounts
- **Notifications** — Telegram or email, only if you configure them yourself
- **Your own Expert Advisors** — anything they request, and only if you allow web requests in the options

## Bugs are fixed in coming updates

Report anything that looks wrong in [Issues](https://github.com/TradingForge/TFT-releases/issues), and
ask questions in [Discussions](https://github.com/TradingForge/TFT-releases/discussions). Fixes ship in
the next release; the Terminal will offer it to you itself.

Only the **latest release** receives fixes — update first, then report if the problem persists.

> Issues and Discussions are public. **Never paste API keys, API secrets, passwords or your
> `accounts.dat`.** Log files contain no keys, but they do contain account names and server addresses.
