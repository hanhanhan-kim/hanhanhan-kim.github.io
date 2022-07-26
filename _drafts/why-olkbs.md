---
title: Why OLKBs?
tag: HIDs
excerpt: "... or how I learned to stop worrying and love relearning how to type."
---

In `config.h`:
```c
// Tapping settings:
#define IGNORE_MOD_TAP_INTERRUPT
#define TAPPING_TERM 200 // 200 is the default value in QMK
#define TAPPING_TERM_PER_KEY
```

In `keymap.c`:
```c
// Left-hand home row mods
#define GUI_A LGUI_T(KC_A)
#define ALT_S LALT_T(KC_S)
#define SFT_D LSFT_T(KC_D)
#define CTL_F LCTL_T(KC_F)

// Right-hand home row mods
#define CTL_J RCTL_T(KC_J)
#define SFT_K RSFT_T(KC_K)
#define ALT_L LALT_T(KC_L)
#define GUI_SCLN RGUI_T(KC_SCLN)

...

// Custom per-key tapping terms for GASC homerow mods:
uint16_t get_tapping_term(uint16_t keycode, keyrecord_t *record) {
    switch (keycode) {
        case GUI_A:
          return TAPPING_TERM + 50;
        case GUI_SCLN:
          return TAPPING_TERM + 50;
        case ALT_S:
          return TAPPING_TERM + 40;
        case ALT_L:
          return TAPPING_TERM + 40;
        default:
          return TAPPING_TERM;
    }
}
```