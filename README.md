# Artillery SideWinder X1v4 

## What is this repository?

A collection of software and links to what makes the printer run, especially with all the modifications.

## Config

Changed from stock:

- Updated stock TFT firmware to a custom one: https://www.thingiverse.com/thing:4294049/files (Marlin 2.0.9.3, firmware ver. 1.0.27.x patch 9.5)

- Upgraded all stock motor drivers to TMC2208s (STEP/DIR version)

- Updated stock MKS Gen L v1.0 (ATMega2560) board to BigTreeTech MKS V1.4 non-turbo (LPC1768, 100MHz, 32b)

- Flashed firmware of BTT MKS v1.4 (Marlin 2.0.9.1)

- Installed PEI metal printbed (https://www.amazon.com/gp/product/B08PFJBLNB/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1)

- (Occasionally) using RPi with Octoprint for remote printing.

## Resources and Links

### TFT firmware
See https://www.thingiverse.com/thing:4294049/files. Download file with `fw` in the name

### MKS v1.4 board upgrade
Mostly following https://www.thingiverse.com/thing:4836744, but:

- Jumpers are connected for STEP/DIR instead of UART mode in the guide. Connect all four jumpers in the left position for each.

- Black reset wire (red/black; red is ground for some reason) is put into the RESET pin. This is the pin that was not connected when connecting TFT wires.

- Custom mount not used (after flashing program)

- Non turbo - use LPC1768 instead of 1769.

- Motor drivers are `TMC2208_STANDALONE`

- `SERIAL_PORT` is 0, `SERIAL_PORT_2` is -1.

- Skip most TMC settings (Since it's not UART).

- Enable misc support (M701/M702, etc.)

### Octoprint

