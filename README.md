# eincleverhelm
This is a project by @bob4o-afk and it is connected with future projects.
If you have problems connact me or go here: https://github.com/TMRh20/TMRpcm

## DESCRIPTION
GitHub Repository Description:

This GitHub repository contains code for recording audio using an Arduino UNO and a KY-038 microphone module. The code enables users to record audio and save it as a WAV file on an SD card.

## Needed parts
* [Arduino UNO](https://store.arduino.cc/products/arduino-uno-rev3)
* [Adafruit Data Logger Shield](https://learn.adafruit.com/adafruit-data-logger-shield)
* [KY-038 sound sensor](https://sensorkit.joy-it.net/de/sensors/ky-038)
* Jumpers
* 5V power supply
  
## Hardware Connection:
You put the shield onto the Arduino Uno like this:
![Arduino Shield](https://cdn-learn.adafruit.com/assets/assets/000/058/608/original/adafruit_products_1141-05.jpg?1533313257)

After that you connect the sound sensor as following:
```
S   -> Analog0
+   -> 5V
-   -> GND
```

## Setup Instructions:
* Connect the Arduino Nano to the SD card module and the MAX9814 microphone module according to the hardware pinout mentioned above.
* Install the required libraries: [TMRpcm](https://www.arduino.cc/reference/en/libraries/tmrpcm/), [SD](https://github.com/arduino-libraries/SD), [SPI](https://github.com/PaulStoffregen/SPI), and [EEPROM](https://github.com/PaulStoffregen/EEPROM).
* Modify the TMRpcm library configuration file "pcmConfig.h" as follows:
  - Uncomment the line "#define buffSize 128" if using Uno or non-mega boards.
  - Uncomment the lines "#define ENABLE_RECORDING" and "#define BLOCK_COUNT 10000UL".
* Upload the code to the Arduino Nano.
* Open the Serial Monitor at a baud rate of 9600 to monitor the process.
* Ensure that an SD card is inserted into the SD card module.
* The code will automatically start recording audio for 15 seconds and save it as a WAV file on the SD card.
* Each recorded file will be named with a prefix ("record") followed by a number and the extension ".wav".
* The file number is stored in the EEPROM memory of the Arduino Nano, so the numbering continues from the last recorded file on subsequent runs.
  
**! Note: If you want to adjust the duration of the recording, you can modify the ```wait_secs``` function in the code.  !** 

## Example wiring diagram
![Diagram](https://europe1.discourse-cdn.com/arduino/original/4X/0/d/d/0ddf9122cba54816ca61dab4547d06b6fd0f8803.png)

For more information on the TMRpcm library and its functionalities, refer to the official [documentation](https://www.arduino.cc/reference/en/libraries/tmrpcm/).
