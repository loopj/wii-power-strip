<p align="center">
  <img src="images/power-strip-logo-black.svg#gh-light-mode-only" />
  <img src="images/power-strip-logo-white.svg#gh-dark-mode-only" />
</p>

<h3 align="center">Slimline PCB to supply power to trimmed Wii motherboards</h3>

<p align="center">
  <img src="images/power-strip-render.png" />
</p>

## Features

- Solders directly onto the top of a Wii motherboard
- Supplies power to the 1V, 1.15V, 1.8V, and 3.3V points
- Power connector allows for modular builds without soldering/desoldering wires
- Adds pads for the relocation of capacitors (C5, C189, C200) typically removed on more aggressive trims
- Pad for an optional thermistor, for compatibility with [4Layer Technologies RVL-PMS](https://4layertech.com/collections/modular-line/products/rvl-pms-2)
- Fits entirely within the outline of an Omega trim
- Fits under heatplates/heatsinks

## Notes

### Connector current capacity

The connector currently used on this board is the [5-pin, 1.5mm pitch Molex Pico-Lock](https://www.molex.com/en-us/products/part-detail/5040500591) connector. This connector accepts a maximum wire gauge of 24AWG which **may not be a beefy enough wire gauge for all Wii builds**. The main area of potential concern is the ground return path, which uses a single wire.

For Short Stack I am cheating - I am using aluminum spacers between the Short Stack main PCB and the Wii motherboard which provide an additional ground return path through the plated mounting holes.

Having said this, in my testing this connector has shown to be sufficient and stable, even when using non-conductive spacers.

In a future revision I would likely swap out this connector for either:
- [6-pin, 1.5mm pitch Molex Pico-Lock](https://www.molex.com/en-us/products/part-detail/5040500691) - doubling up on the ground wires
- [Pico-EZMate HC, 1.8 pitch](https://www.molex.com/en-us/products/connectors/wire-to-board-connectors/pico-ezmate-connectors) - very low profile, higher current connector

### C189 height

Some motherboard revisions have a very tall (~2.9mm) C189 capacitor, which can interfere with heatplates. If you have one of these boards, you may wish to consider purchasing a lower profile capacitor. As long as it is a 220uF, 6.3V+, 2917 or 2312 SMD package capacitor it should work fine. The Kyocera AVX NOJC227M006RWJ is a low profile version of the original cap used on the Wii. The TAJX227K006RNJ or TAJY227K006RNJ should also both work.

## How to order

- Grab the Gerber files for the [latest release](https://github.com/loopj/wii-power-strip/releases/latest)
- Order a 2-layer, 0.6mm PCB from JLCPCB or similar fab
- Purchase a Molex 504050-0591 connector from [DigiKey](https://www.digikey.com/en/products/detail/molex/5040500591/9352715), [Mouser](https://www.mouser.com/ProductDetail/Molex/504050-0591?qs=OAhjpuo3Vu7FoUIT4KH7/g%3D%3D), or your favorite component store
- Don't forget to purchase either pre-assembled cables, or parts to crimp your own
- Optional - 10KΩ thermistor with a 3380K B value, in an 0603 SMD package

## Installation

- If you are doing a motherboard trim that will trim off C5 or C189, desolder these and save them
- If you are doing a NAND relocation which removes C200, desolder this and save it
- Solder the connector and any rescued capacitors to the board by hand or using a hot plate
- Place board on the Wii motherboard, it should self-align
- Solder the pads on the edge of the board to the Wii motherboard
    - GND pad solders to the bottom of C180
    - 1V0 pad solders to the top of C143
    - 1V15 pad solders to the left of C17
    - 1V8 pad solders to the via array at the top left. You may wish to scratch away some solder mask to have more copper to solder to
    - 3V3 pad solders to the top of C128
- Use plenty of solder and flux!

## License

Permissively released under the Solderpad Hardware License v2.1
