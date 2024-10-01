## 4. Perform Experiment to use NodeMCU ESP8266 as HTTP Server using WiFi Access Point (AP) mode .

The main difference between NodeMCU station mode and Wi-Fi access point mode is that in station mode, the NodeMCU joins an existing network, while in access point mode, it creates its own network

```ino
#include <ESP8266WiFi.h>

WiFiClient client;
WiFiServer server(80);

#define led D5

void setup()
{
  Serial.begin(9600);
  WiFi.softAP("joy", "123456789");
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
client.println("<a href=\"/on\"\"><button>LED 1 ON</button></a>");
client.println("<a href=\"/off\"\"><button>LED 1 OFF</button></a><br/>");
client.println("</body>");
client.println("</html>");
}

```
