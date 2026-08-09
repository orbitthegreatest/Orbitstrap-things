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

- `emote-wheels/manifest.json` — **10 real emote wheel zips included**, sourced from the
  `Roblox-emote-weels` repo: Cute Bears, Deathnote, Emo2, Itachi, Killua, Miguel, Pink Anime
  Girl, Pink Theme, Purple, Rick and Morty.
- `skyboxes/manifest.json` — **24 real skybox zips included**:
  - 4 "new" skyboxes from the `nice-skyboxes-roblox` repo: Northern Lights, Sky Nibiru Bl,
    Troll Face, XenSkybox.
  - 20 "old" skyboxes pulled from what's already bundled inside the Orbitstrap app itself
    (`Orbitstrap/Resources/Skyboxes/`), re-zipped here so they're available through the same
    on-demand download path: Beautiful, Blue, Chill Gray, ChromaKey, Default, Grimnight, Homer
    Uchiha, Jungle CSGO, Light Blue, Light Pink, Minesky, Neon Sky, Neon Sky 2, Pandora, Planet
    Cyan, Purple Void, RemRam, Sky Purple, Sky2006, Yumeko.

**The `url` fields in both manifests are still placeholders** pointing at
`raw.githubusercontent.com/orbitthegreatest/Orbitstrap-things/main/...` — they'll resolve for
real once this folder is pushed to that repo (see Setup below). The zip files themselves are
real and already sitting next to each manifest in this delivery.

Nothing here is consumed by the app yet — that's Task 3B (wire the app to actually fetch from
this repo), which comes after this repo exists for real on GitHub.

## Setup (for the repo owner)

1. Create an empty GitHub repo named `Orbitstrap-things` under your account.
2. Push the contents of this folder to it (including the 34 zip files — `emote-wheels/*.zip` and
   `skyboxes/*.zip` — not just the manifests).
3. If your GitHub username/repo name differs from `orbitthegreatest/Orbitstrap-things`, update
   the `url` field in both `manifest.json` files to match your actual repo path.
