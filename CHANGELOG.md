# Changelog

All notable changes to ItemPass are documented in this file.

The format follows [Semantic Versioning](https://semver.org/).

---

## [1.1.3] – 2026-01-02

### Fixed
- Controller no longer participates in trade chains
- Eliminated `/giveme self` and NULL trade target failures
- Controller now clicks items locally **after** the trade chain completes
- Chain execution is fully deterministic regardless of controller state

### Changed
- Controller checkbox now controls **end-of-chain local usage**
- Trade logic and controller logic are explicitly separated

### Internal
- Added durable FSM phase for controller-only actions
- Enforced controller exclusion from trade-based FSM states
- Improved chain-order correctness when `(Start)` is used

---

## [1.1.2]

### Fixed
- Controller checkbox not triggering local item usage
- Missing FSM state causing controller `/useitem` to be skipped

> Superseded by v1.1.3 due to remaining self-trade edge cases.

---

## [1.1.1]

### Fixed
- `(Start)` marker not consistently honored
- Chain ordering inconsistencies

---

## [1.1.0]

### Initial Public Release
- Deterministic item pass chain
- Profile support
- ImGui UI
- EMU-safe inventory handling
