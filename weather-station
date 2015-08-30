// Simple weather station - Humidity & Temperature using the DHT22 sensor
// and a 16x2 LCD display and an Arduino Uno
// Edited and Updated by superchunks (superchunks.co.uk) - August 2015
// Tony Akens
// 2/14/13
// Wiring for the LCD is as taken from arduino.cc, potentiometer included
// Wiring for DHT sensor is connecting data to pin 8, with a pullup resistor from
// 5v to data wire in addition.
// Details & link to library, and example code adapted from:
// Example testing sketch for various DHT humidity/temperature sensors
// Written by ladyada, public domain
// http://learn.adafruit.com/dht


#include <LiquidCrystal.h>
#include "DHT.h"

#define DHTPIN 2     // what pin we're connected to
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);  //Pins for the LCD display

// Uncomment whatever type you're using!
//#define DHTTYPE DHT11   // DHT 11 
#define DHTTYPE DHT22   // DHT 22  (AM2302)
//#define DHTTYPE DHT21   // DHT 21 (AM2301)

// Connect pin 1 (on the left) of the sensor to +5V
// Connect pin 2 of the sensor to whatever your DHTPIN is
// Connect pin 4 (on the right) of the sensor to GROUND
// Connect a 10K resistor from pin 2 (data) to pin 1 (power) of the sensor

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  //Serial.begin(9600);  
  dht.begin();
  lcd.begin(16, 2);
}

void loop() {
  // Reading temperature or humidity takes about 250 milliseconds!
  // Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  //t = t* 9/5 + 32; (uncomment to read in F)

  // check if returns are valid, if they are NaN (not a number) then something went wrong!
  if (isnan(t) || isnan(h)) {
    lcd.setCursor(0, 0);
    lcd.print(F("looking..."));
    //Serial.println("looking...");
  } else {
   lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("Humidity: ");
    lcd.print(h);
    lcd.print("%");
    lcd.setCursor(0, 1);
    lcd.print("Temp: ");
    lcd.print(t);
    lcd.print("\337C");
    //Serial.print("Humidity: "); 
    //Serial.print(h);
    //Serial.print(" %\t");
    //Serial.print("Temperature: "); 
    //Serial.print(t);
    //Serial.println("*C");

      // Wait 5 seconds between measurements.
  delay(5000); 
  }
}
