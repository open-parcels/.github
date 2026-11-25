<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/open-parcels/open-parcels/main/docs/branding/banner-on-dark.png">
    <img alt="Open Parcels" src="https://raw.githubusercontent.com/open-parcels/open-parcels/main/docs/branding/banner-on-light.png" width="640">
  </picture>
</p>
<p align="center">
  <a href="https://hub.docker.com/r/bluscream1/open-parcels"><img alt="Docker Hub pulls" src="https://img.shields.io/docker/pulls/bluscream1/open-parcels?logo=docker&label=pulls"></a>
  <a href="https://github.com/open-parcels/open-parcels"><img alt="Server stars" src="https://img.shields.io/github/stars/open-parcels/open-parcels?label=server%20stars&style=flat"></a>
  <a href="https://github.com/open-parcels/open-parcels-ha"><img alt="Integration stars" src="https://img.shields.io/github/stars/open-parcels/open-parcels-ha?label=HA%20integration%20stars&style=flat"></a>
</p>

# Open Parcels

**Self-hosted parcel and order tracking.** One service on your own hardware recognises the
tracking numbers of [about 95 carriers](https://open-parcels.github.io/#carriers), looks most of
them up live, signs in to carrier and shop accounts, reads shipping emails, shows the courier live on a
map and keeps a delivery calendar (also as an ICS feed). It runs on Docker, on Unraid and as a Home
Assistant app, and its Home Assistant integration gives every connection (carrier account, shop or inbox)
its own device. Order confirmation emails become orders; optional fallback services (a universal
lookup or 17TRACK) cover parcels no built-in carrier follows. The web UI is in English and German,
with a Status page and scheduled backups.

> **Status:** early development, `2.0.0-dev`. Expect breaking changes.

## Repositories

```
 open-parcels-rules ──(vendored package)─▶ open-parcels ──(REST + live events)──▶ open-parcels-ha
 tracking-number formats,               server + web UI,                       Home Assistant
 status tables, email rules             carrier providers, image               integration
                                              ▲      ▲
       open-parcels-ha-apps ──(runs it)───────┘      └──(sign-in capture)── open-parcels-extension
       Home Assistant app                                                   browser extension
```

| Repository | What it is |
|---|---|
| [open-parcels](https://github.com/open-parcels/open-parcels) | The server and web UI: carrier providers, email parsing, scheduler, live events, Docker image and Unraid template. |
| [open-parcels-rules](https://github.com/open-parcels/open-parcels-rules) | Shared knowledge: tracking-number formats, carrier status tables, expected-delivery phrases and shipping-email rules, with a TypeScript engine. |
| [open-parcels-ha](https://github.com/open-parcels/open-parcels-ha) | The Home Assistant integration (HACS custom repository): a device per connection, a tracker per open parcel. |
| [open-parcels-ha-apps](https://github.com/open-parcels/open-parcels-ha-apps) | The HA app (Home Assistant app, formerly an add-on): runs the server and web UI inside Home Assistant, opened from the sidebar. |
| [open-parcels-extension](https://github.com/open-parcels/open-parcels-extension) | Companion browser extension: one-click sign-in for carriers whose sign-in ends on a phone-app address (such as `dhllogin://`). Not in a browser store yet: install it from its [releases](https://github.com/open-parcels/open-parcels-extension/releases) or [load it unpacked](https://github.com/open-parcels/open-parcels-extension#load-unpacked). |

## Quick start

- **Website and install guides:** https://open-parcels.github.io
- **Docker Compose:** [docker-compose.yml](https://github.com/open-parcels/open-parcels/blob/main/docker-compose.yml). Version 2 is published as `bluscream1/open-parcels:dev` (amd64, arm64); `:latest` is still version 1 until 2.0.0.
- **Unraid:** [template](https://github.com/open-parcels/open-parcels/blob/main/unraid/open-parcels.xml)
- **Home Assistant app:** [add the HA app repository](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fopen-parcels%2Fopen-parcels-ha-apps), then install **Open Parcels**.
- **Home Assistant integration:** add `https://github.com/open-parcels/open-parcels-ha` to HACS as a custom integration repository.

Carrier interfaces are mostly unofficial and can break at any time. Open Parcels is not affiliated
with any carrier or shop.
