## 4. Perform Experiment to use NodeMCU ESP8266 as HTTP Server using WiFi Access Point (AP) mode .

The main difference between NodeMCU station mode and Wi-Fi access point mode is that in station mode, the NodeMCU joins an existing network, while in access point mode, it creates its own network

- Nodemcu is creating its on wifi local area network
- Its working as a hotspot

<br>

#### Version 1:

```ino
#include <ESP8266WiFi.h>

WiFiClient client;
WiFiServer server(80);

#define led D5

void setup()
{
  // put your setup code here, to run once:
  Serial.begin(9600);
  WiFi.softAP("NodeMCU", "123456789");
  Serial.println();
  Serial.println("NodeMCU Started!");

  // generate nodemcu ip
  Serial.println(WiFi.softAPIP());
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

#### Version 2: control LED using web page

```ino
#include <ESP8266WiFi.h>

WiFiClient client;
WiFiServer server(80);

#define led LED_BUILTIN

void setup()
{
  Serial.begin(9600);
  WiFi.softAP("joy", "123456789");
  Serial.println("NodeMCU Started!");

  // generate nodemcu ip
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
