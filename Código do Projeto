#include <Ultrasonic.h> //Biblioteca para sensor

int buttonPin = 6; 
int buttonState;
bool running = false;
float luminosidadeLED = 0;
float buzzer=0;
long distancia;
int devices [4]={2,3,5,1};
int pin_sensor [2]={12,13};
Ultrasonic ultrasonic1(pin_sensor[1],pin_sensor[0]);
float Read(Ultrasonic ultrasonic){
long distancia = ultrasonic.Ranging(CM);


  
}
void setup() {
  pinMode(buttonPin, INPUT);
for(int i=0;i<5;i++)
{pinMode(devices[i],OUTPUT);} 
pinMode(devices[3], INPUT);
Serial.begin(9600);
Serial.println("Aguardando Analise...");

}

void loop() {
if (digitalRead(buttonPin)){
    buttonState = !buttonState;
    delay (1000);
    Serial.println("Sistema Acionado...");
    
  }
  if (buttonState == LOW)
 {
  return;
  digitalWrite(buttonPin, LOW);
 Serial.println(" Varredura Completa, Sistema Desligado...");
 }
 
if(Read(ultrasonic1)<10 ){

digitalWrite(devices[1],1);
delay(20); 
tone(devices[5],261);    
delay(20);
noTone(devices[5]);
digitalWrite(devices[1],0);
delay(20);
digitalWrite(devices[0],1);
delay(20); 
digitalWrite(devices[0],0);

luminosidadeLED = map(analogRead(devices[3]), 0, 1023, 0, 255);
analogWrite(devices[2], luminosidadeLED);
buzzer=map(analogRead(devices[5]), 0, 1023, 0, 255);
analogWrite(devices[2], buzzer);

  Serial.print(" Analisando Sensor: ");
  Serial.println(Read(ultrasonic1));
  Serial.println("cm");
  delay(100);
  
}

}
