# Observability

1. Send traces, metrics, and logs with OpenTelemetry over OTLP.\
   Use only the signals that the SDK of the language supports as stable.
2. Send them to an OpenTelemetry Collector, not to a backend.\
   When the backend changes, change only the Collector.
3. Turn observability off unless its settings are there.\
   With no settings, load no SDK.
4. Write logs to stdout as JSON, in UTC, with the trace id.
5. Record the rate, the errors, and the duration of each endpoint and each consumer.

- Do not put request or response bodies, headers, cookies, query values, tokens, or personal data in telemetry.
- Keep the probes out of traces.
- Send errors to an error tracker (for example, Sentry) only when it is configured.\
  Do not report expected HTTP errors (4xx).
- Collect crashes from mobile apps (for example, Firebase Crashlytics or Sentry).
- Alert on what users see: the error rate and the latency of a service level objective.\
  Do not alert on each cause.
- Keep dashboards and alert rules as code in `infra/`.
- Self-hosted backend: Grafana with Loki, Tempo, and Mimir or Prometheus.\
  Cloud backend: see [cloud.md](cloud.md).
