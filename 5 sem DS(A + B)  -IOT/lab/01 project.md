## 1. Introduction to various sensors and actuators.

a) PIR Motion Sensor.
b) Rain Drop Sensor.
c) Moisture Sensor.
d) Temperature Sensor.
e) Touch Sensor.
f) Infrared Sensor.
g) RFID Sensor.
h) Ultrasonic Sensor.
i) Bluetooth Module.
j) Wi-Fi Module.
k) LED/OLED
l) Servo Motor.

- Download Arduino IDE [Click me](https://www.arduino.cc/en/software)

#### How to Select sketch and upload

- From menu select file--> example--> digital--> BlinkwithoutDelay

### 55. The Arduino IDE - Understanding the Preferences pane<a id="55"></a>

<img src="assets/images/1.png" width="700">

### 57. How to upload a sketch to your Arduino<a id="57"></a>

- go to menu Files--> Example--> basic--> blink
- go to menu Tools--> Boards--> arduino avr board--> arduino uno
- go to menu Tools--> Port--> COM(arduino)
- click on ✅ to compile, then ➡️ to upload sketch on uno

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
