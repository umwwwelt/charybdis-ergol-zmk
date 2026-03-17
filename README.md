# Charybdis Ergol ZMK

Config ZMK pour Charybdis 5x3 + trackball droite, inspiree de Selenium.

## Profil actif
- layout OS: Ergol (firmware en keycodes qwerty)
- `MACOS`
- `HT_TWO_THUMB_KEYS` (mode Selenium 34 touches)
- `VIM_NAVIGATION`
- 3e pouce gauche dedie: `MO(POINTER)`

## Index des layers

- `0` Base
- `1` NumLock
- `2` Symbols
- `3` VimNav
- `4` NavNum
- `5` NumRow
- `6` Function
- `7` Pointer
- `8` Scroll

## Apercu (grille 5x3 avec contour)

Le clavier est documente ici en **5x3 reel** (pas en projection 6x3 Selenium), dans une grille propre avec contour.

### L0 Base (Ergo-L + Vim + 2TK)

```text
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
| Q     | W     | E     | R     | T     ||| Y     | U     | I     | O     | P     |
| A     | HRM_S | HRM_D | HRM_F | G     ||| H     | HRM_J | HRM_K | HRM_L | ;     |
| Z     | X     | C     | V     | B     ||| N     | M     | ,     | .     | /     |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
|       | MO_PTR|L_TKESC|L_HMBSP|       |||       |R_HMSPC|R_RCENT|       |       |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
```

- `HRM_*` = hold-tap home row (tap lettre, hold modificateur).
- `L_TKESC` = hold `LSHIFT`, tap `ESC`; `L_HMBSP` = hold `VIM_NAV`, tap `BACKSPACE`.
- `R_HMSPC` = hold `NUM_ROW`, tap `SPACE`; `R_RCENT` = hold `SYMBOLS`, tap `ENTER`.
- `MO_PTR` = `MO(POINTER)` maintenu.

### L2 Symbols

```text
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
| ^     | <     | >     | $     | %     ||| @     | &     | *     | '     | `     |
| {     | (     | )     | }     | =     ||| \     | +     | -     | /     | "     |
| ~     | [     | ]     | _     | #     ||| |     | !     | ;     | :     | ?     |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
|       | MO_PTR|SYM_NUM| SPACE |       |||       | RALT  |   ▽   |       |       |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
```

- `SYM_NUM` = `EZ_SL(NUM_ROW)` (hold `NUM_ROW`, tap one-shot `NUM_ROW`).
- `RALT` = AltGr; `▽` = transparent (`&trans`).

### L3 VimNav

```text
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
| CAPS  |X_CLOSE|X_PREV |X_NEXT | DEL   ||| HOME  | PGDN  | PGUP  | END   | DEL   |
| X_ALL |X_SAVE | SHTAB | TAB   | •     ||| LEFT  | DOWN  | UP    | RIGHT | •     |
| X_UNDO| X_CUT | X_COPY|X_PASTE| X_REDO||| •     | •     | •     | •     | •     |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
|       | MO_PTR| CAPS  |FN_DEL |       |||       | MO_FN |   ▽   |       |       |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
```

- `X_*` = raccourcis OS (fermer, precedent, suivant, copier/coller, etc.).
- `FN_DEL` = `LT(FUNCTION,DEL)` (hold `FUNCTION`, tap `DEL`).
- `MO_FN` = `MO(FUNCTION)` maintenu.

### L5 NumRow

```text
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
| 1     | 2     | 3     | 4     | 5     ||| 6     | 7     | 8     | 9     | 0     |
| •     | •     | •     | •     | •     ||| •     | ,     | .     | :     | /     |
| •     | •     | •     | •     | •     ||| •     | •     | •     | •     | •     |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
|       | MO_PTR|   ▽   |RS_SPC |       |||       |LS_SPC |   ▽   |       |       |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
```

- `RS_SPC` / `LS_SPC` = `Shift+Space` droite/gauche.
- `▽` = transparent (`&trans`).

### L6 Function

```text
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
| F1    | F2    | F3    | F4    | •     |||C_PREV | VOL+  | BRI+  | SLCK  | •     |
| F5    | F6    | F7    | F8    | •     ||| C_PP  | MUTE  | ALOCK | PSCR  | •     |
| F9    | F10   | F11   | F12   | •     |||C_NEXT | VOL-  | BRI-  | INS   | •     |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
|       | MO_PTR|   ▽   | BOOT  |       |||       | RESET |STUDIO |       |       |
+-------+-------+-------+-------+-------+||+-------+-------+-------+-------+-------+
```

- `BOOT` = bootloader, `RESET` = reset firmware, `STUDIO` = `studio_unlock`.
- `C_PREV`/`C_PP`/`C_NEXT` = controles media (precedent, play/pause, suivant).
- `VOL+`/`VOL-` = volume, `BRI+`/`BRI-` = luminosite ecran.
- `ALOCK` = verrouillage alphabetique (`C_AL_LOCK`), `SLCK` = Scroll Lock.
- `•` = touche non assignee (`&none`).

## Trackball droite

- Device tree: `config/boards/shields/charybdis/charybdis_right.overlay`
- `compatible = "pixart,pmw3610"`
- `scroll-layers = <4>`
- `snipe-layers = <3>`

## Build CI

Le workflow CI produit notamment:

- `charybdis_ergol_vim_left`
- `charybdis_ergol_vim_right`
