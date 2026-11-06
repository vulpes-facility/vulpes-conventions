# Servers without Kubernetes

Use this file for bare metal and for virtual machines.

1. Run each app as a container with Docker Compose, or as a systemd service.
2. Put a reverse proxy in front for TLS and routing (Caddy or nginx).\
   For rate limits, use nginx `limit_req`, or a Caddy build with a rate-limit module.
3. Deploy a container by an image tag that does not change.\
   Deploy a systemd service as a binary release with its version in the path.\
   Keep the last release, so you can go back.
4. Run the migrations as a one-shot step before the new version starts.
5. Back up the data stores ([data-stores.md](data-stores.md)).

- Open only the ports of the reverse proxy and SSH.\
  Use SSH keys, not passwords.
- Turn on automatic security updates of the operating system.
- Use a restart policy (`unless-stopped`, or `Restart=on-failure` in systemd).
- A restart policy starts a process again only after it stops.\
  An unhealthy container continues to run.\
  When the app cannot recover, make it stop.
- Write logs to stdout or journald.\
  Send them to the OpenTelemetry Collector ([observability.md](observability.md)).
