#include <DHT.h>
// DHT11 Settings
#define DHTPIN A3
#define DHTTYPE DHT11
DHT dht(DHTPIN, DHTTYPE);
// Soil Moisture Settings
const int sensorPin = A0;  // Soil moisture sensor pin
const int ledPin = 7;      // LED pin
// Variables
int h;
int t;
int sensorValue = 0;
void setup()
{
    Serial.begin(9600);
    Serial.println("Temperature, Humidity and Soil Moisture Test");
    dht.begin();
    pinMode(ledPin, OUTPUT);
}
void loop()
{
    // Read DHT11
    h = dht.readHumidity();
    t = dht.readTemperature();
    // Read Soil Moisture
    sensorValue = analogRead(sensorPin);
    // Print all values to Serial Monitor
    Serial.print("Temp: ");
    Serial.print(t);
    Serial.print(" C  |  Humidity: ");
    Serial.print(h);
    Serial.print(" %  |  Soil Moisture: ");
    Serial.println(sensorValue);
    // Control LED based on soil moisture
    if (sensorValue > 500) {
        digitalWrite(ledPin, HIGH);  // Soil is dry, turn LED on
        Serial.println("Status: Soil is DRY");
    } else {
        digitalWrite(ledPin, LOW);   // Soil is wet, turn LED off
        Serial.println("Status: Soil is WET");
    }
    delay(1000);
}
