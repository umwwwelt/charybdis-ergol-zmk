# Charybdis Ergol ZMK

Config ZMK pour Charybdis 5x3 + trackball droite, inspiree de Selenium.

## Profil actif

- `KB_LAYOUT_ERGOL`
- `MACOS`
- `HT_HOME_ROW_MODS`
- `VIM_NAVIGATION`

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

## Apercu ASCII des touches

Notation: `HRM_X` = home-row mod, `LT` = layer-tap, `MO` = momentary layer.

### L0 Base

```text
TAB   Q      W      E      R      T   |   Y      U      I      O      P      BSPC
ESC   A      HRM_S  HRM_D  HRM_F  G   |   H      HRM_J  HRM_K  HRM_L  ;      ENTER
LSFT  Z      X      C      V      B   |   N      M      ,      .      /      RSFT

             LTH_TK LTH_HM LTH_RC      RTH_RC RTH_HM RTH_TK
```

### L2 Symbols

```text
TRNS  ^      <      >      $      %   |   @      &      *      '      `      TRNS
TRNS  {      (      )      }      =   |   \      +      -      /      "      TRNS
TRNS  ~      [      ]      _      #   |   |      !      ;      :      ?      TRNS

             SYM/NUM SPACE  ENTER       TRNS   RALT   TRNS
```

### L3 VimNav

```text
TRNS  CAPS   X_CLOSE X_PREV X_NEXT NONE | HOME   PGDN   PGUP   END    DEL    TRNS
TRNS  X_ALL  X_SAVE  SHTAB  TAB    NONE | LEFT   DOWN   UP     RIGHT  NONE   TRNS
TRNS  X_UNDO X_CUT   X_COPY X_PASTE X_REDO | NONE NONE  NONE   NONE   NONE   TRNS

             CAPS   LT(FN,DEL) MO(NUMROW)   TRNS MO(FN) OSM(RALT)
```

### L5 NumRow

```text
TRNS  RS(1)  RS(2)  RS(3)  RS(4)  RS(5) | LS(6)  LS(7)  LS(8)  LS(9)  LS(0)  TRNS
TRNS  1      2      3      4      5     | 6      7      8      9      0      TRNS
TRNS  NONE   NONE   NONE   NONE   NONE  | -      ,      .      :      /      TRNS

             TRNS   RS(SPC) TRNS         TRNS   LS(SPC) RALT
```

### L6 Function

```text
TRNS  F1  F2  F3  F4  NONE | NONE C_PREV VOL+ BRI+ SLCK  TRNS
TRNS  F5  F6  F7  F8  NONE | NONE C_PP   MUTE ALOCK PSCR TRNS
TRNS  F9  F10 F11 F12 NONE | NONE C_NEXT VOL- BRI- INS   TRNS

             MO(POINTER) TRNS BOOT       SYSRST TRNS STUDIO
```

### L7 Pointer / L8 Scroll

```text
Pointer: clics souris sur la main droite + acces MO(SCROLL) au pouce.

... ... ... ... ... ... | ... ... ... ... ... ...
... ... ... ... ... ... | ... LCLK MCLK RCLK ... ...
... ... ... ... ... ... | ... ...  ...  ...  ... ...

             ... ... ...             MO(SCROLL) ... ...
```

## Trackball droite

- Device tree: `config/boards/shields/charybdis/charybdis_right.overlay`
- `compatible = "pixart,pmw3610"`
- `scroll-layers = <8>`
- `snipe-layers = <7>`

## Build CI

Le workflow CI produit notamment:

- `charybdis_ergol_vim_left`
- `charybdis_ergol_vim_right`
