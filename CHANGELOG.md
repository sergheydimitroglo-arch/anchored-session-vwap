# Changelog

All notable changes to this project will be documented in this file.

## [1.0.0] — 2026-04-28

### Added

- Session-anchored VWAP with configurable session window and timezone
- 1, 2, 3 SD bands with independent toggle visibility
- Filled zones between adjacent bands
- Color-coded VWAP line based on price/volume state (bullish / bearish / neutral)
- Status dashboard with VWAP value, state, distance in SD units, volume regime, last signal age
- Volume confirmation filter (configurable lookback and multiplier)
- Dedup window to suppress repeat signals near a band
- First-bar-of-session signal guard
- Buy / Sell signal markers on band touches with volume + dedup confirmation
- Built-in alerts for signals and VWAP crosses
- Companion strategy file (`SessionVWAP_Strategy.pine`) with three exit modes (VWAP target / opposite band / fixed R:R)
- Session-end flat option in strategy
- Long-only / short-only / both direction filter in strategy

### Technical notes

- Built around TradingView's built-in `ta.vwap()` — math consistent with platform's standard VWAP
- Signals guarded by `barstate.isconfirmed` for non-repainting behavior
- Volume filter uses prior-bar SMA to avoid look-ahead bias
- VWAP cross alerts gated to fire once per bar at close

[1.0.0]: https://github.com/your-username/anchored-session-vwap/releases/tag/v1.0.0
