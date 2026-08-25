
## Coming soon

- Multiple accounts at once, each with its own Expert Advisors.
- Exchange-native stop-loss / take-profit on Binance (placed as real orders on the exchange).

## Roadmap 

- More backends.
- Charting — a built-in price chart to view bars, draw objects, and plot indicators on-chart.
- Linux and macOS support.
- MetaTrader 5 (MQL5) support — compile and run your MQL5 Expert Advisors and indicators, the
  way MQL4 works today (parsing MQL5 source, not just connecting to an MT5 broker).
- Data feeds — pair a trading account with a separate market-data feed (trade on one broker, take quotes from another).
- Linked accounts (copy-trading) — a signal on one account enters or exits the same trade across many linked accounts at once, in the same millisecond.

## Why run MT4 Expert Advisors through TFT?

Even when your broker is MetaTrader 4, running your Expert Advisors here adds things MetaTrader
itself does not give you:

- **Multiple accounts at once** — one terminal driving several MT4 accounts in parallel (coming soon).
- **Performance** — your EAs are compiled to native code, not interpreted; more on this in a later note.
- **Extra timeframes** — chart periods beyond MetaTrader 4's fixed set.
- **Broker + feed separation** — trade on your MT4 broker while taking quotes from a separate data
  feed (see *Roadmap — Data feeds*).

## Tips

- **Everything stays on your PC.** TFT operates no server and the Terminal sends
  us nothing — no telemetry, no analytics, no account registration. Your credentials,
  positions, trade history, Expert Advisors and logs live only in the Terminal's `Workdir`
  on your own machine; API keys and passwords are stored encrypted and are never uploaded
  anywhere. The Terminal connects to the network only for your own broker/exchange, update
  checks, and any notifications you configure yourself. (Full detail: SECURITY.md.)
- Your Expert Advisors, indicators and libraries live in `Workdir\MQL4`. They are kept
  across updates and are **never** removed on uninstall.
- Updates: the Terminal offers new versions itself (*Help -> Check for updates*). Your
  accounts, settings and Expert Advisors are preserved.
- Never share your `accounts.dat`, API keys or API secrets. Log files contain no keys, but
  they do contain account names and server addresses.


## Known limitations (current build)

- **Source code only (`.mq4`), not compiled `.ex4`.** The Terminal compiles the original MQL4
  source, so you need the `.mq4` file. Pre-compiled `.ex4` binaries (for example from the
  MetaTrader Market, or protected/encrypted Expert Advisors) cannot be loaded — there is no
  decompilation.
- **Binance stop-loss / take-profit are handled by the Terminal, not by the exchange.** There are three
  options:
    - **Internally** — S/L and T/P are monitored by TFT, and the position is closed automatically when the
      level is reached. This requires TFT to be running and connected, so it carries some execution risk.
    - **By Exchange** — native exchange-side S/L and T/P placement is planned for a future version.
    - **Manual** — full S/L and T/P can be attached manually through the Binance web terminal. However, this
      method is not available through the Binance API.
- **One account at a time.** The Terminal connects to and trades a single broker account.
  Running several accounts side by side is coming soon (see below).
- **Windows only.** A 64-bit Windows 10 or 11 is recommended (Linux and macOS are on the
  roadmap). Setup installs the .NET 10 Desktop Runtime, which supports current Windows 10/11
  (and matching Server) builds; older editions may work but are not tested. Use the 64-bit
  build unless an Expert Advisor `#import`s an old 32-bit DLL that cannot be recompiled for
  64-bit — those need the 32-bit build.

---

Beta software, under active development. Trading involves substantial risk of loss and is
not suitable for every investor; you are responsible for what your Expert Advisors do.
