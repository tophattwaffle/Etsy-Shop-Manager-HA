# AGENTS.md

Guidance for AI coding agents (Claude Code, Codex and others) working in this repository.

This is the Home Assistant integration (`etsy_shop_manager`, Python) for the self-hosted Etsy Shop Manager app. It
reads only the app's `/api/ha/v1` API on the LAN, never Etsy. The app, its design docs and the one to-do list for the
app, this integration and the dashboard card live in the app repository,
[etsy-shop-manager](https://github.com/TopHATTwaffle/etsy-shop-manager); the card is in
[Etsy-Shop-Manager-HA-Card](https://github.com/TopHATTwaffle/Etsy-Shop-Manager-HA-Card).

## Backlog and docs
- Open work for this integration is tracked in the app repository's `docs/BACKLOG.md`, not here. When you add, finish
  or drop work on this integration, update that file too (a PR in the app repository), as its `AGENTS.md` asks.
- Keep `README.md` true in the same PR as any change (attributes, events, actions, options, install steps).
- The sensor attributes must stay backward compatible with the card: add keys, never change or remove them. The app
  builds the payload (`HaPayloadBuilder`); a new attribute usually starts there.

## Releases
- Bump `version` in `custom_components/etsy_shop_manager/manifest.json` and tag the merge commit `vX.Y.Z`; HACS only
  offers an update for a new tag.

## Tests
`pip install pytest-homeassistant-custom-component`, then `pytest`. The tests run the integration in a real Home
Assistant against a mocked service. New behaviour gets a test; run the suite before saying a change is done.

## Public repository
This repository is mirrored publicly on GitHub: never write personal names or emails, private hostnames or LAN
addresses, API keys, or real order or customer data into code, tests, docs or commit messages.
