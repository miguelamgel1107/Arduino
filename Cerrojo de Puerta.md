                                                        
# Proyecto

Hoy he realizado, junto a [Miguel Ángel](https://github.com/miguelamgel1107) y [David](https://github.com/DavidMenCam), el proyecto de Arduino Cerrojo de Puerta.

## Resumen

Este proyecto consiste en crear un cerrojo de puerta para proteger y mantener fuera de tu espacio a personas non gratas.

Esto se basa en un cerrojo, el cual tendrá una "llave", que consistirá en dar unos golpes para así abrir el mismo. Depende de cada uno, cada cerrojo tendrá una "llave" diferente, es decir, requerirá de diferentes números de golpes para abrirse. En mi caso son 3, pero puedes poner que requiera más o menos golpes, como he dicho, eso va al gusto de cada uno.

¿Y cómo se cambia? Muy fácil. 

Busca la línea de código 39 o if(numberOfKnocks < 3 && knockVal > 0){ y cambias el valor 3 por el de tu gusto.

Después busca la línea 43 o Serial.print(3-numberOfKnocks); y como en el ejemplo anterior cambias el 3 por el número que hayas puesto en el código de la línea 39, aunque no es estrictamente necesario, ya que está línea solo sirve para el Monitor serial, así que no importa si no se cambia ya que se requerirán los golpes que tu hayas puesto en la línea de código que he mencionado antes, pero ayuda a que no hayan líos.

Y por último ve a la línea 46 o if(numberOfKnocks >= 3){ y cambia el valor 3 por el que tu hayas escogido en la línea de código número 39. 

Y ya tendrías tu cerrojo con "llave" personalizada.

Para este proyecto se necesita: Cables, Interruptor, Leds, Resistencia de 10 KiloOhmios, Resistencias de 220 Ohmios, Resistencia de 1 MegOhmio, Un condensador de 100 uF, un servomotor y por último un piezo.


## Código

Aquí está el código del proyecto: 

```C++
#include <Servo.h>
Servo myServo;
const int piezo = A0;
const int switchPin = 2;
const int yellowLed = 3;
const int greenLed = 4;
const int redLed = 5;
int knockVal;
int switchVal;
const int quietKnock = 20;
const int loudKnock = 100;
boolean locked = false;
int numberOfKnocks = 0;
void setup(){
  myServo.attach(9);
  pinMode(yellowLed,OUTPUT);
  pinMode(redLed,OUTPUT);
  pinMode(greenLed,OUTPUT);
  pinMode(switchPin,INPUT);
  Serial.begin(9600);
  digitalWrite(greenLed,HIGH);
  myServo.write(0);
  Serial.println("La caja está abierta");
}
void loop(){
  if(locked == false){
    switchVal = digitalRead(switchPin);
    if(switchVal == HIGH){
      locked = true;
      digitalWrite(greenLed,LOW);
      digitalWrite(redLed,HIGH);
      myServo.write(90);
      Serial.println("La caja está cerrada");
      delay (1000);
    }
  }
  if(locked == true){
    knockVal = analogRead(piezo);
    if(numberOfKnocks < 3 && knockVal > 0){
      if(checkForKnock(knockVal) == true){
        numberOfKnocks++;
      }
      Serial.print(3-numberOfKnocks);
      Serial.println("Moras golpes para ir");
    }
    if(numberOfKnocks >= 3){
      locked = false;
      myServo.write(0);
      delay(20);
      digitalWrite(greenLed,HIGH);
      digitalWrite(redLed,LOW);
      Serial.println("La caja está abierta");
      numberOfKnocks =0;
    }
  }
}
boolean checkForKnock(int value){
  if(value > quietKnock && value < loudKnock){
    digitalWrite(yellowLed,HIGH);
    delay(50);
    digitalWrite(yellowLed,LOW);
    Serial.print("Valor de golpe válido");
    Serial.println(value);
    return true;
  }
  else {
    Serial.print("Valor de golpe no válido");
    Serial.println(value);
    return false;  
  }
}   

```
P.D: En mi caso yo he cambiado el const int quietKnock a 20 ya que me venía mejor, pero de normal es 10.
Y el código en el libro tiene un bug, falta el numberofKnocks =0; después de Serial.println("La caja está abierta"); , entre las líneas 52 y 53 del código.


## Imágenes o Vídeos

Y por último aquí tenéis la imagen y el vídeo del mismo:

![](https://github.com/Tabrih/Arduino/blob/main/Archivos/IMG_20220126_115326.jpg)

[Vídeo del proyecto](https://raw.githubusercontent.com/Tabrih/Arduino/main/Archivos/VID_20220126_115954.mp4)
