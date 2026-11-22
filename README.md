# gjallar-grafana

Dashboards and alert rules for [Gjallar](https://github.com/heimdallr-dev/gjallar).

| Path | What |
|---|---|
| `dashboards/gjallar.json` | Risk overview, pipeline health, lakehouse, and **metering**: usage per namespace, engine time and runs, API use per client (web, CLI, MCP), runtime observation |
| `alerts/gjallar-rules.yaml` | Prometheus rules: urgent and KEV findings, dropped jobs, stale vulnerability DB, engine errors |

Import the dashboard in Grafana (it asks for a Prometheus data source), or let
the Helm chart ship it as a ConfigMap for the Grafana sidecar
(`observability.grafanaDashboard: true`). The chart carries a copy; this repo
is the source.

Every metric comes from Gjallar's own `/metrics` endpoints; nothing is sent
anywhere. Any Prometheus-compatible store works (Prometheus, Mimir, Thanos,
VictoriaMetrics).

Apache-2.0.
