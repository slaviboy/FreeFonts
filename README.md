# FreeFonts

A pinned copy of free fonts from [Google Fonts](https://github.com/google/fonts), used by the OfficePro
Android app. The app downloads a font from here the first time the user picks it, so the fonts do
not have to ship inside the app and cannot disappear if Google changes its catalogue.

- `index.json` lists every font: family, category, licence and its files with size and SHA-256.
- `fonts/<family>/` holds the full `.ttf` files, the licence text and `METADATA.pb` from the
  upstream repository.
- `previews/<hash>.json` holds each family's name as a vector outline drawn in its own face.
  - The app's Font list draws these, so every font shows in its face before it is downloaded.
  - `index.json`'s top-level `previews` field names the current file, with its size and SHA-256.

Every font keeps its own licence (mostly the SIL Open Font License 1.1) and is credited to its
authors in its own folder. Source: https://github.com/google/fonts

## Mirrors

The same repository, byte for byte, is published in two places. The app tries GitHub first and
falls back to GitLab. Every file is checked against the SHA-256 in `index.json` whichever mirror
served it.

- https://github.com/slaviboy/FreeFonts (primary)
- https://gitlab.com/slaviboy/FreeFonts (backup)

## Contents

The 400 most popular families of Google Fonts (by Google's own popularity ranking) that have a
licence file and are not CJK-only, as full `.ttf` files (mostly variable fonts). Each has a name
preview.

## Maintaining

This repository is generated. Families are added in batches with the scripts in the maintainer's
local `FreeFonts-bulk` folder, whose `AI-GUIDE.md` is the step-by-step procedure. Installed copies
of the app depend on these rules:

- **Published files stay as they are.** Never change, rename or delete a font, licence or
  previews file. A new batch adds files and a new previews file.
- **Push order:** push the fonts, then the previews file, then `index.json` last.
- **Both mirrors:** every commit goes to both GitHub and GitLab.
- **Licences:** every family keeps its licence file.
