# ESP8266 I2C Master-Slave

This is an example of I2C master-slave communication with upcoming Arduino 2.5.0 firmware.

It should work against recent Arduino/ESP8266 core from GitHub master, however with core 2.4.2 it does nothing (master works, slave will not receive anything and stay silent).

The example sends "MESA" message from the master to slave, which then responds with a "PONG" message.

Protocol also contains additional CRC16 check for safe transfers and request to retransfer, in case the check fails.

## Installation

In case you're having issues with getting the right version of Arduino Core, just place files from the `esp8266-patch` folder to your Arduino IDE packages folder (e.g. `~/Library/Arduino15/packages/esp8266/2.4.2`).

Replace files in the `core` folder: `core_esp8266_si2c.c`, `twi_util.h` and `twi.h`.
Replace files in the `libraries/Wire` with `Wire.cpp`

## Running

Take two ESP8266 boards, connect pins D1-D1, D2-D2 and GND-GND.

Load one with Master (you can just close the console and let it run...) and the other with Slave code (you'll see in the slave console, once it starts working).
