# Changelog

All notable changes to TradingForge Terminal, newest first.

## 1.0.16 - 2026-09-04

### What's new

- forum_words  added
- Polish TFT marketing site and release documentation
- docs(readme): name the test EA in the Performance caption (3 indicators + decision per tick)
- docs(readme): add Performance section — tick-to-trade latency vs MetaTrader 4
- perf: hand the argument array to reflection instead of copying it
- perf: compute a handler's parameter count once, not per invoke
- fix(logging): make the MT4LIB silencer the FIRST rule, so the guard works
- 1.0.15 => 1.0.16
- perf: stop allocating three delegates per tick
- docs(marketing): build the real static site from the landing design

## 1.0.15 - 2026-08-31

### What's new

- Account equity now includes credit, so your balance matches what your broker reports.
- Expert Advisors react faster to incoming ticks, cutting the delay before orders reach your broker.
- Product details and license now point to tradingforge-terminal.com.

## 1.0.14 - 2026-08-27

### What's new

- Maintenance and internal improvements.

## 1.0.13 - 2026-08-27

### What's new

- Security and stability fixes.
- Documentation adds new ways to support the project, including card, PayPal, and crypto donations.

## 1.0.12 - 2026-08-26

### What's new

- Expert Advisors and price history updates run more smoothly, with fixes for rare timing glitches that could cause erratic behavior.
- Your account limit now follows your license tier, which is shown in the About window and title bar; the Backends row is removed.
- The Single Account Mode dialog now makes clear that the one-account limit applies only to the Beta tier.
- The guide now explains the three ways Binance stop loss and take profit can be handled: internally, by the exchange, or manually.
- The guide now explains the Windows SmartScreen "Windows protected your PC" prompt, which appears only the first time you run a new release.

## 1.0.11 - 2026-08-24

### What's new

- Maintenance and internal improvements.

## 1.0.10 - 2026-08-23

### What's new

- Binance positions and closed trades now show the actual execution price of each order.

## 1.0.9 - 2026-08-22

### What's new

- Live orders on real accounts are now sized with live exchange limits, not demo limits.
- Live prices no longer freeze ΓÇö the mark price keeps updating.
- Take-profit and stop-loss orders placed from the exchange's web order form now appear in the terminal and no longer drop your account connection.
- Pending orders filled while the terminal was offline keep their ticket, magic number, and TP/SL after reconnecting.
- Connection status now tracks the market data feed accurately.
- Security and stability fixes.

## 1.0.8 - 2026-08-20

### What's new

- Triggered buy-stop and sell-stop orders now become open positions correctly on Binance.
- A take-profit order placed outside the terminal no longer corrupts your order list or drops the broker connection.
- Corrected the misspelled "Commission" column header in the Trade grid.
- Help > About and the README now show the current support contact address.
- Refreshed documentation with a clearer overview diagram and an up-to-date main-window screenshot.

## 1.0.7 - 2026-08-18

### What's new

- Indicator calls (iMA, iRSI, and other i* functions) on a different symbol or timeframe than the chart now return that symbol's and timeframe's values instead of the chart's own indicator.
- Double-click an order in the Trade grid to open a Modify Order ticket.
- The Modify Order button now becomes active as soon as you start typing a new value, instead of staying greyed out.
- Uninitialized string variables in Expert Advisors now start empty instead of containing a stray quote character.

## 1.0.5 - 2026-08-14

### What's new

- The New Order ticket no longer freezes when it's opened before your account has connected to the broker.

## 1.0.4 - 2026-08-14

### What's new

- Place market orders with the new New Order dialog.
- Double-click a symbol in the market watch to open an order ticket, with the familiar MT4 lot size list.
- Place manual orders even when Auto Trading is switched off.
- Binance orders now show their client order ID in the journal, so they are easier to match with your exchange history.
- Expert Advisors that use the DeMarker indicator now compile correctly on PCs set to comma decimal formatting.

## 1.0.3 - 2026-08-14

### What's new

- Expert Advisors that read text from byte arrays now get the full text instead of a blank string.
- Check for and install updates from inside the terminal.
- Updates no longer stall partway through.
- 32-bit and 64-bit versions can be installed side by side and run independently.
- Uninstalling keeps your Workdir MQL4 folder, Expert Advisors, and includes; everything else the terminal installed is removed.
- Security and stability fixes.

## 1.0.2 - 2026-08-13

### What's new

- Expert Advisors that read text from byte arrays now get the full text instead of a blank string.
- Check for and install updates from inside the terminal.
- Updates no longer stall partway through.
- 32-bit and 64-bit versions can be installed side by side and run independently.
- Uninstalling keeps your Workdir MQL4 folder, Expert Advisors, and includes; everything else the terminal installed is removed.
- Security and stability fixes.

