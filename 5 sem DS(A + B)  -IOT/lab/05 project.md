## 5. Perform Experiment for Controlling LED through an HTTP page Using NodeMCU Station Mode (STA)

The main difference between NodeMCU station mode and Wi-Fi access point mode is that in station mode, the NodeMCU joins an existing network, while in access point mode, it creates its own network:

#### Version 1: Station mode: Boiler plate, How to connect nodemcu to any wifi network

```ino
#include <ESP8266WiFi.h>

void setup() {
  Serial.begin(9600);
  WiFi.begin("AIML", "@123@123");
  while(WiFi.status() != WL_CONNECTED)
  {
    Serial.print("..");
    delay(200);
  }
  Serial.println();
  Serial.println("NodeMCU is Connected!");

  // print ip address of local wifi
  Serial.println(WiFi.localIP());

}

void loop() {
  // put your main code here, to run repeatedly:

}
```

<br>

#### Version 2: Make get request by typing in url bar

```ino
#include <ESP8266WiFi.h>

WiFiClient client;
WiFiServer server(80);

#define led D5

void setup()
{
  // put your setup code here, to run once:
  Serial.begin(9600);
  WiFi.begin("AIML", "@123@123");
  while(WiFi.status() != WL_CONNECTED)
  {
    delay(200);
    Serial.print("..");
  }
  Serial.println();
  Serial.println("NodeMCU is connected!");
  Serial.println(WiFi.localIP());
  server.begin();
  pinMode(led, OUTPUT);
}

void loop()
{
  // put your main code here, to run repeatedly:
  client = server.available();  //Gets a client that is connected to the server and has data available for reading.
  if (client == 1)
  {
    String request =  client.readStringUntil('\n');
    Serial.println(request);
    request.trim();
    if(request == "GET /ledon HTTP/1.1")
    {
      digitalWrite(led, HIGH);
    }
    if(request == "GET /ledoff HTTP/1.1")
    {
      digitalWrite(led, LOW);
    }
  }
}

```

1. Get the ip address from serial monitor, paste it on browser
2. After ip address type /on or /off to switch on/off LED

```sh
To make led turn on
198.164.4.1/on

To make led turn off
198.164.4.1/off
```

<br>

#### Version 3: Turn LED ON or OFF using web page

```ino
#include <ESP8266WiFi.h>

WiFiClient client;
WiFiServer server(80);

#define led D5

void setup()
{
  Serial.begin(9600);
  WiFi.softAP("AIML", "@123@123");
  Serial.println("NodeMCU Started!");
  Serial.println(WiFi.softAPIP());
  server.begin();
  pinMode(led, OUTPUT);
}

void loop()
{
  // put your main code here, to run repeatedly:
  client = server.available(); //Gets a client that is connected to the server and has data for reading.
  if (client == 1)
  {
    String request = client.readStringUntil('\n');
    Serial.println(request);
    request.trim();

  if(request == "GET /on HTTP/1.1")
  {
    digitalWrite(led, HIGH);
  }

  if(request == "GET /off HTTP/1.1")
  {
    digitalWrite(led, LOW);
  }
}

client.println("<html>");
client.println("<body>");
client.println("<h1>Welcome to the Webpage!</h1>");
client.println("<h3>LED Controls<h3>");
client.println("<br>");
client.println("<a href=\"/on\"\"><button>LED 1 OFF</button></a>");
client.println("<a href=\"/off\"\"><button>LED 1 ON</button></a><br/>");
client.println("</body>");
client.println("</html>");
}

```
