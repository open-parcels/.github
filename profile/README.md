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
| [open-parcels-ha](https://github.com/open-parcels/open-parcels-ha) | The Home Assistant integration (HACS custom repository): a device per source, an entity per parcel. |

## Quick start

- **Website and install guides:** https://open-parcels.github.io
- **Docker Compose:** [docker-compose.yml](https://github.com/open-parcels/open-parcels/blob/master/docker-compose.yml)
- **Unraid:** [template](https://github.com/open-parcels/open-parcels/blob/master/unraid/open-parcels.xml)
- **Home Assistant:** add `https://github.com/open-parcels/open-parcels-ha` to HACS as a custom integration repository.

Carrier interfaces are mostly unofficial and can break at any time. Open Parcels is not affiliated
with any carrier or shop.
