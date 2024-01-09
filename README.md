# Lisa Breakout Board
A power, floppy, keyboard, etc. breakout board for the Apple Lisa. You can use this board in lieu of having an actual Lisa case which provides the display, PSU, floppy drive, etc. This allows you to run the card cage outside of a Lisa with a standard ATX power supply.

For a display, I use the video out connector on the motherboard a with RGB2HDMI adapter.

This has only been tested with the Lisa 2/5 (see details of my machine below).

![Wide rectangular green citcult board with two edge connetors at the bottom, several jacks installed on either side, and an Arduino Nano Pro in the middle](https://github.com/RolandJuno/Lisa_Breakout/blob/main/Lisa%20Breakout%20Board.jpg)

## Features
Connects to the Lisa power/video and floppy edge connectors on the motherboard to provide the following functions:

- Power switch
- Power LED
- Sound output RCA jack
- 20/24 pin ATX power input
- optional 7905 voltage regulator for -5V generation
- Selectable -5V source for 7905 or 20-pin ATX connector
- Lisa keyboard input jack
- Mac M0110/A keyboard input jack and on-board conversion to Lisa keyboard using my fork of [Warmech's M0110 Mac Keyboard to Lisa Adapter](https://github.com/RolandJuno/m0110-to-lisa-keyboard-adapter)
- Sony 800K floppy drive connector (front and back of card ports) [Note: only tested with a FloppyEmu]
- ATX power voltage breakout test points
- Audio/video output block for testing/troubleshooting

## Potential Incompatibility

I initially experienced issues with the breakout board and my Lisa. It would usually boot successfully at a cold start and continue working fine. After a reboot or power cycle, it would get stuck with garbage on the screen (before it clears and POST starts).

My Lisa consisted of the following:

- New clone motherboard
- New clone 2/5 IO board (with EPROM for a PROM)
- Original rev D CPU board (possibly only use in the Lisa 2/10?) (with EPROM for a PROM)
- Original SunRem 2MB RAM board

I swapped in an orignal rev B CPU card (*usually in a Lisa 2/5) and the issue went away. Caveat emptour.

## Assembly

Follow the silkscreen for which side the components are soldered onto. For instance, the two edge connectors at the bottom are on one side while the ATX power input IS ON THE OPPOSITE SIDE. If you get this wrong, you'll send voltages to the wrong places which would be bad.

### -5V Rail

Choose one of the following power sources. Don't jumper both power sources.

- If you use an ATX power supply that provies -5V (20 pin variety typically do), you can opt to NOT install the 7905 and the two caps on either side. Jumper the right two pins of JP1 (ATX).

- If you use an ATX power supply that does not provide -5V (24 pins typically do not), you should install the 7905 regulator and the two caps on either side. Jumper the left two pins of JP1 (7905). NOTE: The silkscreen for the 7905 regulator should be spun 180 around (text on the chip should face the keyboard connectors)

### Keyboard

Choose one of the following keyboard types. Don't plug in a Lisa keyboard when you're using the Mac keyboard converter.

- If you have a Lisa keyboard, you can omit the 4P4C telephone jack, the Arduino Pro Micro, and the two its two buttons (KB RESET and KB MODE). Install the 1/4" input jack and plug your keyboard in (while the system power is unplugged!)

- If you have a Mac M0110A keyboard, you can omit the 1/4" input jack. Install the 4P4C telephone jack, the Arduino Pro Micro, and its two buttons (KB RESET and KB MODE). I suggest installing the Arduino Pro Micro in a standard 24 pin DIP socket. The configuration solder pads are already jumpered to defaults of using a standard Mac coil cable (not a telephone cable) and a US layout. Flash the Arduino with [Warmech's M0110 Mac Keyboard to Lisa Adapter](https://github.com/warmech/m0110-to-lisa-keyboard-adapter)


## BOM

Not all parts are needed. See assembly instructions for details.

### Must haves
- [60 position floppy edge connector](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/1-5530841-8/2310823)
- [30 position power/video edge connector](https://www.digikey.com/en/products/detail/sullins-connector-solutions/EBM15DRXH/927296)
- [24 pin ATX power connector MiniFit Jr 44206](https://www.digikey.com/en/products/detail/molex/0442060002/3311016) (Note: This also works with a 20 pin ATX power supply. The plug will only fit in one way and the voltages match up. Four pins will be left empty.)
- [20 pin floppy header](https://www.digikey.com/en/products/detail/sullins-connector-solutions/SBH11-PBPC-D10-ST-BK/1990065)
- [Tact swiches](https://www.mouser.com/ProductDetail/Apem/MJTP1230?qs=ooeArD5nza9YuOFpo4pJ2Q%3D%3D) x 2
- [2N4401 transistor](https://www.digikey.com/en/products/detail/nte-electronics-inc/2N4401/11649865)
- 40K Ohm resistor (for soft power-on)
- 3.3K Ohm resistor (for keyboard port pull-down)
- 150 Ohm resistor (for LED)
- LED of your choice (I used red)

### You have a Lisa keyboard
- [1/4" stereo headphone jack](https://amzn.to/3QI4mLv)

### You have a Mac M0110/A keyboard
- [Arduino ProMicro 5V](https://amzn.to/3sHc1lu)
- [4P4C modular jack](https://www.digikey.com/en/products/detail/assmann-wsw-components/A-2004-3-4-LP-N-R/2183632)
- [Tact swiches](https://www.mouser.com/ProductDetail/Apem/MJTP1230?qs=ooeArD5nza9YuOFpo4pJ2Q%3D%3D) x 2

### Your PSU does not provide -5V
- [7905 -5V regulator](https://www.digikey.com/en/products/detail/onsemi/MC7905BTG/1481513) (install text facing the keyboard connectors)
- 0.1 uF capacitors x 2

### You want sound out
- [RCA jack for speaker out](https://www.digikey.com/en/products/detail/cui-devices/RCJ-043/408507)

## Errata

- The silkscreen for the 7905 regulator should be spun 180 around (text on the chip should face the keyboard connectors)
- GND and AGND are not connected and should be. This is easily fixed by soldering a short jumper between AGND and GND on the Audio_Video 2x3 jumper block.

