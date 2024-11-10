# Sofle v2.0w ZMK Configuration

This is a custom configuration for the Sofle v2.0w (as found here: https://github.com/josefadamcik/SofleKeyboard/pull/180).

## Installation

Refer to the [v2 build guide](https://josefadamcik.github.io/SofleKeyboard/build_guide.html) for installation instructions.

Note that the Bill of Materials (BOM) is slightly different:
- Uses nice!nanov2
- ALPS power switch
- JST connectors for battery
- Removal of the TRRS connectors
- Kailh MX or Choc hotswap switch support
- Optional nice!view

## Usage

Regarding the batter/JST connections:

The JST can be soldered two different ways on the PCB. I took advantage of this to ensure that my batteries were using the
same +/- orientation in their connector so that they were interchangeable between sides. This required that the connector on
the board was installed differently per side. Minor thing to remember during build for the ease of battery interchange later.

To use the nice!view:
1. Enable `nice_view_adapter` in `build.yaml` of zmk-config.
2. Override `cs-gpios` in `sofle.keymap` file of zmk-config:
    ```c
    &nice_view_spi { cs-gpios = <&pro_micro 0 GPIO_ACTIVE_HIGH>; };
    ```
## References

- [Sofle Keyboard Main Repository](https://github.com/josefadamcik/SofleKeyboard)
- [ZMK Docs](https://zmk.dev/docs)

## Thanks
A huge thanks to @GarrettFaucher for the wireless mod! 🥇 And, of course @josefadamcik for the Sofle.
