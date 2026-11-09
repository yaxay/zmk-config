# Corne Choc Pro — Cheatsheet

Der Rechner nutzt das Systemlayout `de`; die Tastatur sendet deutsche Tastencodes, es kommt an, was auf der Taste steht.
Die Kappen sind US-QWERTY, Y und Z liegen wie auf den Kappen (die Firmware tauscht sie für das deutsche Layout).

## Ebene 0: QWERTY (Basis)

```
┌───────┬───────┬───────┬───────┬───────┬───────┐    ┌───────┬───────┬───────┬───────┬───────┬───────┐
│  Esc  │   Q   │   W   │   E   │   R   │   T   │    │   Y   │   U   │   I   │   O   │   P   │   ⌫   │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│  Tab  │   A   │   S   │   D   │   F   │   G   │    │   H   │   J   │   K   │   L   │  ; :  │   ↵   │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│  Strg │   Z   │   X   │   C   │   V   │   B   │    │   N   │   M   │  , <  │  . >  │  / ?  │ Shift │
└───────┴───────┴───────┴───────┴───────┴───────┘    └───────┴───────┴───────┴───────┴───────┴───────┘

                    [ Super ]  [ Lower ]  [ Space ]      [ Space ]  [ Raise ]  [  Sym  ]
```

`; :`, `, <`, `. >` und `/ ?` sind Mod-Morphs: mit Shift kommt das zweite Zeichen der US-Beschriftung.

Home-Row-Mods: halten (zusammen mit einer Taste der anderen Hand) ergibt `S`/`L` = Alt, `D`/`K` = Strg, `F`/`J` = Shift; antippen schreibt den Buchstaben. Strg+C: `K` halten, `C` tippen. Alt+Tab: `L` halten, `Tab` tippen. Das echte Strg bleibt links unten.

## Ebene 1: NUMBER – linken mittleren Daumen halten (Lower)

```
┌───────┬───────┬───────┬───────┬───────┬───────┐    ┌───────┬───────┬───────┬───────┬───────┬───────┐
│   ^   │   1   │   2   │   3   │   4   │   5   │    │   6   │   7   │   8   │   9   │   0   │   _   │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│   °   │   !   │   "   │   §   │   $   │   €   │    │   (   │   )   │   [   │   ]   │   {   │   }   │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│   ¶   │   ¡   │   ~   │   ¢   │   =   │   ×   │    │   &   │   /   │   \   │   %   │   '   │   -   │
└───────┴───────┴───────┴───────┴───────┴───────┘    └───────┴───────┴───────┴───────┴───────┴───────┘

                    [       ]  [       ]  [ Space ]      [ Space ]  [       ]  [  Sym  ]
```

`^` ist beim deutschen Layout eine tote Taste; die Taste sendet `^` und ein Space, damit das Zeichen sofort erscheint.

`¶ ¡ ¢ ×` hat das deutsche Layout nicht; jede Taste drückt Compose (Umschalt+Caps) und die Folge `p !`, `! !`, `c /` bzw. `x x`. `+ * # @` liegen auf SYMBOLS.

Die linke äußere Daumentaste (sonst Super) sendet auf dieser Ebene nichts: mit gedrücktem Super würde aus `AltGr+8` ein `Super+8` (Workspace-Wechsel) statt `[`. Nur die Taste dieser Ebene halten; liegt Super schon, erst loslassen.

## Ebene 2: FNAV – rechten mittleren Daumen halten (Raise)

```
┌───────┬───────┬───────┬───────┬───────┬───────┐    ┌───────┬───────┬───────┬───────┬───────┬───────┐
│   F1  │   F2  │   F3  │   F4  │   F5  │   F6  │    │   F7  │   F8  │   F9  │  F10  │  F11  │  F12  │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│ Druck │ Rollen│ Pause │ Ende  │ Einfg │  Entf │    │   ←   │   ↓   │   ↑   │   →   │  PgDn │  PgUp │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│  Strg │  Alt  │ Shift │       │  Caps │  Pos1 │    │  Menü │       │       │ Shift │ AltGr │  Strg │
└───────┴───────┴───────┴───────┴───────┴───────┘    └───────┴───────┴───────┴───────┴───────┴───────┘

                    [ Super ]  [       ]  [ Space ]      [ Space ]  [       ]  [       ]
```

Leere Tasten senden nichts. Entf, Strg und Alt liegen zusammen links: `Strg+Alt+Entf` schließt in Omarchy alle Fenster, also nur mit Absicht. Ganz rechts unten ist hier Strg (auf der Basisebene Shift).

## Ebene 3: TILING (Hyprland) – Lower und Raise zusammen halten

```
┌───────┬───────┬───────┬───────┬───────┬───────┐    ┌───────┬───────┬───────┬───────┬───────┬───────┐
│ ◀ mon │  WS 1 │  WS 2 │  WS 3 │  WS 4 │  WS 5 │    │  WS 6 │  WS 7 │  WS 8 │  WS 9 │ WS 10 │ win→◀ │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│ mon ▶ │ →WS 1 │ →WS 2 │ →WS 3 │ →WS 4 │ →WS 5 │    │ →WS 6 │ →WS 7 │ →WS 8 │ →WS 9 │ →WS 10│ win→▶ │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │◀ focus│▼ focus│▲ focus│▶ focus│next WS│    │ ◀ swap│ ▼ swap│ ▲ swap│ ▶ swap│prev WS│       │
└───────┴───────┴───────┴───────┴───────┴───────┘    └───────┴───────┴───────┴───────┴───────┴───────┘

                    [ Super ]  [       ]  [ Space ]      [ Space ]  [       ]  [       ]
```

`WS n` = `Super+n`, `→WS n` = `Super+Shift+n` (Fenster in den Workspace); `focus` = `Super+Pfeil`, `swap` = `Super+Shift+Pfeil`; `mon` = `Super+Strg+Pfeil` (Monitor-Fokus), `win→` = `Super+Strg+Shift+Pfeil` (Fenster auf den Monitor). `Super+1…0` wirkt im Block des fokussierten Monitors (Laptop 1–10, LG 11–20).

## Ebene 4: ADJUST – linkes und rechtes Space gleichzeitig

```
┌───────┬───────┬───────┬───────┬───────┬───────┐    ┌───────┬───────┬───────┬───────┬───────┬───────┐
│       │ Hell −│ Hell +│ Zurück│  Play │ Weiter│    │ Vol − │ Vol + │ Stumm │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │  BT 0 │  BT 1 │  BT 2 │  BT 3 │  BT 4 │    │       │       │       │       │       │       │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │ BT CLR│ reset │  boot │       │       │    │ Studio│       │       │       │       │       │
└───────┴───────┴───────┴───────┴───────┴───────┘    └───────┴───────┴───────┴───────┴───────┴───────┘

                    [ Super ]  [       ]  [ Space ]      [ Space ]  [       ]  [       ]
```

Zeile 1: Helligkeit −/+, Zurück, Play/Pause, Weiter | Lautstärke −/+, Stumm. Zeile 2: Bluetooth-Profil 0–4. Zeile 3: BT CLR (aktives Profil löschen), reset (Neustart), boot (Bootloader); `Studio` entsperrt ZMK Studio.

## Ebene 5: SYMBOLS – rechten äußeren Daumen halten

```
┌───────┬───────┬───────┬───────┬───────┬───────┐    ┌───────┬───────┬───────┬───────┬───────┬───────┐
│   ~   │   @   │   [   │   ]   │   {   │   }   │    │   €   │   ü   │       │   ö   │   |   │       │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │   ä   │   ß   │   `   │   ´   │       │    │   <   │   >   │   #   │       │   \   │       │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │   +   │   *   │       │       │       │    │       │       │       │       │       │ Shift │
└───────┴───────┴───────┴───────┴───────┴───────┘    └───────┴───────┴───────┴───────┴───────┴───────┘

                    [       ]  [       ]  [ Space ]      [ Space ]  [       ]  [  Sym  ]
```

`` ` `` und `´` sind tote Tasten; sie senden das Zeichen und ein Space. Große Umlaute: Shift halten.

## Ebene 6: WORK – Lower und Symbols zusammen halten

```
┌───────┬───────┬───────┬───────┬───────┬───────┐    ┌───────┬───────┬───────┬───────┬───────┬───────┐
│ close │ tab 1 │ tab 2 │ tab 3 │ tab 4 │ tab 5 │    │ tab 6 │ tab 7 │ tab 8 │ tab 9 │       │  menu │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│prefix │split ▼│split ▶│       │       │       │    │ ◀ pane│ ▼ pane│ ▲ pane│ pane ▶│       │  keys │
├───────┼───────┼───────┼───────┼───────┼───────┤    ├───────┼───────┼───────┼───────┼───────┼───────┤
│       │ ◀ tab │ hWS ▼ │ hWS ▲ │ tab ▶ │       │    │ ◀ size│ ▼ size│ ▲ size│ size ▶│       │       │
└───────┴───────┴───────┴───────┴───────┴───────┘    └───────┴───────┴───────┴───────┴───────┴───────┘

                    [       ]  [       ]  [ Space ]      [ Space ]  [       ]  [  Sym  ]
```

Einzeltasten für herdr: `tab n` = `Alt+n`, `close` = `Alt+Esc` (schließt die Pane ohne Rückfrage), `prefix` = `Strg+Leertaste`, `split ▼ / ▶` = `Alt+Enter` / `Alt+Umschalt+Enter`, `◀ / tab ▶` = `Alt+←/→` (Tab zurück/weiter), `hWS` = `Alt+↓/↑` (herdr-Workspace), `pane` = `Strg+Alt+Pfeil` (Fokus), `size` = `Strg+Alt+Umschalt+Pfeil`. Omarchy: `menu` = `Super+Leertaste`, `keys` = `Super+K`. Nicht belegte Tasten senden nichts.

## Häufige Zeichen

| Zeichen | Tasten |
|---------|--------|
| ä ö ü ß | SYMBOLS + A / O / U / S (Shift halten für Ä Ö Ü) |
| € | SYMBOLS + Y-Position oder Lower + G-Position |
| @ | SYMBOLS + Q-Position |
| + * | SYMBOLS + Z / X |
| ¶ ¡ ¢ × | Lower + unterste Reihe links (Compose-Makros) |
| \| | SYMBOLS + P-Position |
| \\ | SYMBOLS + `;`-Position |
| # | SYMBOLS + K-Position |
| < > | SYMBOLS + H / J, oder Shift + `,` / `.` |
| ~ | SYMBOLS + Esc-Position |
| [ ] { } | SYMBOLS + W E R T, oder Lower + K L `;` Enter |
| ( ) | Lower + H / J |
| ^ ´ ` | tote Tasten mit Space: ^ auf Lower (oben links außen), ` und ´ auf SYMBOLS (D / F) |

## Tiling (Hyprland, Omarchy 4.5.0)

| Aufgabe | Taste |
|---------|-------|
| Workspace im Block des fokussierten Monitors | TILING + oberste Reihe (1–5 links, 6–0 rechts) |
| Fenster in den Workspace | TILING + mittlere Reihe |
| Fenster-Fokus | TILING + untere Reihe links (Pfeile) |
| Fenster tauschen | TILING + untere Reihe rechts (Pfeile) |
| nächster / vorheriger Workspace | TILING + B / `/` |
| Monitor-Fokus links / rechts | TILING + Esc- / Tab-Position |
| Fenster auf den Monitor links / rechts | TILING + Backspace- / Enter-Position |

Alles andere von Omarchy (Terminal `Super+Enter`, Schließen `Super+W`, Vollbild `Super+F`, Floating `Super+T`, Menü `Super+Leertaste`)
liegt auf der Basisebene: linken Daumen (Super) halten und die Taste tippen.

## Flashen und Pairing in Kürze

Siehe `README.md`: Bootloader per Doppelklick auf Reset oder `boot` auf ADJUST, UF2 auf das Laufwerk kopieren; Pairing zurücksetzen
mit den `settings_reset`-Images auf beiden Hälften, danach die Firmware auf beide.

Die linke äußere Daumentaste (sonst Super) sendet auf dieser Ebene nichts: mit gedrücktem Super würde aus `AltGr+8` ein `Super+8` (Workspace-Wechsel) statt `[`. Nur die Taste dieser Ebene halten; liegt Super schon, erst loslassen.

