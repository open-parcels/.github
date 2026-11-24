# Contributing

Thanks for helping. A few rules apply to every Open Parcels repository:

- **Open an issue first** for anything larger than a small fix, so the approach can be agreed.
- **Run the repository's checks** before you open a pull request. Do not disable checks or skip
  hooks.

  | Repository | Command |
  |---|---|
  | open-parcels, open-parcels-rules | `npm run gate` |
  | open-parcels-ha | ruff, mypy and pytest (see its README) |
  | open-parcels-extension | `npm run check` |
  | open-parcels-ha-apps, open-parcels.github.io | none: keep the change small and describe in the pull request how you tested it |

- **Add a test** for every fix and feature in the repositories that have tests.
- **Conventional commits** (`fix(dhl): …`, `feat: …`, `docs: …`).
- **No personal data.** Fixtures and examples use made-up tracking numbers, names, addresses and
  emails. Redact anything real before you paste logs or diagnostics.
- New carriers' tracking-number formats, status tables and email rules belong in
  [open-parcels-rules](https://github.com/open-parcels/open-parcels-rules); live lookups and
  sign-ins belong in the server's providers.

Security problems: see [SECURITY.md](SECURITY.md).
