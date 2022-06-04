# RGB Cooling HAT

This repository aims to control the RGB fan and more of
`YB-EPV02` via I2C protocol.

### Features

- Auto changes the fan speed according to current tempearture.
- Full manager utility `rgb-cooling-hat` for fan/RGB control.
- Provides I2C write (8/16 Bit) feature via `i2cw` command.
- Show current `Freq` and `Temp` if OLED display available.

### Pre-required

Hardware:
- `YB-EPV02` and compatable board
  (e.g. Raspberry Pi, Rock Pi...)
- Enable I2C feature for GPIO pins
  (using device tree overlay)

Dependency:
- bash
- systemd (optional)
- cargo (make)
- git (make)

### Install

- Arch Linux

  change `pwd` into subdir `AUR`,
  then using `makepkg`:

  ``` shell
  $ makepkg -csi
  ```

- Others

  Install all files:

  ``` shell
  $ make install
  ```

  Optional enable the fan control service:

  ``` shell
  $ systemctl enable --now rgb-cooling-hat
  ```

### Uninstall

If you enable the fan control service previous,
firstly disable it:

``` shell
$ systemctl disable --now rgb-cooling-hat
```

Uninstall all files:

``` shell
$ make uninstall
```

### License

This repository is unofficial and working myself,
all code of this repository are under `MPL-2.0`,
so any modifies should be open source.
