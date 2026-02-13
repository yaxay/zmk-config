# Corne Choc Pro BT - Keyboard Configuration

## Overview

| Property | Value |
|----------|-------|
| **Keyboard** | Corne Choc Pro BT |
| **Controller** | Nice!Nano v2 |
| **Firmware** | ZMK |
| **Layout** | US-QWERTY (optimized for programming) |
| **Linux Layout** | US AltGr-International (for Corne) / German (for laptop) |
| **Window Manager** | Hyprland (omarchy) |
| **Displays** | 2x OLED (Nice!View) |

## Hardware Notes

- **42 Matrix Positions:** 38 physical keys + 4 display positions (`&none`)
- **Split Design:** Wireless connection between halves
- **Thumb Cluster:** 3 keys per side

---

## Layer Structure

| Layer | Name | Activation |
|-------|------|------------|
| 0 | QWERTY | Default (Base Layer) |
| 1 | NUMBER | Hold: Lower (left middle thumb) |
| 2 | FNAV | Hold: Raise (right middle thumb) |
| 3 | TILING | Hold: Lower + Raise together |
| 4 | ADJUST | Combo: Left Space + Right Space together |

---

## Layer 0: QWERTY (Base Layer)

US-QWERTY layout matching physical keycaps.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐       ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ Esc │  Q  │  W  │  E  │  R  │  T  │       │  Y  │  U  │  I  │  O  │  P  │ ⌫   │
├─────┼─────┼─────┼─────┼─────┼─────┤ DISP  ├─────┼─────┼─────┼─────┼─────┼─────┤
│ Tab │  A  │  S  │  D  │  F  │  G  │       │  H  │  J  │  K  │  L  │ ; : │ ↵   │
├─────┼─────┼─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┼─────┼─────┤
│Shift│  Z  │  X  │  C  │  V  │  B  │       │  N  │  M  │ , < │ . > │ / ? │Shift│
└─────┴─────┴─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │Super│Lower│Space│       │Space│Raise│ Alt │
                  └─────┴─────┴─────┘       └─────┴─────┴─────┘
```

### Base Layer Features:
- **Escape:** Top left
- **Tab:** Second row left
- **Backspace (⌫):** Top right (above Enter)
- **Enter (↵):** Middle right
- **Space:** Both inner thumb keys (left and right)
- **Semicolon/Colon (;/:):** Right side, accessible on base layer
- **Slash/Question (/?):** Right side, accessible on base layer

### Accessing Umlauts (via Linux AltGr-International):
| Character | Key Combination |
|-----------|-----------------|
| ä | AltGr + Q |
| ö | AltGr + P |
| ü | AltGr + Y |
| Ä | AltGr + Shift + Q |
| Ö | AltGr + Shift + P |
| Ü | AltGr + Shift + Y |
| ß | AltGr + S |

---

## Layer 1: NUMBER (Lower Layer)

Activated by holding **Lower** (left middle thumb).

Numbers and special characters.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐       ┌─────┬─────┬─────┬─────┬─────┬─────┐
│  ^  │  1  │  2  │  3  │  4  │  5  │       │  6  │  7  │  8  │  9  │  0  │  ß  │
├─────┼─────┼─────┼─────┼─────┼─────┤ DISP  ├─────┼─────┼─────┼─────┼─────┼─────┤
│  °  │  !  │  "  │  §  │  $  │  €  │       │  (  │  )  │  [  │  ]  │  {  │  }  │
├─────┼─────┼─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ¶  │  ¡  │  "  │  ¢  │  =  │  ×  │       │  &  │  /  │  \  │  %  │  '  │  ¿  │
└─────┴─────┴─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │Super│ ▼▼▼ │Space│       │Space│     │ Alt │
                  └─────┴─────┴─────┘       └─────┴─────┴─────┘
```

### Lower Layer Keycodes (for US AltGr-International):

| Character | ZMK Keycode | Key Combination |
|-----------|-------------|-----------------|
| ^ | `LS(N6)` | Shift + 6 |
| ° | `RA(LS(SEMI))` | AltGr + Shift + ; |
| § | `RA(LS(S))` | AltGr + Shift + S |
| € | `RA(N5)` | AltGr + 5 |
| ¶ | `RA(SEMI)` | AltGr + ; |
| ¡ | `RA(LS(N1))` | AltGr + Shift + 1 |
| ¢ | `RA(LS(C))` | AltGr + Shift + C |
| × | `RA(EQUAL)` | AltGr + = |
| ß | `RA(S)` | AltGr + S |
| ¿ | `RA(FSLH)` | AltGr + / |

### Bracket Pairs (logically grouped):
| Pair | Keys | Position |
|------|------|----------|
| `( )` | Row 2, Right 1-2 | Parentheses |
| `[ ]` | Row 2, Right 3-4 | Square brackets |
| `{ }` | Row 2, Right 5-6 | Curly braces |

---

## Layer 2: FNAV (Raise Layer)

Activated by holding **Raise** (right middle thumb).

Function keys and navigation.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐       ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ F1  │ F2  │ F3  │ F4  │ F5  │ F6  │       │ F7  │ F8  │ F9  │ F10 │ F11 │ F12 │
├─────┼─────┼─────┼─────┼─────┼─────┤ DISP  ├─────┼─────┼─────┼─────┼─────┼─────┤
│Ctrl │ Alt │Shift│Caps │     │     │       │  ←  │  ↓  │  ↑  │  →  │     │ Del │
├─────┼─────┼─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │     │     │     │     │     │       │Home │PgDn │PgUp │ End │     │     │
└─────┴─────┴─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │Super│     │Space│       │Space│ ▼▼▼ │ Alt │
                  └─────┴─────┴─────┘       └─────┴─────┴─────┘
```

### Raise Layer Features:
- **F1-F12:** Full function key row
- **Arrow Keys:** Vim-style (H/J/K/L → ←/↓/↑/→)
- **Navigation:** Home, End, Page Up, Page Down
- **Modifiers:** Ctrl, Alt, Shift, Caps Lock (left side, easy combinations)
- **Delete:** Right side

---

## Layer 3: TILING (Hyprland Window Management)

Activated by holding **Lower + Raise** together.

All keys send **Hyper (Ctrl+Alt+Super+Shift)** + key, mapped to Hyprland actions in `~/.config/hypr/bindings.conf`.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐       ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ H+/ │ H+1 │ H+2 │ H+3 │ H+4 │ H+5 │       │ H+6 │ H+7 │ H+8 │ H+9 │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ DISP  ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │ H+A │ H+S │ H+D │ H+F │ H+G │       │ H+H │ H+J │ H+K │ H+L │H+Tab│     │
├─────┼─────┼─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │ H+Z │ H+X │ H+C │ H+V │ H+B │       │ H+N │ H+M │ H+, │ H+. │ H+P │     │
└─────┴─────┴─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │Super│ ▼▼▼ │Space│       │Space│ ▼▼▼ │ Alt │
                  └─────┴─────┴─────┘       └─────┴─────┴─────┘
```

### Hyprland Shortcuts (H = Hyper):

| Action | Keys |
|--------|------|
| Switch to Workspace 1-9 | H + 1-9 |
| Move Window to Workspace 1-9 | H + A/S/D/F/G/H/J/K/L |
| Focus Window (←/↓/↑/→) | H + N/M/,/. |
| Swap Windows (←/↓/↑/→) | H + Z/X/C/V |
| Next Workspace | H + Tab |
| Previous Workspace | H + P |
| Balance Sizes | H + B |
| Show Keybindings | H + / |

---

## Layer 4: ADJUST (Media & System)

Activated by pressing **Left Space + Right Space** together (combo).

```
┌─────┬─────┬─────┬─────┬─────┬─────┐       ┌─────┬─────┬─────┬─────┬─────┬─────┐
│     │ Bri-│ Bri+│ Prev│Play │ Next│       │ Vol-│ Vol+│ Mute│     │     │     │
├─────┼─────┼─────┼─────┼─────┼─────┤ DISP  ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │ BT1 │ BT2 │ BT3 │ BT4 │ BT5 │       │ H+W │ H+T │H+Ent│ H+R │ H+B │ H+= │
├─────┼─────┼─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┼─────┼─────┤
│     │BTClr│Reset│Boot │ H+O │ H+I │       │     │     │ H+- │     │     │     │
└─────┴─────┴─────┼─────┼─────┼─────┤       ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │Super│     │Space│       │Space│     │ Alt │
                  └─────┴─────┴─────┘       └─────┴─────┴─────┘
```

### Media Controls:
| Function | Key |
|----------|-----|
| Brightness Down | Bri- |
| Brightness Up | Bri+ |
| Previous Track | Prev |
| Play/Pause | Play |
| Next Track | Next |
| Volume Down | Vol- |
| Volume Up | Vol+ |
| Mute | Mute |

### Bluetooth:
| Function | Key |
|----------|-----|
| Profile 1-5 | BT1-BT5 |
| Clear All Profiles | BTClr |

### System:
| Function | Key |
|----------|-----|
| Reset | Reset (soft restart) |
| Bootloader | Boot (firmware flash mode) |

### Additional Hyprland (H = Hyper):
| Action | Key |
|--------|-----|
| Close Window | H + W |
| Toggle Float/Tile | H + T |
| Fullscreen | H + Enter |
| Toggle Split | H + R |
| Balance Sizes | H + B |
| Resize Width + | H + = |
| Resize Width - | H + - |
| Move to WS 9 | H + O |
| Move to WS 9 + Float | H + I |

---

## Thumb Key Layout

```
Left Hand:                              Right Hand:
┌─────┬─────┬─────┐                    ┌─────┬─────┬─────┐
│Super│Lower│Space│                    │Space│Raise│ Alt │
└─────┴─────┴─────┘                    └─────┴─────┴─────┘
```

| Position | Key | Function |
|----------|-----|----------|
| Left Outer | Super | Super/Windows key |
| Left Middle | Lower | Activate Layer 1 (Numbers) |
| Left Inner | Space | Space key |
| Right Inner | Space | Space key |
| Right Middle | Raise | Activate Layer 2 (F-keys/Nav) |
| Right Outer | Alt | AltGr (Right Alt) |

---

## Quick Reference

### Common Tasks:

| Task | Keys |
|------|------|
| Type numbers | Lower + top row |
| Type brackets | Lower + right middle row |
| F1-F12 | Raise + top row |
| Arrow keys | Raise + H/J/K/L |
| Page navigation | Raise + bottom right row |
| Umlauts (ä ö ü) | AltGr + Q/P/Y |
| Eszett (ß) | AltGr + S |
| Euro (€) | Lower + G |
| Degree (°) | Lower + Tab position |
| Section (§) | Lower + D |
| Volume control | Left Space + Right Space (hold), then Vol keys |
| Switch Workspace | Lower + Raise + Number |
| Move Window | Lower + Raise + Letter |

### Modifier Combinations (Raise Layer):
| Modifier | Position |
|----------|----------|
| Ctrl | Esc position |
| Alt | A position |
| Shift | S position |
| Caps Lock | D position |

---

## Repository

- **GitHub:** https://github.com/yaxay/ZMK-keyboard-config
- **Keymap File:** `config/corne_choc_pro.keymap`

---

## Flashing Instructions

```bash
# 1. Download firmware from GitHub Actions
# 2. Put keyboard half into bootloader mode (double-press reset button)
# 3. Wait for KEEBART drive to appear

# Flash left half
cp nice_view-corne_choc_pro_left-zmk.uf2 /run/media/$USER/KEEBART/

# Flash right half (repeat step 2 for right side)
cp nice_view-corne_choc_pro_right-zmk.uf2 /run/media/$USER/KEEBART/
```

---

## Linux Configuration

### Hyprland Per-Device Layout:

The Corne is configured with a per-device keyboard layout override in `~/.config/hypr/input.conf`:

```
# Global layout (laptop keyboard)
kb_layout = de

# Per-device override (Corne uses US AltGr-International)
device {
    name = zmk-project-corne-choc-pro-keyboard
    kb_layout = us
    kb_variant = altgr-intl
}
```

### Verify Device Layout:
```bash
# Check that the Corne shows US layout and laptop shows German
hyprctl devices -j | jq '.keyboards[] | {name, active_keymap}'
```

### Hyper Combo Bindings:

All tiling window management shortcuts are defined in `~/.config/hypr/bindings.conf` using the Hyper modifier (Ctrl+Alt+Super+Shift).

### Switching Between Keyboards:
- **Corne:** Automatically uses US AltGr-International layout
- **Laptop Built-in:** Automatically uses German layout
- **No manual switching needed** — Hyprland handles per-device layouts

---

*Last Updated: February 2026*
