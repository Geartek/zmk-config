# Bépo Corne Choc layout — EN/FR + C + Vim

## Design decisions
- **Base layer = untouched standard BÉPO 1.1 (NF Z71-300).** Your letter
  muscle memory doesn't move at all — this is the whole point.
- **Bepo_numsym (Layer 1, left thumb):** merged numbers + symbols + nav.
  Reproduces real BÉPO number-row behaviour (bare key = symbol, +Shift =
  digit). `{ } < >` are bare (not behind AltGr) since they're used
  constantly in C. Arrows land on the same physical columns QWERTY's
  H J K L occupy, so they double as everyday (non-Vim) mouse-free nav.
- **Bepo_func (Layer 2, auto tri-layer 1+3):** F-keys, media.
- **Vim (Layer 3, right thumb, outer key):** right hand becomes
  arrows/Home/End/PgUp/PgDn/gg/G/dd/yy/p for mouse-free navigation in
  *any* app (browser, terminal, non-vim editors), left hand keeps
  Ctrl/Shift/Alt so Ctrl+arrow / Shift+arrow combos still work.

## Why there's no vimrc/hjkl remap
Real Vim normal-mode motions (`hjkl`, `w`/`b`, `g`-prefixed commands) stay
untouched here on purpose — typed via their real BÉPO physical position,
whatever that is. One mental model: the character you type is the Vim
command, no relabeling layer in between. The Vim layer above only sends
plain literal keystrokes (universal arrows, or a real Vim command
autotyped twice by a macro), so it never fights the muscle memory you're
building for actual Vim motions. Yes, this means real `hjkl` are scattered
across the board instead of clustered like on QWERTY — accepted tradeoff
for not maintaining a second remap to keep in your head.

## Symbol/char reference
`config/keys_fr_bepo.h` is the ZMK community BÉPO 1.1 header — every
accented/symbol character sent by this keymap is verified against it,
not hand-guessed.

## Build
Builds via GitHub Actions on push (see `.github/workflows/build.yml` /
`build.yaml`). To build locally instead:
```console
west build -p -d build/left -b nice_nano_v2 -- \
  -DSHIELD=corne_left -DZMK_CONFIG="$(pwd)/config"
west build -p -d build/right -b nice_nano_v2 -- \
  -DSHIELD=corne_right -DZMK_CONFIG="$(pwd)/config"
```

Reference base: github.com/goof03/zmk-config (Bépo Corne choc ZMK config),
adjusted for C punctuation + an added Vim navigation layer.
