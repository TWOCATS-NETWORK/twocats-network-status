# Hedge Mappings

This document outlines how `sizing-output.schema.json` values are translated into Pulse tile data for Hedge lanes.

## Field Mapping

| sizing-output field | Pulse tile field |
| ------------------- | ---------------- |
| `risk_state` | `readiness` (lowercase) |
| `metrics.max_notional` | `metrics.max_notional` |
| `metrics.var_24h_bps` | `metrics.var_24h_bps` |
| `metrics.slippage_at_size_bps` | `metrics.slippage_at_size_bps` |
| `timestamp` | `last_updated` |
| `triggers` | `notes.triggers` |
| `actions` | `notes.actions` |

## Readiness Rules

`risk_state` from the sizing output is converted to lowercase and stored as the tile's `readiness`.

## Pages URLs

Published tiles are available on GitHub Pages:

- `pulse/data/hedge/laneA/latest.json`
- `pulse/data/hedge/laneB/latest.json`

Environment metadata files (`pages/pulse/<env>/latest.json`) include an `annotations.hedge` pointer to the latest lane files and an updated `last_updated` timestamp.
