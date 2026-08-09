# Orbitstrap-things

External asset repo for [Orbitstrap](https://github.com/orbitthegreatest/Orbitstrap). Holds
downloadable mod assets (emote wheels, skyboxes) that the app fetches on demand at runtime,
instead of bundling them into the .exe — keeps the installer small.

## How this is used

Each mod category has a `manifest.json` listing the available options and where to download
them from. The app downloads `manifest.json` first to populate a dropdown, then downloads only
the selected item's zip when the user picks it.

`manifest.json` format:
```json
[
  { "id": "some-id", "name": "Display Name", "url": "https://raw.githubusercontent.com/<owner>/Orbitstrap-things/main/<category>/<file>.zip" }
]
```

## Status

- `emote-wheels/manifest.json` — scaffolded with the wheels named in the Orbitstrap master plan
  (Task 2B). **The `url` fields are placeholders** — upload the matching zip for each entry to
  this repo, then update the URL to point at the real file.
- `skyboxes/manifest.json` — same idea, scaffolded with the skyboxes named for Task 2C.

Nothing here is consumed by the app yet — that's Task 3B (wire the app to actually fetch from
this repo), which comes after this repo exists for real on GitHub.

## Setup (for the repo owner)

1. Create an empty GitHub repo named `Orbitstrap-things` under your account.
2. Push the contents of this folder to it.
3. As you add real emote-wheel / skybox zip files, update the corresponding `url` field in that
   category's `manifest.json` to the real raw.githubusercontent.com link, then commit.
