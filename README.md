# toldo-automatico-y-anti-ciclonico

#include <Servo.h>

Servo servo;  //nombre de servo
Servo servo1;   //nombre de servo
Servo servo2;
Servo servo3;

const int pinpot = 0; //entrada analogica
const int pulsomin = 650;
const int pulsomax = 2550;
int valor;
int angulo;
int val;
int ang;

void setup() {
  servo.attach(9);   //pin digital cortina
  servo1.attach(8);   //pin digital cortina
  servo2.attach(7);  //inclinacion
  servo3.attach(6); //lona :v ?

}
void loop() {
  valor = analogRead (0);   //entrada del potenciometro cortina
  angulo = map ( valor,0,1023,0,80); // valores del potenciometro a leer
  servo1.write(angulo);    //valores para el servo
  delay(5);
  servo.write(angulo);    //valores para el servo
  valor = analogRead (0);   //entrada del potenciometro cortina
  angulo = map ( valor,0,1023,80,0); // valores del potenciometro a leer
  servo.write(angulo);    //valores para el servo
  delay(5);
  valor = analogRead (0);
  angulo= map ( valor, 0,1023,0,170);
  servo3.write(angulo);
  delay(5);
  
  val = analogRead (1);
  ang = map (val,0,1023,0,100);
  servo2.write (ang);
  delay (5);
  
}
