# meridian-media

Media hosting for [Meridian](https://github.com/veeresh-bikkaneti/Meridian)
(the free browser geography game). Served by GitHub Pages at
`https://veeresh-bikkaneti.github.io/meridian-media/`.

## Why a separate repo

106 journal movies × ~5.6 MB ≈ 600 MB. In the main repo that would
quadruple the git object store and push the Pages site toward the 1 GB
cap. Here the videos live apart and the app lazy-loads them by URL only
when a player opens that journal entry (`preload="none"`); nothing is
bundled. The manifest lives in the main repo at
`public/videos/journal-manifest.json` — moving hosts later is a manifest
change. See `docs/journal-movies.md` in the main repo for the plan and
the pilot recipe.

## Layout

- `journal/<entry-id>.mp4` — one 10 s movie per journal entry
  (1152×768, 24 fps, h264 + AAC, no on-screen text).
- `old-faithful.mp4` is the approved pilot (rebuilt beat, Magnus voice).

## Rules

- Never merge into the main repo from here; this repo holds media only.
- A clip lands here only after the coordinator's verification
  (ffprobe/decode/frames/audio/no-text). No ear-verification is claimed —
  the owner's listen is the final check.
