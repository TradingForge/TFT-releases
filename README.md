# TradingForge Terminal

> **Keep your MQL4 strategy. Change everything behind it.**

Run your existing MQL4 Expert Advisors across supported trading platforms—without rewriting the strategy and without running a MetaTrader terminal or a third-party bridge in the middle.

**One strategy. Multiple markets. Direct execution.**

[![Watch TFT run an MQL4 strategy live on Binance](assets/github_screen.png)](VIDEO_URL)

In the demo, a simple EMA crossover strategy is compiled in TFT, verified in the MT4 Strategy Tester, and then launched on Binance. When the signal arrives, TFT opens the position and it appears immediately in the Binance web terminal.

## Why TFT

- **Keep your MQL4 code** — run the same `.mq4` strategy logic across supported platforms.
- **Compiled performance** — TFT transpiles MQL4 to .NET code, which is JIT-compiled to native machine code at runtime. In our measured test, the complete local tick-to-trade path had a median latency of 0.590 ms (590 microseconds).
- **Direct execution** — connect to the broker or exchange API without a MetaTrader bridge in the middle.
- **Extra timeframes** — use chart periods beyond MT4's fixed set across supported backends.
- **Multi-account execution is coming** — run strategies across multiple accounts and different platforms from one terminal.
- **Broker/feed separation is planned** — use a fast or high-quality market-data feed while sending trades through a different broker.
- **Linked accounts are planned** — copy the same strategy action across a group of accounts.

## How it works

<div align="center">
	<img src="assets/pipeline.png" alt="MQL4 EA source is transformed into C# by the TFT Transpiler, compiled and run by the TFT Runtime, and connected to a broker, exchange, or trading API" width="880">
</div>

TFT transforms your MQL4 source into executable C# and compiles it. The TFT Runtime executes the strategy, while the selected backend handles market data, account state, and orders for the connected broker or exchange.

Your source is compiled by TFT. The MQL4 standard-library runtime is implemented by TFT, allowing supported Expert Advisors to run without MetaTrader being present at runtime.

## Platform status

```text
┌────────────────────────┐                                     ┌── MT4 accounts          [AVAILABLE]
│ MQL4 EA  [AVAILABLE]   │──┐                                  ├── Binance Futures       [AVAILABLE]
└────────────────────────┘  │                                  ├── cTrader               [IN DEVELOPMENT]
                            │                                  ├── Interactive Brokers   [IN DEVELOPMENT]
┌────────────────────────┐  │    ┌──────────────────────────┐  ├── Additional exchanges  [ROADMAP]
│ MQL5 EA    [ROADMAP]   │──┼──> │  TradingForge Terminal   │──┤
└────────────────────────┘  │    │  Extensible backends     │  ├── FIX-protocol brokers  [ROADMAP]
                            │    └──────────────────────────┘  ├── Proprietary APIs      [ROADMAP]
┌────────────────────────┐  │                                  ├── DEX / DeFi            [ROADMAP]
│ Custom Script [ROADMAP]│──┘                                  └── Custom backends       [ROADMAP]
└────────────────────────┘
```

The current release runs one connected account at a time. Multi-account execution across accounts and platforms is the next major step.

## Performance — compiled execution

TFT runs MQL as compiled .NET code that is JIT-compiled to native machine code. To measure the complete local tick-to-trade path, we ran a multi-hour Npcap/Wireshark capture.

The test EA calculated three indicators on every tick and made a trading decision. Latency was measured at the network interface from the incoming quote packet to the outgoing trade request:

```text
          t_in (Quote)                                  t_out (Trade)
               v                                              v
┌────────────┐   ┌─────────┐   ┌──────────────┐   ┌─────────┐   ┌────────────┐
│ MT4 Server │──>│ Backend │──>│ Runtime (EA) │──>│ Backend │──>│ MT4 Server │
└────────────┘   └─────────┘   └──────────────┘   └─────────┘   └────────────┘
               ^                                              ^
          sniffer tap                                    sniffer tap
          NIC / wire                                     NIC / wire
               └──────── INTEGRAL = t_out - t_in ─────────────┘
```

### Raw measured latency

| Runtime | Minimum | Median | Mean | p99 |
|---|---:|---:|---:|---:|
| **TFT** | 0.241 ms | **0.590 ms** | 0.600 ms | 1.176 ms |
| **MetaTrader 4** | 6.248 ms | **40.966 ms** | 56.863 ms | 181.899 ms |

| Metric | TFT | MetaTrader 4 | Measured difference |
|---|---:|---:|---:|
| Median latency | ~0.59 ms | ~41 ms | **~69× lower latency** |
| Mean latency | ~0.6 ms | ~57 ms | **~95× lower latency** |

**Test hardware:** Intel Core i7-6700HQ and 32 GB of RAM.

In this test, TFT was not only faster but substantially more consistent, while MetaTrader 4 showed much greater latency variation.

## Download

| Build | Download |
|---|---|
| **64-bit — recommended** | [TFT-Setup-x64.exe](https://github.com/TradingForge/TFT-releases/releases/latest/download/TFT-Setup-x64.exe) |
| **32-bit** | [TFT-Setup-x86.exe](https://github.com/TradingForge/TFT-releases/releases/latest/download/TFT-Setup-x86.exe) |

Installation is per-user and does not require administrator rights. Use the 64-bit build unless your Expert Advisor imports a 32-bit DLL; in that case, install the 32-bit build. Both versions can be installed side by side.

Setup installs the .NET 10 Desktop Runtime automatically if it is missing. TFT can check for new versions through **Help → Check for updates**.

The current installer is not yet code-signed, so Windows may display a blue **Windows protected your PC** warning. Select **More info → Run anyway** to continue. Code signing is planned.

## Setup guides

- [Add an MT4 account — method 1](MT4_SETUP_VIDEO_1_URL)
- [Add an MT4 account — method 2](MT4_SETUP_VIDEO_2_URL)
- [Connect a Binance account](BINANCE_SETUP_VIDEO_URL)

When creating exchange API credentials, grant only the permissions TFT needs for trading. Do not enable withdrawals.

## Roadmap

- Multiple accounts, each with its own Expert Advisors.
- Exchange-native stop-loss and take-profit on Binance.
- cTrader and Interactive Brokers backends.
- More brokers, exchanges, and trading APIs.
- Separate market-data feeds.
- Built-in charts and on-chart indicators.
- Linked accounts and copy trading.
- MQL5 Expert Advisors and indicators.
- Linux and macOS support.

## Current limitations

- **MQL4 source is required.** TFT loads `.mq4` files, not compiled `.ex4` binaries. It does not decompile protected or encrypted EAs.
- **One account at a time.** Multi-account execution is in development.
- **Windows only.** A 64-bit Windows 10 or 11 system is recommended. Linux and Mac support is on the roadmap.
- **MQL5 is not supported yet.** MQL5 support is on the roadmap.
- **Binance stop-loss and take-profit are currently monitored by TFT.** TFT must remain running and connected for terminal-side S/L and T/P handling. Exchange-native protective orders are planned.

## Privacy and security

TFT operates no server and sends us nothing: no telemetry, analytics, account registration, strategies, credentials, positions, or trade history.

Your Expert Advisors, indicators, and libraries remain under `Workdir\MQL4`. Updates and uninstalling TFT do not remove your strategies.

The Terminal connects to the network only for:

- your configured broker or exchange;
- update checks;
- notifications you configure yourself.

See [SECURITY.md](SECURITY.md) for the complete security model.

## Help and feedback

- Something is broken: [open an issue](https://github.com/TradingForge/TFT-releases/issues)
- Questions, feature requests, and platform requests: [start a discussion](https://github.com/TradingForge/TFT-releases/discussions)
- Release history: [CHANGELOG.md](CHANGELOG.md)
- Known limitations and development notes: [NOTES.md](NOTES.md)
- Contact: tradingforge.terminal@gmail.com

Feedback from MQL and algorithmic traders is especially welcome. Tell me which brokers, exchanges, data feeds, and MQL features matter most to your workflow.

## Support the project

If TFT saves you time, you can support development — thank you 🙏

Donate by card or PayPal:

[![Support on Ko-fi](https://img.shields.io/badge/Ko--fi-Support%20development-FF5E5B?logo=kofi&logoColor=white)](https://ko-fi.com/tradingforge)

Or with crypto:

| Network | Address |
|---|---|
| **Tron** (TRC-20) | `THnH7ihFYSJ2Z2sjCsAqB53RwieARDA7dn` |
| **Bitcoin** | `bc1qwrrzmx43ks3sgkp6qmgy6pcssvfr5jasxdekgk` |
| **Solana** | `9G2ezVrnsMzvbm1VLQgemusd24QAJpb77pJSvztQuU8b` |
| **Ethereum** (any Ethereum-based network, any token) | `0x545A8597f231221b620f9bD49152c5026c5ab5a9` |

## Legal

Copyright © TradingForge. All rights reserved. This software is proprietary and licensed for use, not for redistribution, resale, repackaging, or modification.

Trading involves substantial risk of loss and is not suitable for every investor. Automated trading can lose money faster than manual trading. You are responsible for the behavior and results of your Expert Advisors.
