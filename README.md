# Mriya46 Choc — ZMK config

ZMK firmware configuration for the Mriya46 split keyboard (Choc switches,
nRF52840).

- ZMK is pinned to a stable release in `config/west.yml` (`# zmk-revision` marker).
- `config/boards/arm/mriya` — legacy board definition for ZMK v0.x (Zephyr 3.5).
- `hwmv2/boards/mriya` — HWMv2 board definition for ZMK main (Zephyr 4.x).
- `config/mriya.keymap` — the keymap; `config/mriya.json` — layout for
  [keymap-editor](https://nickcoutsos.github.io/keymap-editor/).
- [ZMK Studio](https://zmk.dev/docs/features/studio) is supported via the
  `*_studio` firmware (USB connection); unlock with the `&studio_unlock` key on
  the Control layer.
- Layer diagrams and the flashing guide live in the umbrella repo:
  [zmk-buildroot](https://github.com/grinderz/zmk-buildroot).

## Building

GitHub Actions builds every target from `build.yaml` on push.

Local Docker builds are driven from the umbrella repository
([zmk-buildroot](https://github.com/grinderz/zmk-buildroot)), which includes
this repo as a submodule:

```sh
make mriya46-choc                  # every firmware target of this keyboard
make mriya46-choc-left-studio      # a single target
make ZMK_REV=main PRISTINE=1 mriya46-choc   # against ZMK main (uses hwmv2 board)
```
