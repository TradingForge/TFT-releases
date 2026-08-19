# Changelog

All notable changes to TradingForge Terminal, newest first.

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

