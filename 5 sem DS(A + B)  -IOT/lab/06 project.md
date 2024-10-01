## 6. Interact with DHT11 sensor with NodeMCU and compose a program to print temperature and humidity readings on screen Serial Monitor.

```ino
#include "DHT.h"
#define DHTPIN 2 // what digital pin we're connected to
#define DHTTYPE DHT11 // DHT 11

DHT dht(DHTPIN, DHTTYPE);

void setup()
{
  Serial.begin(9600);
  Serial.println("Room Temperature and Humidity");
  dht.begin();
}

void loop()
{
  delay(2000);
  float h = dht.readHumidity();
  float t = dht.readTemperature(); // Read temperature as Celsius (the default)
  float f = dht.readTemperature(true); // Read temperature as Fahrenheit (isFahrenheit = true)

  // Check if any reads failed and exit early (to try again).
  if (isnan(h) || isnan(t) || isnan(f))
  {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  Serial.print("Humidity: ");
  Serial.print(h);
  Serial.println(" %");
  Serial.print("Temperature: ");
  Serial.print(t);
  Serial.print(" *C ");
  Serial.print(f);
  Serial.println(" *F");
}
```
