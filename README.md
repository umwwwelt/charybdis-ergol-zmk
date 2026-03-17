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

## Apercu (layout physique 5x3)

Le clavier est documente ici en **5x3 reel** (pas en projection 6x3 Selenium), avec un decalage visuel proche des colonnes physiques.

### L0 Base (Ergo-L + Vim + 2TK)

```text
Gauche                                  Droite
  Q      W      E      R      T           Y      U      I      O      P
    A    HRM_S  HRM_D  HRM_F  G         H      HRM_J  HRM_K  HRM_L    ;
  Z      X      C      V      B           N      M      ,      .      /

               MO(PTR)  LTH_TK  LTH_HM   RTH_HM(SPACE)  RTH_RC
```

### L2 Symbols

```text
Gauche                                  Droite
  ^      <      >      $      %           @      &      *      '      `
    {    (      )      }      =         \      +      -      /      "
  ~      [      ]      _      #           |      !      ;      :      ?
```

### L3 VimNav

```text
Gauche                                  Droite
  CAPS   X_CLOSE X_PREV  X_NEXT DEL       HOME   PGDN   PGUP   END    DEL
    X_ALL X_SAVE  SHTAB  TAB    •       LEFT   DOWN   UP     RIGHT  •
  X_UNDO  X_CUT   X_COPY X_PASTE X_REDO   •      •      •      •      •
```

### L5 NumRow

```text
Gauche                                  Droite
  1      2      3      4      5           6      7      8      9      0
    •    •      •      •      •         •      ,      .      :      /
```

### L6 Function

```text
Gauche                                  Droite
  F1     F2     F3     F4     •           C_PREV VOL+   BRI+   SLCK   •
    F5   F6     F7     F8     •         C_PP   MUTE   ALOCK  PSCR   •
  F9     F10    F11    F12    •           C_NEXT VOL-   BRI-   INS    •
```

### Legende detaillee

- `▽` = touche transparente (`&trans`), la couche inferieure decide.
- `•` = touche non assignee (`&none`), aucun evenement n'est emis.
- `HRM_X` = home-row mod: tap = lettre `X`, hold = modificateur associe.
- `MO(LAYER)` = active `LAYER` uniquement pendant le maintien.
- `LTH_*` / `RTH_*` = comportements hold-tap des pouces (defines dans `hold_taps.dtsi`).
- `X_*` = raccourcis edition/navigation OS (fermer, copier, coller, etc.).
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
