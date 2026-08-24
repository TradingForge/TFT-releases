# Changelog

All notable changes to TradingForge Terminal, newest first.

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

