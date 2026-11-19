# Contributing

Thanks for helping. A few rules apply to every Open Parcels repository:

- **Open an issue first** for anything larger than a small fix, so the approach can be agreed.
- **Run the repository's gate** before you open a pull request (see its README, e.g.
  `npm run gate`, or ruff, mypy and pytest for the Home Assistant integration). Do not disable
  checks or skip hooks.
- **Add a test** for every fix and feature.
- **Conventional commits** (`fix(dhl): …`, `feat: …`, `docs: …`).
- **No personal data.** Fixtures and examples use made-up tracking numbers, names, addresses and
  mails. Redact anything real before you paste logs or diagnostics.
- New carriers' tracking-number formats, status tables and mail rules belong in
  [open-parcels-rules](https://github.com/open-parcels/open-parcels-rules); live lookups and
  sign-ins belong in the server's plug-ins.

Security problems: see [SECURITY.md](SECURITY.md).
