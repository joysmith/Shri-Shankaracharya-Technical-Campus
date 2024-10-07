## 10. Compose a program on NodeMCU to transfer temperature and stickiness information to thingspeak,Blynk or any other free cloud

- Create thing-speak account [click me](https://thingspeak.mathworks.com/)

<img src="assets/images/10/1.png" width="700">

<img src="assets/images/10/2.png" width="700">

<img src="assets/images/10/3.png" width="700">

<img src="assets/images/10/4.png" width="700">

<img src="assets/images/10/5.png" width="700">

<img src="assets/images/10/6.png" width="700">

<img src="assets/images/10/7.png" width="700">

<img src="assets/images/10/8.png" width="700">

<img src="assets/images/10/9.png" width="700">

<img src="assets/images/10/10.png" width="700">

<img src="assets/images/10/11.png" width="700">

<img src="assets/images/10/12.png" width="700">

<img src="assets/images/10/13.png" width="700">

<img src="assets/images/10/14.png" width="700">

<img src="assets/images/10/15.png" width="700">

<br>

#### How to install library

Open arduino IDE and follow steps

- Go to sketch--> include library--> manage library--> Search: "DHT11" by adafruit --> install all
- Go to sketch--> include library--> manage library--> Search: "Thingspeak" by mathwork --> install

<br>

#### Version 1 college sonu sir code

```ino
#include <DHT.h> // Including library for dht
#include <ESP8266WiFi.h>

String apiKey = "H38TEGNC0XKW43BB"; // Enter your Write API key from ThingSpeak
const char *ssid = "sstc"; // replace with your wifi ssid and wpa2 key
const char *pass = "sstc1234";
const char* server = "api.thingspeak.com";

#define DHTPIN D3 //pin where the dht11 is connected
DHT dht (DHTPIN, DHT11);
WiFiClient client;


void setup()
{
  Serial.begin(115200);
  delay(10);
  dht.begin();
  Serial.println("Connecting to ");
  Serial.println(ssid);
  WiFi.begin(ssid, pass);

  while (WiFi.status() != WL_CONNECTED)
  {
    delay(500);
    Serial.print(".");
  }

  Serial.println("");
  Serial.println("WiFi connected");
}


void loop()
{
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  if (isnan(h) || isnan(t))
  {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

if (client.connect(server,80)) // "184.106.153.149" or api.thingspeak.com
{
  String postStr = apiKey;
  postStr +="&field1=";
  postStr += String(t);
  postStr +="&field2=";
  postStr += String(h);
  postStr += "\r\n\r\n";

  client.print("POST /update HTTP/1.1\n");
  client.print("Host: api.thingspeak.com\n");client.print("Connection: close\n");
  client.print("X-THINGSPEAKAPIKEY: "+apiKey+"\n");
  client.print("Content-Type: application/x-www-form-urlencoded\n");
  client.print("Content-Length: ");
  client.print(postStr.length());
  client.print("\n\n");
  client.print(postStr);
  Serial.print("Temperature: ");
  Serial.print(t);
  Serial.print(" degrees Celcius, Humidity: ");
  Serial.print(h);
  Serial.println("%. Send to Thingspeak.");
}

client.stop();
Serial.println("Waiting...");

// thingspeak needs minimum 15 sec delay between updates
delay(5000);
}
```

<br>

#### Version 2: outside

<img src="assets/images/10/16.png" width="700">

<img src="assets/images/10/17.png" width="700">

```ino
#include <ESP8266WiFi.h>
#include <DHT.h>
#include <ThingSpeak.h>

DHT dht(D5, DHT11);

WiFiClient client;

// 1️⃣ copy channel number from Thingspeak account
long myChannelNumber = 2684307;

// 2️⃣ get the api Write key from thingspeak account
const char myWriteAPIKey[] = "7A7AEXW4357E3YT9";

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  WiFi.begin("iot", "project1234");
  while(WiFi.status() != WL_CONNECTED)
  {
    delay(200);
    Serial.print("..");
  }
  Serial.println();
  Serial.println("NodeMCU is connected!");
  Serial.println(WiFi.localIP());
  dht.begin();
  ThingSpeak.begin(client);
}

void loop() {
  // put your main code here, to run repeatedly:
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  Serial.println("Temperature: " + (String) t);
  Serial.println("Humidity: " + (String) h);
  ThingSpeak.writeField(myChannelNumber, 1, t, myWriteAPIKey);
  ThingSpeak.writeField(myChannelNumber, 2, h, myWriteAPIKey);
  delay(2000);
}
```
