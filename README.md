## Adafruit ATtinyx16 Breakouts with seesaw - STEMMA QT / Qwiic PCB

<a href="http://www.adafruit.com/products/5681"><img src="assets/5681-04.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>
<a href="http://www.adafruit.com/products/5690"><img src="assets/5690-01.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit ATtiny816 and ATtiny1616 Breakouts with seesaw - STEMMA QT / Qwiic. 

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/5681
* https://www.adafruit.com/product/5690

### Description

These breakout boards are a "three in one" product:

* The ATtinyx16 are part of the 'next gen' of AVR microcontrollers, and now we have cute development/breakout boards for them, with just enough hardware to get the chip up and running.
* It's also an Adafruit seesaw board. Adafruit seesaw is a near-universal converter framework which allows you to add and extend hardware support to any I2C-capable microcontroller or microcomputer. Instead of getting separate I2C GPIO expanders, ADCs, PWM drivers, etc, seesaw can be configured to give a wide range of capabilities.
* Finally, with STEMMA QT connectors on it, you could use it as either an I2C controller or peripheral with plug-and play support.

We primarily designed this board for our own use: it's a mini dev board that lets us design with the ATtiny816 just like we did for the ATSAMD09. With the 2021-2022 silicon shortage, we're adapting some of our SAMD09 designs to the ATTiny8xx series and wanted a quick minimal board to test code on.

Each breakout comes with the assembled and tested board, as well as some header strips. Each PCB is fairly minimal and contains:

The ATtiny816 and ATtiny1616 are identical in specifications except for storage space: 
* The ATtiny816 has 8KB flash, 512 bytes of RAM, 128 bytes of EEPROM
* The ATtiny1616 has 16KB flash, 2KB of RAM, 256 bytes of EEPROM

* Internal oscillator can run up to 20MHz
* Internal hardware multiplier
* Can run from 2V to 5V power/logic (check the datasheet for max speed at desired power)
* 3.3V regulator - by default we run at the Vin voltage, which can be 5V, but there's a solder jumper on the bottom if you'd like to select 3V logic.
* Green power LED
* Red indicator LED
* Two STEMMA QT I2C connectors with 10K pullup resistors, connected to pins 8 and 9

These boards comes pre-programmed with seesaw peripheral code that will let it act as an "I2C to something" converter, basically a little I2C-controlled friend to do all the timing-sensitive things many microcontrollers and microcomputers are not good at.

For example, using these breakouts with the pre-burned seesaw firmware gives you

* 12 x GPIO with selectable pullup resistors: 0-5, 6, 8, 11, 14, 15, 16
* 9 x 10-bit ADC inputs - pins 0, 1, 2, 3, 4, 5, 14, 15, 16
* 5 x 8-bit PWM outputs - pins 0, 1, 7, 11, 16
* 1 x NeoPixel output (up to 60 pixels)
* 1 x EEPROM with 127 byte of NVM memory (handy for storing small access tokens or MAC addresses) - last byte of EEPROM is used for I2C address selection
* 1 x Interrupt output that can be triggered by any of the accessories - pin 6
* 2 x I2C address selection pins - pins 12 and 13
* 1 x Activity LED on pin 10, tied active low

Of course, you can configure or reprogram the chip to however you want to use it - we like using SpenceKonde's megaTinyCore which brings Arduino peripheral support to this series of chips. To program the chip you will need a 'UPDI' programmer, which you can make with a USB-to-Serial cable and a single 4.7K or 10K resistor.

Please note: The boards do not come with a bootloader. If you want to do development on seesaw (e.g. changing the configuration) you need a separate UPDI programming setup! The firmware we put on is available as this example sketch, compiled using the megaTinyCore. We don't provide any support for custom builds of seesaw - we think this is cool and useful for the Maker community!

For more details including the documentation on how to use seesaw, libraries for Arduino/CircuitPython/Raspberry Pi Python, schematics, and more check out the Adafruit seesaw guide

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution. 
See license.txt for additional details.
