# Kubernetes

1. Make one Deployment and one Service for each server and for each web image.\
   Set resource requests and limits.
2. Run the migrations as a Job before the new Deployment rolls out.\
   Run scheduled work as a CronJob with `concurrencyPolicy: Forbid`.
3. Set a liveness probe, a readiness probe, and a startup probe.\
   For a gRPC server, add the gRPC health service and use `grpc` probes.
4. Give the configuration as environment variables from a ConfigMap.\
   Give the secrets from a Secret.
5. At the Ingress or Gateway, send the API path to the API Service.\
   Send all other paths to the web Service.
6. Run a data store or a broker as a managed service ([cloud.md](cloud.md)), or with its operator.\
   Do not run it as a Deployment.

- The liveness probe calls nothing outside the process.
- The readiness probe of a server calls only the main database, with a short timeout.\
  It does not call the cache, the broker, or other services.
- The readiness probe of a web server gets only its own page.
- A server MUST be stateless.\
  Run at least 2 replicas.
- On `SIGTERM`, make readiness send 503 for a short delay, but continue to serve.\
  Then stop.
- Set `terminationGracePeriodSeconds` longer than that delay plus the longest request.
- When many replicas do background work, give each row a lease: a claim token and an expiry time.\
  In PostgreSQL, lock the rows with `FOR UPDATE SKIP LOCKED` while you write the lease.\
  In MongoDB, get the lease with one `findOneAndUpdate`.\
  Make the work idempotent, because a lease can end before the work stops.
- Do TLS termination and rate limits at the Ingress or Gateway.\
  Deploy images by a tag that does not change, or by digest.
