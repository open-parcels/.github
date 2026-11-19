<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/open-parcels/open-parcels/master/docs/branding/banner-on-dark.png">
    <img alt="Open Parcels" src="https://raw.githubusercontent.com/open-parcels/open-parcels/master/docs/branding/banner-on-light.png" width="640">
  </picture>
</p>
<p align="center">
  <a href="https://hub.docker.com/r/bluscream1/open-parcels"><img alt="Docker Hub pulls" src="https://img.shields.io/docker/pulls/bluscream1/open-parcels?logo=docker&label=pulls"></a>
  <a href="https://github.com/open-parcels/open-parcels"><img alt="Server stars" src="https://img.shields.io/github/stars/open-parcels/open-parcels?label=server%20stars&style=flat"></a>
  <a href="https://github.com/open-parcels/open-parcels-ha"><img alt="Integration stars" src="https://img.shields.io/github/stars/open-parcels/open-parcels-ha?label=HA%20integration%20stars&style=flat"></a>
  <a href="https://github.com/open-parcels/open-parcels-extension/releases"><img alt="Extension downloads" src="https://img.shields.io/github/downloads/open-parcels/open-parcels-extension/total?label=extension%20downloads"></a>
</p>

# Open Parcels

**Self-hosted parcel and order tracking.** One service on your own hardware follows about 90
carriers, signs in to carrier and shop accounts, reads shipping mails, shows the courier live on a
map and keeps a delivery calendar (also as an ICS feed). It runs on Docker, on Unraid and as a Home
Assistant app, and its Home Assistant integration gives every carrier account, shop and mailbox its
own device.

> **Status:** early development, `2.0.0-dev`. Expect breaking changes.

## Repositories

```
 open-parcels-rules ──(npm package)──▶ open-parcels ──(REST + event stream)──▶ open-parcels-ha
 tracking-number formats,              server + web UI,                        Home Assistant
 status tables, mail rules             carrier plug-ins, image                 integration
```

| Repository | What it is |
|---|---|
| [open-parcels](https://github.com/open-parcels/open-parcels) | The server and web UI: carrier plug-ins, mail parsing, scheduler, event stream, Docker image and Unraid template. |
| [open-parcels-rules](https://github.com/open-parcels/open-parcels-rules) | Shared knowledge: tracking-number formats, carrier status tables, delivery-date phrases and shipping-mail rules, with a TypeScript engine. |
| [open-parcels-ha](https://github.com/open-parcels/open-parcels-ha) | The Home Assistant integration (HACS custom repository): a device per source, a tracker per open parcel. |
| [open-parcels-extension](https://github.com/open-parcels/open-parcels-extension) | Companion browser extension: one-click sign-in for carriers whose login ends on an app address. |

## Quick start

- **Website and install guides:** https://open-parcels.github.io
- **Docker Compose:** [docker-compose.yml](https://github.com/open-parcels/open-parcels/blob/master/docker-compose.yml)
- **Unraid:** [template](https://github.com/open-parcels/open-parcels/blob/master/unraid/open-parcels.xml)
- **Home Assistant:** add `https://github.com/open-parcels/open-parcels-ha` to HACS as a custom integration repository.

Carrier interfaces are mostly unofficial and can break at any time. Open Parcels is not affiliated
with any carrier or shop.
