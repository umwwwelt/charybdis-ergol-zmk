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
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| Q          | W          | E          | R          | T          ||| Y          | U          | I          | O          | P          |
| A          | HRM_S      | HRM_D      | HRM_F      | G          ||| H          | HRM_J      | HRM_K      | HRM_L      | ;          |
| Z          | X          | C          | V          | B          ||| N          | M          | ,          | .          | /          |
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| MO(PTR)    | L_TK(ESC)  | L_HM(BSP)  ||| R_HM(SPC)   | R_RC(ENT)  |
+------------+------------+------------+||+------------+------------+
```

### L2 Symbols

```text
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| ^          | <          | >          | $          | %          ||| @          | &          | *          | '          | `          |
| {          | (          | )          | }          | =          ||| \          | +          | -          | /          | "          |
| ~          | [          | ]          | _          | #          ||| |          | !          | ;          | :          | ?          |
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| MO(PTR)    | SYM_NUM    | SPACE      ||| RALT       | ▽          |
+------------+------------+------------+||+------------+------------+
```

### L3 VimNav

```text
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| CAPS       | X_CLOSE    | X_PREV     | X_NEXT     | DEL        ||| HOME       | PGDN       | PGUP       | END        | DEL        |
| X_ALL      | X_SAVE     | SHTAB      | TAB        | •          ||| LEFT       | DOWN       | UP         | RIGHT      | •          |
| X_UNDO     | X_CUT      | X_COPY     | X_PASTE    | X_REDO     ||| •          | •          | •          | •          | •          |
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| MO(PTR)    | CAPS       | LT(FN,DEL) ||| MO(FN)     | ▽          |
+------------+------------+------------+||+------------+------------+
```

### L5 NumRow

```text
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| 1          | 2          | 3          | 4          | 5          ||| 6          | 7          | 8          | 9          | 0          |
| •          | •          | •          | •          | •          ||| •          | ,          | .          | :          | /          |
| •          | •          | •          | •          | •          ||| •          | •          | •          | •          | •          |
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| MO(PTR)    | ▽          | RS(SPACE)  ||| LS(SPACE)   | ▽          |
+------------+------------+------------+||+------------+------------+
```

### L6 Function

```text
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| F1         | F2         | F3         | F4         | •          ||| C_PREV     | VOL+       | BRI+       | SLCK       | •          |
| F5         | F6         | F7         | F8         | •          ||| C_PP       | MUTE       | ALOCK      | PSCR       | •          |
| F9         | F10        | F11        | F12        | •          ||| C_NEXT     | VOL-       | BRI-       | INS        | •          |
+------------+------------+------------+------------+------------+||+------------+------------+------------+------------+------------+
| MO(PTR)    | ▽          | ▽          ||| ▽          | RESET      |
+------------+------------+------------+||+------------+------------+
```

### Legende detaillee

- `▽` = touche transparente (`&trans`), la couche inferieure decide.
- `•` = touche non assignee (`&none`), aucun evenement n'est emis.
- `HRM_X` = hold-tap home row (`tap-preferred`): tap = lettre, hold = mod.
- `HRM_S`/`HRM_D`/`HRM_F` = `LGUI`/`LCTL`/`LALT` en hold, `S`/`D`/`F` en tap.
- `HRM_J`/`HRM_K`/`HRM_L` = `LALT`/`RCTL`/`RGUI` en hold, `J`/`K`/`L` en tap.
- `MO(LAYER)` = active `LAYER` uniquement pendant le maintien (momentary layer).
- `LT(LAYER,KEY)` = hold: `LAYER`, tap: `KEY` (ex: `LT(FN,DEL)`).
- `L_TK(ESC)` = hold `LSHIFT`, tap `ESC` (`&mt LSHIFT ESC`).
- `L_HM(BSP)` = hold `VIM_NAV`, tap `BACKSPACE` (`&sc VIM_NAV BACKSPACE`, `hold-preferred`).
- `R_HM(SPC)` = hold `NUM_ROW`, tap `SPACE` (`&lt NUM_ROW SPACE`, `tap-preferred`).
- `R_RC(ENT)` = hold `SYMBOLS`, tap `ENTER` (`&sc SYMBOLS ENTER`, `hold-preferred`).
- `SYM_NUM` = `EZ_SL(NUM_ROW)`: hold = `NUM_ROW`, tap = one-shot `NUM_ROW`.
- `X_*` = raccourcis edition/navigation OS (fermer, precedent, suivant, copier, coller...).
- `C_PREV`/`C_PP`/`C_NEXT` = controles media (precedent, play/pause, suivant).
- `VOL+`/`VOL-` = volume, `BRI+`/`BRI-` = luminosite ecran.
- `ALOCK` = verrouillage alphabetique (`C_AL_LOCK`), `SLCK` = Scroll Lock.

## Trackball droite

- Device tree: `config/boards/shields/charybdis/charybdis_right.overlay`
- `compatible = "pixart,pmw3610"`
- `scroll-layers = <4>`
- `snipe-layers = <3>`

## Build CI

Le workflow CI produit notamment:

- `charybdis_ergol_vim_left`
- `charybdis_ergol_vim_right`
