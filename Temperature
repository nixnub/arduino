/* LCD/LED room temperature  */
int ledPin = 13;
#include <LiquidCrystal.h>

int pin = 0; // analog pin
int tempc = 0,tempf=0; // temperature variables
int samples[8]; // variables to make a better precision
int maxi = -100,mini = 100; // to start max/min temperature
int i;


// initialize LCD Library
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);


void setup()
{
pinMode(ledPin, OUTPUT);
lcd.begin(16, 2);
}

void loop()
{
 //initiate LCD

for (i = 0; i <= 7; i++) { // gets 8 samples of temperature
 
  samples[i] = ( 5.0 * analogRead(pin) * 100.0) / 1024.0;
  tempc = tempc + samples[i];
  delay(1000);

}

tempc = tempc/8.0; // better precision
tempf = (tempc * 9)/ 5 + 32; // converts to fahrenheit

if(tempc > maxi) {maxi = tempc;} // set max temperature
if(tempc < mini) {mini = tempc;} // set min temperature
 digitalWrite(13, HIGH);
 delay(100);
 digitalWrite(13,LOW);
 delay(100);
lcd.setCursor(1,0);
lcd.print(tempc,DEC);
lcd.print(" Celsius ");
lcd.setCursor(1,1);
lcd.print(tempf,DEC);
lcd.print(" fahrenheit ");
tempc = 0;

delay(1000); // delay before loop
}
