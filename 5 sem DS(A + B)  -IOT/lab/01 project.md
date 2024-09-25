## 1. Introduction to various sensors and actuators.

a) PIR Motion Sensor. <br>
b) Rain Drop Sensor. <br>
c) Moisture Sensor. <br>
d) Temperature Sensor. <br>
e) Touch Sensor. <br>
f) Infrared Sensor. <br>
g) RFID Sensor. <br>
h) Ultrasonic Sensor. <br>
i) Bluetooth Module. <br>
j) Wi-Fi Module. <br>
k) LED/OLED. <br>
l) Servo Motor. <br>

<br>
<br>

### 50. Introduction to this section<a id="50"></a>

### 51. Arduino IDE 1.8<a id="51"></a>

### 52. Arduino IDE 2.0<a id="52"></a>

- Download Arduino IDE [Click me](https://www.arduino.cc/en/software)

#### How to Select sketch and upload

- From menu select file--> example--> digital--> BlinkwithoutDelay

### 53. An introduction to the Arduino IDE<a id="53"></a>

### 54. Getting and installing the Arduino IDE<a id="54"></a>

### 55. The Arduino IDE - Understanding the Preferences pane<a id="55"></a>

<img src="assets/images/1.png" width="700">

### 56. The Arduino IDE - Understanding the Menu items<a id="56"></a>

#### How to upload sketch using external programmer

- go to menu sketch--> Upload using programmer

#### How to get compiled binary file of sketch

- go to menu sketch--> Export compiled binary

#### How to burn bootloader in Atmega16 any new chip

- go to menu tools--> burn bootloader

### 57. How to upload a sketch to your Arduino<a id="57"></a>

- go to menu Files--> Example--> basic--> blink
- go to menu Tools--> Boards--> arduino avr board--> arduino uno
- go to menu Tools--> Port--> COM(arduino)
- click on ✅ to compile, then ➡️ to upload sketch on uno

### 58. How to upload a sketch to your Arduino - For Windows users<a id="58"></a>

#### How to use serial monitor

<img src="assets/images/3.png" width="700">

- go to menu Files--> Example--> basic--> blink
- go to menu Tools--> Boards--> arduino avr board--> arduino uno
- go to menu Tools--> Port--> COM(arduino)

```ino

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
  Serial.begin(9600);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);  // turn the LED on (HIGH is the voltage level)
  delay(1000);                      // wait for a second
  Serial.println("ON");

  digitalWrite(LED_BUILTIN, LOW);  // turn the LED off by making the voltage LOW
  delay(1000);                     // wait for a second
  Serial.println("OFF");
}

```

- click on ✅ to compile, then ➡️ to upload sketch on uno
- go to menu Tools--> Serial Monitor

---

#### How to use Serial Plotter

<img src="assets/images/1.png" width="700">

- go to menu Files--> Example--> basic--> blink
- go to menu Tools--> Boards--> arduino avr board--> arduino uno
- go to menu Tools--> Port--> COM(arduino)

```ino

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
  Serial.begin(9600);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);  // turn the LED on (HIGH is the voltage level)
  delay(1000);                      // wait for a second
  Serial.println(10);

  digitalWrite(LED_BUILTIN, LOW);  // turn the LED off by making the voltage LOW
  delay(1000);                     // wait for a second
  Serial.println(0);
}

```

- click on ✅ to compile, then ➡️ to upload sketch on uno
- go to menu Tools--> Serial Plotter

---

#### Documentation

- Serial communication documentation [Click me](https://www.arduino.cc/reference/en/language/functions/communication/serial/read/)
- The arduino board send data to my computer/laptop
