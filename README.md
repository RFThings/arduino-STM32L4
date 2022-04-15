# Arduino Core for STM32L4 based boards

## Supported boards

### [RFThings](https://rfthings.com.vn/)
 * [RFThings-DKPlatinum](https://rfthings.com.vn/product/dk/)
     * <b>MCU</b>: 1MB Flash
     * <b>GPS</b>: Ublox CAM-M8Q
 * [RFThings-DKBlue](https://rfthings.com.vn/product/dk/)
     * <b>MCU</b>: 256kB Flash
     * <b>GPS</b>: Quectel L96
 * [RFThings-DKAIoT]()
     * <b>MCU</b>: 1MB Flash
     * <b>GPS</b>: Ublox CAM-M8Q
     * <b>MicroSD</b>
     * <b>Sensors</b>: ICM-20948, SGP30-2.5K, SPH0690LM4H-1
     * <b>Optional sensors</b>: BME280, LSM303, ATECC608, HP203B, LTR-303, KXTJ3, KX023
 * [Generic STM32L496RG]()
     * <b>MCU</b>: STM32L496RG (1MB Flash)

## Installing

### Board Manager

 1. [Download and install the Arduino IDE](https://www.arduino.cc/en/Main/Software) (at least version v1.8.13)
 2. Start the Arduino IDE
 3. Go to Preferences
 4. Copy & Add the following JSON URL to your "Additional Board Manager URL"
```
https://rfthings.github.io/ArduinoBoardManagerJSON/package_rfthings-stm32l4_index.json
``` 
 5. Open the Boards Manager from the Tools -> Board menu and install "STM32L4 Boards (RFThings) by RFThings"
 6. Select your STM32L4 board from the Tools -> Board menu

#### OS Specific Setup

##### Linux

 1. Go to ~/.arduino15/packages/rfthings-stm32l4/hardware/stm32l4/```<VERSION>```/drivers/linux/
 2. sudo cp *.rules /etc/udev/rules.d
 3. reboot

#####  Windows

###### STM32 BOOTLOADER driver setup for Tlera Corp boards

 1. Download [Zadig](http://zadig.akeo.ie)
 2. Plugin STM32L4 board and toggle the RESET button while holding down the BOOT button
 3. Let Windows finish searching for drivers
 4. Start ```Zadig```
 5. Select ```Options -> List All Devices```
 6. Select ```STM32 BOOTLOADER``` from the device dropdown
 7. Select ```WinUSB (v6.1.7600.16385)``` as new driver
 8. Click ```Replace Driver```

###### USB Serial driver setup for Tlera Corp boards (Window XP / Windows 7 only)

 1. Go to ~/AppData/Local/Arduino15/packages/rfthings-stm32l4/hardware/stm32l4/```<VERSION>```/drivers/windows
 2. Right-click on ```dpinst_x86.exe``` (32 bit Windows) or ```dpinst_amd64.exe``` (64 bit Windows) and select ```Run as administrator```
 3. Click on ```Install this driver software anyway``` at the ```Windows Security``` popup as the driver is unsigned

###### ST-LINK V2.1 driver setup for NUCLEO boards

 1. Plugin NUCLEO board
 2. Download and install [ST-Link USB Drivers](http://www.st.com/en/embedded-software/stsw-link009.html)

### From git (for core development)

 1. Follow steps from Board Manager section above
 2. ```cd <SKETCHBOOK>```, where ```<SKETCHBOOK>``` is your Arduino Sketch folder:
  * OS X: ```~/Documents/Arduino```
  * Linux: ```~/Arduino```
  * Windows: ```~/Documents/Arduino```
 3. Create a folder named ```hardware```, if it does not exist, and change directories to it
 4. Clone this repo: ```git clone https://github.com/grumpyoldpizza/arduino-STM32L4.git grumpyoldpizza/stm32l4```
 5. Restart the Arduino IDE

## Recovering from a faulty sketch for Tlera Corp Boards

 Sometimes a faulty sketch can render the normal USB Serial based integration into the Arduindo IDE not working. In this case plugin the STM32L4 board and toggle the RESET button while holding down the BOOT button and program a known to be working sketch to go ack to a working USB Serial setup.

## Credits

This core is based on the [Arduino SAMD Core](https://github.com/arduino/ArduinoCore-samd)

