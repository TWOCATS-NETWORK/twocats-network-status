# Pulse Tiles

The Pulse repository publishes machine-readable tile specifications for dashboards and agents.

## Available tiles

- **Feed Heartbeat**  
  Source: `pulse/staging/latest.json` (defaults to `env_default` unless overridden)  
  Fields: `last_updated`, `last_event.component`, `last_event.task`, `last_event.status`
- **Hedge — Lane A**  
  Source: `pulse/data/hedge/laneA/latest.json`  
  Fields: `readiness`, `metrics.max_notional`, `metrics.var_24h_bps`, `metrics.slippage_at_size_bps`, `timestamp`
- **Hedge — Lane B**  
  Source: `pulse/data/hedge/laneB/latest.json`  
  Fields: `readiness`, `metrics.max_notional`, `metrics.var_24h_bps`, `metrics.slippage_at_size_bps`, `timestamp`
- **PR Activity (last 10)**  
  Source: `pulse/api/events/latest.json`  
  Filter: `component=PR`, limit 10  
  Fields: `timestamp`, `owner`, `status`, `summary`, `pr_number`, `pr_url`

## Tile index

Fetch the index to discover all tiles:

```
GET https://twocats-network.github.io/twocats-network-status/pulse/tiles/index.json
```

Heartbeat tiles use `env_default=staging` unless explicitly overridden.
