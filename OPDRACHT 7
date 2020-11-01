#include <Servo.h>
#define ALARM 10


//defineren van poorten
const int TrigPin = 12;
const int EchoPin = 8;
int distance;
int length;
int pin = 11;
Servo myservo;

//functie bieden aan de pins voor de ultrasone
void setup()

{
  Serial.begin(9600);
  pinMode(TrigPin, OUTPUT);
  pinMode(EchoPin, INPUT);
  myservo.attach(pin);
}

//Loop door de pinnen heen voor de ultrasone functie


void loop()
{
  pinMode(TrigPin, OUTPUT);
  digitalWrite(TrigPin, LOW);
  delayMicroseconds(10);
  digitalWrite(TrigPin, HIGH);
  delayMicroseconds(20);
  digitalWrite(TrigPin, LOW);
  
  pinMode(EchoPin, INPUT);
  length = pulseIn(EchoPin, HIGH);
  distance = (length/2)/29;
  //ultrasone afstand bepalen in centimeter
  Serial.print(distance);
  Serial.println("cm");


//functie geven aan de ultrasone  
  if(distance <= ALARM)
  {
    myservo.write(60); //servo draaiafstand geven
    delay(50);
  }
  else
  {
    myservo.write(0);
    delay(50);
  }
    
  delay(300);
}
