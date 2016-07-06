# OnlyKey-Firmware

This is the official firmware for **OnlyKey** - The Two-factor Authentication & Password Solution. For general information on OnlyKey check out the Kickstarter page: [OnlyKey Kickstarter Page](http://www.crp.to/ok)

OnlyKey pre-orders are available here: [OnlyKey Pre-order](http://www.crp.to/po)
 
## Introduction ##
There are two available version of the OnlyKey firmware: 

**OnlyKey Firmware US** is the U.S. version of the OnlyKey firmware that comes pre-installed on the OnlyKey (U.S. Customers). 

**OnlyKey Firmware IN** is the International version of the OnlyKey firmware that comes pre-installed on the OnlyKey (International Customers). 

For more information on the difference between the two versions see the [OnlyKey FAQ App](https://github.com/onlykey/OnlyKey-Firmware/wiki/FAQs).

In order to configure an OnlyKey that already has firmware loaded install the [OnlyKey Chrome App](https://github.com/onlykey/OnlyKey-Chrome-App).

## Installation ##
In order to install the latest version of the OnlyKey firmware:  
- Download the zip [here](https://github.com/onlykey/OnlyKey-Firmware-US/archive/master.zip) and save it to a convenient location on your PC.
- For Teensy users you will use the OnlyKey_Standalone_test.cpp.hex firmware included in the zip file.
- For those lucky enough to have an OnlyKey (you know who you are) you will use the OnlyKey_Alpha.ino.cpp.hex firmware included in the zip file.
- Ensure that your copy of the firmware has not been tampered with by checking to see if the SHA256 hash of the downloaded file matches these:
- OnlyKey_Alpha.cpp.hex - 66346a68eda30b398c5860687c2abdd040f7340cb44abc05d242c4f7a608acef
- OnlyKey_Standalone_test.cpp.hex - 0dfb334df3caa18103727b84b377e5f41d3eeee69d69034ac342c94ec33aa4ff
- (To do this in Windows open a command prompt and type certUtil -hashfile pathToFileToCheck SHA256)
- Load the firmware that you downloaded (OnlyKey_XXXXXXX.hex) using the instructional video here [![Load Firmware using Teensy Loader](http://img.youtube.com/vi/qJUjz0gFhqg/0.jpg)](http://www.youtube.com/watch?v=qJUjz0gFhqg)

## Development ##
OnlyKey is currently in development **WARNING** The OnlyKey firmware alpha is available for testing purposes only and is not to be used to store any sensitive information. The following items are in progress:
- U2F Certificate set/wipe - Receive U2F cerificate from chrome app and store to flash/ erase from flash (untested)
- Yubikey Priv ID, Pub ID, Key set/wipe - Receive Yubikey values from chrome app and store to flash/ erase from flash (untested)
- Plausible Deniability Mode - This feature is partially tested. Additional testing is needed here.
- Self Destruct - This feature is partially tested. Currently it overwrites EEPROM with 0s when self destruct PIN is entered. TODO also overwrite flash variables.
- U2F key generation
- U2F - Investigate using deterministic signing - https://github.com/kmackay/micro-ecc/issues/37
- Factory Default to wipe flash sectors used as well as EEPROM
- U2F - Remove placeholder handlekey, generate from nonce.
- U2F - Key wrapping (using RNG, hmac) follow Yubikey architecture - https://www.yubico.com/2014/11/yubicos-u2f-key-wrapping/
- Ensure all license files are properly posted
- Breaking okcore to multiple appropriately named libraries
- General code cleanup
- Remove debugging
- Consider using different SHA256 library. Currently using library from Brad Conte, considering using  Southern Storm Software

## Testing ##
The current publicly available test case document is [here] (https://docs.google.com/spreadsheets/d/1SEByiDpYqyAhNw-Xv2Eix7-MW8PP0Hj5bA2UC55slaI/edit)

To suggest additional test cases or to report your findings email k@crp.to

## Support ##

Check out the [OnlyKey Support Forum](https://groups.google.com/forum/#!forum/onlykey).

Check out the [OnlyKey Firmware FAQs](https://github.com/onlykey/OnlyKey-Firmware-US/wiki/FAQs)

## Libraries ##

Check out the [OnlyKey Libraries Here](https://github.com/onlykey/libraries).

A special thanks to those who made this project possible:

PJRC - https://www.pjrc.com/teensy/td_libs.html

Arduino - http://playground.arduino.cc/Main/LibraryList

Yubico - https://github.com/Yubico/

pagong/arduino-yksim - https://github.com/pagong/arduino-yksim 

lucadentella/ArduinoLib_TOTP - https://github.com/lucadentella/ArduinoLib_TOTP

damico/ARDUINO-OATH-TOKEN - https://github.com/damico/ARDUINO-OATH-TOKEN

Cathedrow/Cryptosuite - https://github.com/Cathedrow/Cryptosuite 

Frank Boesing - https://github.com/FrankBoesing/Arduino-Teensy3-Flash 

Yohanes - https://github.com/yohanes/teensy-u2f 

Ken MacKay - https://github.com/kmackay/micro-ecc

Rhys Weatherley - https://github.com/rweather/arduinolibs

