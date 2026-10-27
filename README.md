# FreeFonts

A pinned copy of free fonts from [Google Fonts](https://github.com/google/fonts), used by the OfficePro
Android app. The app downloads a font from here the first time the user picks it, so the fonts do
not have to ship inside the app and cannot disappear if Google changes its catalogue.

- `index.json` lists every font: family, category, licence and its files with size and SHA-256.
- `fonts/<family>/` holds the full `.ttf` files, the licence text and `METADATA.pb` from the
  upstream repository.

Every font keeps its own licence (mostly the SIL Open Font License 1.1) and is credited to its
authors in its own folder. Source: https://github.com/google/fonts
