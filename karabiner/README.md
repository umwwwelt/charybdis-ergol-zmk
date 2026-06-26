# Karabiner MacBook

Config Karabiner-Elements pour retrouver les comportements principaux du Charybdis sur le clavier integre du MacBook.

## Installation

1. Ouvrir Karabiner-Elements.
2. Aller dans `Complex Modifications` puis `Add your own rule`.
3. Coller le contenu de `karabiner/charybdis-macbook.json`.
4. Activer la regle `Charybdis MacBook internal keyboard`.
5. Dans `Devices`, garder cette configuration pour le clavier interne Apple. Eviter de l'appliquer a un clavier externe si le Charybdis est branche.

## Mapping

Touches pouce simulees :

- `left_option` : tap `Esc`, hold `Shift`
- `left_command` : tap `Backspace`, hold `VimNav`
- `spacebar` : tap `Space`, hold `NumRow`
- `right_command` : tap `Enter`, hold `Symbols`

Home-row mods :

- `s` hold = `Ctrl`, tap = `s`
- `d` hold = `Cmd`, tap = `d`
- `f` hold = `Option`, tap = `f`
- `j` hold = `Option`, tap = `j`
- `k` hold = `Cmd`, tap = `k`
- `l` hold = `Ctrl`, tap = `l`

VimNav : maintenir `left_command` puis utiliser :

- `h/j/k/l` : fleches gauche/bas/haut/droite
- `y/u/i/o/p` : `Home/PageDown/PageUp/End/Delete`
- `a/s/d/f` : `Cmd+A`, `Cmd+S`, `Cmd+Shift+Tab`, `Cmd+Tab`
- `z/x/c/v/b` : undo, cut, copy Ergo-L (`Cmd+W`), paste, redo Ergo-L (`Cmd+P`)
- `e/r` : precedent/suivant avec `Option+Left/Right`

## Limites

- Les layers `NumRow` et `Symbols` sont volontairement minimalistes.
- Le layer `Symbols` utilise des keycodes macOS classiques. Selon le layout OS Ergo-L actif, certains symboles peuvent demander un ajustement.
- Les comportements ZMK firmware (`bootloader`, `reset`, `studio_unlock`, trackball, one-shot layers exacts) ne sont pas portes.
