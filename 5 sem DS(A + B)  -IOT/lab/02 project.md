## 2. Acquaintance with NodeMCU and perform essential programming establishment

### Setting up ESP32 in the Arduino IDE on Windows

- download arduino ide [click me](https://www.arduino.cc/en/software)
- github -Arduino core for the ESP32, ESP32-S2, ESP32-S3, ESP32-C3, ESP32-C6 and ESP32-H2 [click me](https://github.com/espressif/arduino-esp32)
- Embedded Software Development [click me](https://platformio.org/)

- Installing using Arduino IDE [click me](https://docs.espressif.com/projects/arduino-esp32/en/latest/installing.html#installing-using-arduino-ide)

#### Here are the steps

1. Open arduino, go to file--> preference--> additional board manager URL:_paste json link here_

```sh
https://espressif.github.io/arduino-esp32/package_esp32_index.json
```

2. Open arduino, go to tools--> board--> board manger--> search:esp32 by espressifsystem--> install

3. Open arduino, go to tools--> boards--> ESP32 dev module

4. Open arduino, go to file--> example--> _Check them out_

#### Install the drivers CP21012 USB chip<a id="13"></a>

- USB-TO-UART BRIDGE CHIPS [click me](http://esp32.net/usb-uart/)
- Download and Install VCP Drivers for window[click me](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)
- restart system
- Open arduino, go to tools--> Port"..."--> USBtoUART
