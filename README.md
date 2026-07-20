# camofox-image

Docker image for [Camofox](https://github.com/jo-inc/camofox-browser) — a self-hosted browser server wrapping [Camoufox](https://github.com/daijro/camoufox) (Firefox fork with C++ fingerprint spoofing).

Used by Hermes Agent for anti-detection browser automation. When `CAMOFOX_URL` is set, Hermes routes all browser tool calls through this server instead of cloud providers.

## Usage

```bash
docker run -d --name camofox \
  --restart unless-stopped \
  -p 9377:9377 \
  ghcr.io/bot-ted/camofox-image:latest
```

The server exposes a REST API on port 9377. Health check at `GET /health`.

## Image

Public image at `ghcr.io/bot-ted/camofox-image:latest`. No pull secret required.

Rebuilt nightly from upstream [camofox-browser](https://github.com/jo-inc/camofox-browser) to track Camoufox updates.
