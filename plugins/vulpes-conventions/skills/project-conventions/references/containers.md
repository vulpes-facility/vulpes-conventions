# Containers

1. Write one Dockerfile for each server and for each web app.\
   Use a build stage with the SDK and a small runtime stage.
2. Pin the base images by version.\
   Run the process as a user that is not root.
3. In `.dockerignore`, write the dependencies, the build output, `.env` files, `.git`, and the test results.
4. Give the image a `HEALTHCHECK` that calls the liveness endpoint only.

- A distroless image has no shell.\
  Give the app a health check command, for example `app healthcheck`.
- Go: when the build does not use cgo, set `CGO_ENABLED=0`.\
  Copy the binary to a distroless static image.
- Go: when the build uses cgo, use a runtime image that has the C libraries.
- Java or Kotlin: use the layered jar of Spring Boot, or `bootBuildImage`.\
  Run on a JRE image, not a JDK image.
- Node.js: start from the create-turbo `with-docker` example.\
  Run `turbo prune <app> --docker`.\
  Then run `pnpm install --frozen-lockfile`.
- A web app without server-side rendering (SSR) is static files.\
  Serve them from a web server, for example Caddy or nginx.
- A web app with SSR is a server.\
  Build it as a server image.
- A native mobile app does not go in a container ([mobile-release.md](mobile-release.md)).
- Cache fingerprinted assets for one year.\
  Send the HTML page with `no-cache`.
- When an asset is not there, send 404.\
  Do not send the app page.
- In a compose file, give each service a health check.\
  Use host ports that other projects do not use.
- Run migrations as a one-shot service that you can run again safely.\
  Run tests against a database that you make again for each run.
