# Building Gudie

![](pic/guide/all.jpg)

## Basic Install Process

### Diodes

1N4148 is the most commonly used diode in mechanical keyboards, there are `SMD` type and `THT` type, here we use the SMD type, the direction corresponds to the following picture:

![](pic/guide/dio.png)

SMD diodes are quite tiny and require a little twisting of the light with tweezers to bring out their direction, so our first step is to mount the diodes in a total of `25 places` on the top of the keyboard:

![](pic/guide/dio2.jpg)

### Hot-swap Sockets

After mounting the diode, solder the hot-swap sockets:

![](pic/guide/hs.jpg)

Blank supports both `Choc` and `GLP` hot-swap socket, you can choose one to install, the pin layout is as shown below:

![](pic/guide/hs2.jpg)

Connect the jumper `P1` under the TRRS after installation:

- `P1` is the default power connection protocol for TRRS, which is basically used by ATMega32U4 ProMicro and RP2040 ProMicro.

> If the RP2040 ProMicro shows `Communication Problems` on the left and right side, please remove the solder on `P1` and change to `P2` and do the communication test again.

![](pic/guide/p1.jpg)

### MCU

Then install the MCU according to the place on the board and the `VCC` and `GND` on the top, with the chip side facing down.

> The pins are available in either THT or plug-in versions. For testing reasons, the photo shows the plug-in version, so please refer to it.

![](pic/guide/m2.jpg)
![](pic/guide/m3.jpg)

> The plug-in pin header installation.

![](pic/guide/m4.jpg)

Next install the `TRRS jack` and the `2pin tactile switch` (you don't need to install the TRRS jack if you only need to install a single-side keyboard).

![](pic/guide/cd1.jpg)

## Cirque 40mm Trackpad Module

- Please be sure to read through the gudie of beekeeb and Keycapsss, the information in both guides will be combined in below:

    - [Cirque Trackpad i2c on Corne Keyboard Build Log](https://beekeeb.com/cirque-trackpad-i2c-on-corne-keyboard/)。
    - [GlidePoint Cirque Trackpad with Adapter PCB](https://keycapsss.com/help/cirque-trackpad/#spi-or-i2c)。

In order to design this keyboard I ordered the trackpad module kit from the web store, and then bought an FFC connector to build the keyboard on.

- The structure of the keyboard takes reference from beekeeb and bastardkb [Dilemma](https://docs.bastardkb.com/bg_dilemma/v2.html) design, the FFC connector will be installed on the back side of the board, on the same side as the hot-swap sockets (please see the photo below for comparison).
- Use the two guides to install the module kit, the length of the spacers posts will need to be adjusted.
- Blank uses `I2C` mode to drive the trackpad.

> The photo is from beekeeb:

![](https://beekeeb.com/trackpad/side.jpg)

> After finishing the Blank:

![](pic/guide/c1.jpg)

Below is a combined information of two trackpad module kit guides from beekeeb and Keypasss:

- The `I2C` mode requires to remove some components on the trackpad PCB and add ones that need to be installed:

|MCU|IC|VCC|Resistor R1|Resistor R7|Resistor R8|4.7K pull-up resistor|
|--|--|--|--|--|--|--|
|ProMicro|ATMega32U4|5V|Remove|Remove|Remove|Needed|
|ProMicro|RP2040|3V3|Remove|-|-|Needed|

> The trackpad photo is from Keycapsss：

![](https://keycapsss.com/help/static/7bc572ccf60a0ee520e6b4f3219e6dff/29d31/resistor-i2c-5v-1.jpg)

### FFC Socket

![](pic/guide/c2.jpg)

It is difficult to solder the FFC connector with a soldering iron, so it is recommended to use a hot plate or a heat gun to solder it to the PCB.

![](pic/guide/h1.jpg)

> It is important to note that a certain amount of `flux` will need to be brushed onto the hot plate.

![](pic/guide/h2.jpg)

After the FFC connector is mounted, attach the cable to it.

![](pic/guide/h3.jpg)

After attaching the cable, go the cable through the holes on the underside to the other side.

![](pic/guide/h4.jpg)

### Pull-up Resistor

![](pic/guide/r1.jpg)

The pull-up resistor part is very simple, bend the pins slightly, insert them into the pad holes on R1 and R2, solder them, and remove the unnecessary parts.

![](pic/guide/r2.jpg)

### FFC Adapter (I2C Adapter)

- Attention when installing the adapter:

    - Before installation, all I2C `jumper`s on the front side of the PCB must be connected for normal use (check the picture below).
    - The FFC connector adapter is a module developed by the store to allow users to install it freely, and the installation method should be referred to the guides of the store.
    - The use of the adapter will increase the thickness of the mounting position, so you need to adjust the height of the `spacer' by yourself.

![pcb1](pic/guide/pcb1.png)

### Covers

![](pic/guide/t1.jpg)

After removing the resistors from the trackpad, assemble the trackpad body and the 3 covers together. First of all, the diameter of the holes in the cover `A` and `C` are not the same, and the order of the cover up and down is different depending on the components installed.

![t7](pic/guide/t7.png)

Then place cover `A` and `B` in pairs and lay them flat.

![](pic/guide/t2.jpg)

The trackpad is placed in the middle, and don't worry about installation errors.

![](pic/guide/t3.jpg)

Then stack the cover `C` plates on top of each other.

![](pic/guide/t4.jpg)

Finally screw together with `6mm screws` and `nuts`.

![](pic/guide/t6.jpg)
![](pic/guide/t5.jpg)

## Rotray Encoder (Knob)

Installation of the rotary encoder part is quite simple, just follow the correct pin layout and solder it.

![](pic/guide/e1.jpg)

## Case

![](pic/guide/b1.jpg)

The bottom plate will be fitted with screws of the correct length for the places shown in the photo, and the installation process will be explained later.

Firstly, the `8mm screws` will be screwed in place with `nuts`.

![](pic/guide/b2.jpg)

The `4mm screw` part will be held in place with the `5mm` spacers and the washers.

![](pic/guide/b3.jpg)

After putting the washers on the screws, set them aside for now until you can use them.

![](pic/guide/b4.jpg)

## Last Step

No matter whether the optional part is a trackpad or a rotray encoder, the final installation is basically the same.

### Trackpad

The first part is to build up the trackpad, place the PCB against the bottom plate and install the correct length of spacers as shown in the photo.

![](pic/guide/l1.jpg)
![](pic/guide/l2.jpg)

Then connect the FFC cable to the connector on the trackpad, follow the direction of the cable and put the plate into the screw holes, and screw it up with `6mm screws`.

![](pic/guide/l3.jpg)
![](pic/guide/l4.jpg)

Lastly, screw the plate and the MCU cover with `3mm screws` in order.

![](pic/guide/l5.jpg)
![](pic/guide/l10.jpg)

### Rotray Encoder (Knob)

![](pic/guide/l6.jpg)

The same is done for the rotray encoder part, place the PCB on the bottom plate and install the spacers with the correct length.

Then install the cap.

![](pic/guide/l7.jpg)

The covers at the encoder will be stacked in the reverse direction of the trackpad, so you can install the rotray encoder directly after screwing.

![](pic/guide/t8.png)
![](pic/guide/l8.jpg)

Finally, turn the keyboard over to the back and put on the `cushion rubber` and you're done.

![](pic/guide/l9.jpg)

## Switches and Keycaps

Keyswitches and keycaps can be installed at the end, depending on your choice. Here, we used Kailh Choc v2 Black Cloud.

![](pic/info/info1.jpg)

The keycaps used are Tai-hao THT low profile, blank version.

![](pic/info/info2.jpg)

DONE!

![](pic/info/info4.jpg)

### Firmware

> The firmware installation process can be different. If you want to flash before building the keyboard, please use the correct method for the MCU you want to use.

- Before building:

    - ATMega32U4 ProMicro: can use `QMK Toolbox` or `QMK MSYS` to flash the firmware.
    - RP2040 ProMicro: drive `RP_BOOT` mode, then put the `.uf2` firmware to the hard-disk。

> It have 2 methods to drive the `RP_BOOT` mode:
> 1. Press the `BOOT` button on the MCU then plug in to your device.
> 2. After plugging into the device, press the `BOOT` botton about 1 second, then press the botton `RESET`.

- After building:

    - ATMega32U4 ProMicro: can use `QMK Toolbox` or `QMK MSYS` to flash the firmware, one press the `RESET` botton to drive the flash mode。
    - RP2040 ProMicro: press twice the `tactile switch` (`RESET`) on the PCB side and hold 1 second, then it will drive the `RP_BOOT` mode, put the `.uf2` firmware to the hard-disk to flash.

> There are also having `RESET` and `BOOT` holes on the back of the MCU that can be triggered by tweezers, so you don't have to worry about flashing issue.

### Debug

> RP2040 ProMicro `Communication problem`, please remove the `P1` jumper on the board and change it to `P2` connection and test again.

> For the keyboard keyswitches section, turn on `VIAL` and go to `Matrix Tester`, if you have to tap keyswitches go through all of them, if not use tweezers to test for `solder pads` or `pins` on each key.

![](pic/guide/n1.png)

> To test the keys on the top of the rotary encoder, open the switch against the `Layout` section and test with the `Matrix Tester`.

![](pic/guide/n2.png)






