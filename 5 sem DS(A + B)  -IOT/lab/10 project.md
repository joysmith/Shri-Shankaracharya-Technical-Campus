## 10. Compose a program on NodeMCU to transfer temperature and stickiness information to thingspeak,Blynk or any other free cloud

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
