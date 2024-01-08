# UOIS SLO Monitoring

Upstream project is [hrbolek/_uois](https://github.com/hrbolek/_uois). SLO monitoring is based on [Prometheus](https://prometheus.io/), [Grafana](https://grafana.com/) and [seznam/slo-exporter](https://github.com/seznam/slo-exporter). The configuration here is based on the testing configuration from [this repo](https://gitlab.ics.muni.cz/Josef.Nemec/asq-measurement).

## Requirements

1. Custom [gql-ug image](https://github.com/Joseph-Beppe/gql_ug/tree/downstream):
```bash
docker build . -t gql_ug_slo:1.0
```

2. Custom [gql-forms image](https://github.com/Joseph-Beppe/gql_forms/tree/downstream):
```bash
docker build . -t gql_forms_slo:1.0
```

## Usage

```bash
docker-compose -f docker-compose.slo.yml up
```

- Prometheus is running at [localhost:9090](http://localhost:9090).
- Grafana is running at [localhost:8300](http://localhost:8300/dashboards). Default login `admin`:`admin`.

## Metrics

- gql_ug: `request_processing_seconds`, `request_latency_seconds`
- gql_forms: `request_latency_seconds`, `request_count_total`
- slo-exporter: `slo_events_total`, `slo_exporter_*`

## Changes

- [https://github.com/Joseph-Beppe/gql_ug/compare/latest...Joseph-Beppe:gql_ug:downstream](https://github.com/Joseph-Beppe/gql_ug/compare/latest...Joseph-Beppe:gql_ug:downstream)
- [https://github.com/Joseph-Beppe/gql_forms/compare/latest...Joseph-Beppe:gql_forms:downstream](https://github.com/Joseph-Beppe/gql_forms/compare/latest...Joseph-Beppe:gql_forms:downstream)
- [https://github.com/Joseph-Beppe/_uois/compare/latest...Joseph-Beppe:_uois:downstream](https://github.com/Joseph-Beppe/_uois/compare/latest...Joseph-Beppe:_uois:downstream)
