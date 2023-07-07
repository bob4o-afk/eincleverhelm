# eincleverhelm
This is a project by @bob4o-afk and it is connected with future projects.
If you have problems connact me or go here: https://github.com/TMRh20/TMRpcm

## DESCRIPTION
GitHub Repository Description:

This GitHub repository contains code for recording audio using an Arduino Nano and a MAX9814 microphone module. The code enables users to record audio and save it as a WAV file on an SD card.

## Hardware Connection:

Arduino Nano is connected to the SD card module with the following pinout:
```
5V --> VCC
GND --> GND
D10 --> CS
D11 --> MOSI
D12 --> MISO
D13 --> SCK
```

Arduino Nano is connected to the MAX9814 microphone module with the following pinout:
```
3.3V --> VDD
GND --> GND
A0 --> Out
```
Arduino Nano pin D2 is used to connect an LED, which notifies the user that the recording is in process.

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
![Diagram](https://forum.arduino.cc/t/solved-problem-with-reading-out-adafruit-max9814/626118)

For more information on the TMRpcm library and its functionalities, refer to the official [documentation](https://www.arduino.cc/reference/en/libraries/tmrpcm/).
