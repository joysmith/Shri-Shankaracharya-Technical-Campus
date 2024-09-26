## 2. Acquaintance with NodeMCU and perform essential programming establishment

### Setting up ESP32 in the Arduino IDE on Windows

- download arduino ide [click me](https://www.arduino.cc/en/software)

<br>

#### Here are the steps

1. Open arduino, go to file--> preference--> additional board manager URL:_paste json link here_

```sh
https://espressif.github.io/arduino-esp32/package_esp32_index.json,

https://arduino.esp8266.com/stable/package_esp8266com_index.json
```

2. Open arduino, go to tools--> board--> board manger--> search:esp8266 by esp8266 community--> install

3. Open arduino, go to tools--> boards--> NodeMCU 1.0

4. Open arduino, go to file--> example--> _Check them out_

<br>

#### Install the drivers CP21012 USB chip<a id="13"></a>

- USB-TO-UART BRIDGE CHIPS [click me](http://esp32.net/usb-uart/)
- Download and Install VCP Drivers for window[click me](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)
- restart system
- Open arduino, go to tools--> Port"..."--> USBtoUART
