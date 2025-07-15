# An observability ("o11y") stack in Docker Compose

## Services

| Service  | URL                                                                         | What it's for                          | Status                                             |
|----------|-----------------------------------------------------------------------------|----------------------------------------|----------------------------------------------------|
| Alloy    | 🟢 http://0.0.0.0:12345                                                     | Aggregate and relay observability data | 🟢                                                 |
| Grafana  | 🟢 http://0.0.0.0:3000                                                      | Visualize data                         | 🟢 [Dashboards OK](http://0.0.0.0:3000/dashboards) |
| Graphite | 🟢 http://0.0.0.0:8080                                                      | Browsing metrics and data from StatsD  | 🟢                                                 |
| Loki     | 🟢 [Grafana source](http://0.0.0.0:3000/connections/datasources/edit/loki)  | Log aggregation and querying           | 🟢                                                 |
| Mimir    | 🟠 [Grafana source](http://0.0.0.0:3000/connections/datasources/edit/mimir) | Time-series database                   | Grafana source not connected                       |
| Tempo    | 🟠 [Grafana source](http://0.0.0.0:3000/connections/datasources/edit/tempo) | Distributed tracing data collection    | Grafana source not connected                       |
| CLI      |                                                                             | Container to shell into for tools      | 🟢                                                 |

## Usage & notes

### Graphite

- Host data is stored in Whisper layout at `/opt/graphite/storage/whisper/collectd/`
- Can be a mounted disk

### Grafana

- Data sources and dashboards are provisioned from `config/grafana` in this project.