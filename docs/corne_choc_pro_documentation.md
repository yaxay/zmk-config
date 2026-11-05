# Corne Choc Pro BT - Keyboard Configuration

## Overview

| Property | Value |
|----------|-------|
| **Keyboard** | Corne Choc Pro BT (Keebart) |
| **Controller** | nRF52840 (Nice!Nano v2 class), UF2 bootloader |
| **Firmware** | ZMK `v0.3`, built by GitHub Actions |
| **Letters** | QWERTY as on the keycaps (US legends) |
| **Host layout** | German system layout `de` (`XKBLAYOUT=de`), no per-device override, no remapping tool |
| **Key codes** | German key codes `DE_*` from `config/keys_de.h` |
| **Window manager** | Hyprland (Omarchy 4.5.0) |
| **Displays** | 2x `nice_view` |
| **ZMK Studio** | left half (split central) only, unlock key on the ADJUST layer |

## Hardware Notes

- **42 physical keys** (3 x 12 + 6 thumb keys) in 46 matrix positions (4 unused `&none` positions in the inner columns); key positions in combos: left Space = 42, right Space = 43.
- **Split design:** wireless connection between the halves; the **left half is the central** (talks to the computer), the right half is the peripheral.
- **Thumb cluster:** 3 keys per side.
- **Bluetooth:** 5 profiles (ADJUST layer); also works over USB-C.

---

## Host layout and key codes

The computer uses its normal system layout `de`. In Omarchy it comes from `/etc/vconsole.conf` (`XKBLAYOUT=de`); Hyprland and the login screen read it, and there is no device rule for the Corne.

A ZMK key code has to be chosen for the layout of the host: `&kp DE_Z` sends the HID usage that the German layout reads as `z` (which is the usage of `y` on a US keyboard). The header `config/keys_de.h` (copy of the German header of [joelspadin/zmk-locales](https://github.com/joelspadin/zmk-locales), generated from Unicode CLDR data; commit, state and licenses in the file's first comments) provides these codes, including the modifiers some characters need (`DE_AT` = AltGr+Q, `DE_PIPE` = AltGr+`<`).

| Rule | Why |
|------|-----|
| Letters are QWERTY, `DE_Y` on the top row and `DE_Z` on the bottom row | the keycaps are US-QWERTY; the Z-X-C-V block stays together |
| `; :`, `, <`, `. >`, `/ ?` are mod-morphs (`semi_colon`, `comma_lt`, `dot_gt`, `slash_qmark`) | the legends are US; with the German layout the shifted character is another key code |
| `^`, `´`, `` ` `` are macros (`caret_sp`, `acute_sp`, `grave_sp`) that send the character and a Space | they are dead keys on the German layout |
| Capital umlauts: Shift on the umlaut key | `DE_A_UMLAUT` etc. are plain keys |

---

## Layer Structure

| Layer | Name | Activation |
|-------|------|------------|
| 0 | QWERTY | Default (Base Layer) |
| 1 | NUMBER | Hold: Lower (left middle thumb) |
| 2 | FNAV | Hold: Raise (right middle thumb) |
| 3 | TILING | Hold: Lower + Raise together |
| 4 | ADJUST | Combo: Left Space + Right Space together |
| 5 | SYMBOLS | Hold: right outer thumb |

The drawn layers are in the README (`keymap.svg`), the printable boxes in [`cheatsheet.md`](cheatsheet.md).

## Layer 0: QWERTY (Base Layer)

```
| Esc | Q | W | E | R | T |             | Y | U | I | O | P | ⌫ |
| Tab | A | S | D | F | G |             | H | J | K | L | ; :| ↵ |
|Strg | Z | X | C | V | B |             | N | M | , <| . >| / ?|Shift|
              [Super][Lower][Space]   [Space][Raise][Sym]
```

- `;` / `:`, `,` / `<`, `.` / `>` and `/` / `?` keep the US legends (mod-morphs).
- Backspace is above Enter on the right, Esc and Tab on the left.

## Layer 1: NUMBER (Lower)

```
|  ^ | 1 | 2 | 3 | 4 | 5 |             | 6 | 7 | 8 | 9 | 0 | _ |
|  ° | ! | " | § | $ | € |             | ( | ) | [ | ] | { | } |
|  + | * | ~ | # | = | @ |             | & | / | \ | % | ' | - |
```

`^` is typed with a Space after it (dead key). The symbols `¶ ¡ ¢ × ¿` do not exist on the German layout and are not on the keyboard any more.

## Layer 2: FNAV (Raise)

| Row | Left half | Right half |
|-----|-----------|------------|
| Top | `F1` … `F6` | `F7` … `F12` |
| Middle | `Strg`, `Alt`, `Shift`, `Caps` | `←` `↓` `↑` `→`, `Entf` |
| Bottom | | `Pos1`, `PgDn`, `PgUp`, `Ende` |

## Layer 3: TILING (Hyprland, Omarchy 4.5.0)

Omarchy 4.5.0 gives every monitor a block of ten workspaces (laptop 1–10, LG 11–20); `Super+1…0` acts on the block of the focused monitor. The layer sends whole key chords with one key.

| Keys | Chord | Omarchy action |
|------|-------|----------------|
| top row `Q … P` | `Super+1` … `Super+0` | workspace in the focused monitor's block |
| middle row `A … ;` | `Super+Shift+1` … `Super+Shift+0` | move the window to the workspace |
| bottom left `Z X C V` | `Super+←` `↓` `↑` `→` | focus the window in that direction |
| bottom left `B` | `Super+Tab` | next workspace |
| bottom right `N M , .` | `Super+Shift+←` `↓` `↑` `→` | swap the window in that direction |
| bottom right `/` | `Super+Shift+Tab` | previous workspace |
| left outer, top / middle (`Esc` / `Tab` position) | `Super+Ctrl+←` / `Super+Ctrl+→` | focus the monitor on the left / right (own bindings in `bindings.lua` of the computer) |
| right outer, top / middle (`Backspace` / `Enter` position) | `Super+Ctrl+Shift+←` / `Super+Ctrl+Shift+→` | move the window to the monitor on the left / right |

The other Omarchy keys are on the base layer with the left thumb (Super): `Super+Enter` terminal, `Super+Shift+Enter` browser, `Super+W` / `Super+Q` close, `Super+F` full screen, `Super+T` floating, `Super+Space` menu, `Super+K` list of key bindings.

## Layer 4: ADJUST (Media & System)

| Position | Key |
|----------|-----|
| top row `Q … T` | brightness −, brightness +, previous, play/pause, next |
| top row `Y U I` | volume −, volume +, mute |
| middle row `A … G` | Bluetooth profile 0 … 4 |
| bottom row `Z X C` | `BT CLR` (clear the bond of the active profile), `reset` (restart), `bootloader` |
| right half, bottom row, first key (`N` position) | `Studio` (ZMK Studio unlock) |

## Layer 5: SYMBOLS

```
|  ~ | @ | [ | ] | { | } |             | € | ü |   | ö | \| |   |
|    | ä | ß | ` | ´ |   |             | < | > | # |   | \ |   |
```

- Umlauts and `ß` sit on their letters (`A`, `U`, `O`, `S`); capitals with Shift.
- `` ` `` and `´` are dead keys on the German layout: the keys send the character and a Space.

## Thumb Key Layout

```
Left Hand:                              Right Hand:
┌─────┬─────┬─────┐                    ┌─────┬─────┬─────┐
│Super│Lower│Space│                    │Space│Raise│ Sym │
└─────┴─────┴─────┘                    └─────┴─────┴─────┘
```

| Position | Key | Function |
|----------|-----|----------|
| Left Outer | Super | Super key (Hyprland) |
| Left Middle | Lower | Layer 1 (NUMBER), with Raise layer 3 (TILING) |
| Left Inner | Space | Space |
| Right Inner | Space | Space (with the left Space: ADJUST) |
| Right Middle | Raise | Layer 2 (FNAV) |
| Right Outer | Symbols | Layer 5 (SYMBOLS); AltGr (`RALT`) on the other layers |

---

## ZMK Studio

- Built into the **left half only** (`studio-rpc-usb-uart` snippet and `CONFIG_ZMK_STUDIO=y` for `corne_choc_pro_left` in `build.yaml`).
- The unlock key `&studio_unlock` is on the ADJUST layer (right half, bottom row, first key).
- **The repository is the truth.** Studio is for trying things out. A keymap saved by Studio on the keyboard overrides the `.keymap` of the firmware until it is reset, so **before changing the `.keymap` use "Restore Stock Settings" in Studio** (or flash the `settings_reset` image on both halves). Studio cannot add layers; the six layers of the keymap are all it has.

---

## Repository

- **GitHub:** https://github.com/yaxay/zmk-config
- **Keymap file:** `config/corne_choc_pro.keymap`
- **Key codes:** `config/keys_de.h`

---

## Flashing Instructions

```bash
# 1. Download the firmware files from the GitHub Actions run (artifact of the "Build ZMK firmware" workflow)
# 2. Put the half into the bootloader: double-press the reset button (or the "bootloader" key on ADJUST)
# 3. Wait for the KEEBART (or NICENANO) drive to appear

# left half (central)
cp nice_view-corne_choc_pro_left-zmk.uf2 /run/media/$USER/KEEBART/

# right half (repeat step 2 for the right half)
cp nice_view-corne_choc_pro_right-zmk.uf2 /run/media/$USER/KEEBART/
```

**Resetting the pairing:** flash the `settings_reset-corne_choc_pro_left-zmk.uf2` and `settings_reset-corne_choc_pro_right-zmk.uf2` images first (they wipe the bonds, the split pairing and anything Studio saved), then the two `nice_view` images, left half first. Switch both halves on and pair profile 0 with the computer. Remove the old Corne entry on the computer before pairing again.

---

## Linux Configuration

The keyboard needs nothing on the computer: the system layout is `de`, and the firmware sends the matching key codes.

### Verify

```bash
# the Corne and the laptop keyboard show the same layout (de)
hyprctl devices -j | jq '.keyboards[] | {name, layout, variant}'
```

### Bindings used by the TILING layer

All chords are Omarchy 4.5.0 defaults, except `Super+Ctrl+←` and `Super+Ctrl+→` (focus the monitor on the left / right), which are set in `~/.config/hypr/bindings.lua` of the computer. List the current bindings with `omarchy menu keybindings --print` (`Super+K`).

---

*Last Updated: November 2026*
