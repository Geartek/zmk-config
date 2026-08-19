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

## Layout reference

**Bepo** (base)
```
╭──────┬─────┬─────┬─────┬─────┬─────╮   ╭─────┬─────┬─────┬─────┬─────┬─────╮
│  TAB │  B  │  É  │  P  │  O  │  È  │   │  ^  │  V  │  D  │  L  │  J  │  Z  │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ ESC  │  A  │  U  │  I  │  E  │  ,  │   │  C  │  T  │  S  │  R  │  N  │  M  │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ CTRL │  À  │  Y  │  X  │  .  │  K  │   │  '  │  Q  │  G  │  H  │  F  │  W  │
╰──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴─────╯
                   │  ⇧  │ SPC │ Sym │   │ ENT │BS/VM│AltGr│
                   ╰─────┴─────┴─────╯   ╰─────┴─────┴─────╯
```
ESC: tap = ESC, hold = LGUI. BS/VM: tap = Backspace, hold = VIM layer.

**Bepo_numsym** (Layer 1, hold Sym)
```
╭──────┬─────┬─────┬─────┬─────┬─────╮   ╭─────┬─────┬─────┬─────┬─────┬─────╮
│ $/#  │ "/1 │ «/2 │ »/3 │ (/4 │ )/5 │   │ @/6 │ +/7 │ -/8 │ //9 │ */0 │ =/° │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ SHFT │  [  │  ]  │  {  │  }  │ DEL │   │LEFT │DOWN │ UP  │ RGT │HOME │ END │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ CTRL │  <  │  >  │  _  │ PGUP│ PGDN│   │     │     │     │     │     │     │
╰──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴─────╯
                   │ GUI │     │ SPC │   │ ENT │SHFT │LALT │
                   ╰─────┴─────┴─────╯   ╰─────┴─────┴─────╯
```

**Bepo_func** (Layer 2, auto tri-layer: hold Sym + VM together)
```
╭──────┬─────┬─────┬─────┬─────┬─────╮   ╭─────┬─────┬─────┬─────┬─────┬─────╮
│  F1  │  F2 │  F3 │  F4 │ F5  │  F6 │   │  F7 │  F8 │  F9 │ F10 │ F11 │ F12 │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ SHFT │v up │prev │pause│next │ BKSP│   │ DEL │LEFT │DOWN │ UP  │ RGT │     │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ CTRL │v dn │mute │     │     │     │   │     │     │ PDN │ PUP │     │CALT │
╰──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴─────╯
                   │LGUI │     │ SPC │   │ ENT │     │ ALT │
                   ╰─────┴─────┴─────╯   ╰─────┴─────┴─────╯
```

**Vim** (Layer 3, hold BS/VM)
```
╭──────┬─────┬─────┬─────┬─────┬─────╮   ╭─────┬─────┬─────┬─────┬─────┬─────╮
│ trns │ BT1 │ BT2 │ BT3 │     │     │   │ HOME│ DOWN│  UP │ END │ PGUP│     │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ SHFT │     │     │     │     │     │   │ LEFT│ DOWN│  UP │ RGHT│ PGDN│     │
├──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼─────┤
│ CTRL │BTclr│     │     │     │     │   │  gg │  G  │  dd │  yy │  p  │     │
╰──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴─────╯
                   │ ALT │     │ SPC │   │ ESC │     │ trns│
                   ╰─────┴─────┴─────╯   ╰─────┴─────┴─────╯
```

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
