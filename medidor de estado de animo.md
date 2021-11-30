# Medidor de estado de ánimo

## Proyecto

Hoy he realizado el proyecto Medidor de estado de ánimo con [David](https://github.com/DavidMenCam) y [Christian](https://github.com/Tabrih) .

Consiste, gracias a un servomotor, en hacer un calibrador de estado de ánimo según los estados que hemos puesto personalmente ese día.

## Resumen 

Los servomotores  son un tipo especial de motores que no giran alrededor de un círculo continuamente, sino se mueven a una posición específica y permanecen en ella hasta que se les diga que se muevan de nuevo. Los servos solo suelen girar 180 grados (la mitad de un círculo). Combinando uno de estos motores con un pequeño cartón hecho a mano, será capaz de decirle a la gente si deberían venir y preguntar si necesita o no ayuda para su próximo proyecto. De la misma forma que se ha usado PWM y los LEDs en el proyecto anterior, los servomotores necesitan un número de impulsos para saber que ángulo deben de girar. Los impulsos siempre tienen los mismos intervalos (periodo), pero el ancho de estos impulsos puede variar entre 1000 y 2000 micro segundos. Si bien es posible escribir código para generar estos impulsos, el software de Arduino incluye una librería que permite controlar el motor con facilidad.

Ya que el servomotor solo gira 180 grados y la entrada analógica varía de 0 a 1023, es necesario usar una función llamada map() para cambiar la escala de los valores que produce el potenciómetro.

Una de las grandes cosas que tiene la comunidad de Arduino es el talento de la gente quien aumenta su funcionalidad a través de software adicional. De esta forma es posible que cualquiera escriba librerías para aumentar la funcionalidad de Arduino. Existen librerías para una gran variedad de sensores y actuadores y otros dispositivos con la que los usuarios han contribuido en esta comunidad. El software libre extiende la funcionalidad de un entorno de programación. El software de Arduino viene con un número de librerías que son útiles para trabajar con el hardware o lo datos. Una de las librerías incluida esta diseñada para ser usada con servomotores. Cuando se escriba el código será necesario importar esta librería y así se podrá controlar el servomotor.

Sacado del libro de Arduino.

## Código

Este es el código entero de este proyecto


```C++

#include <Servo.h>
Servo myServo;
int const potPin = A0;
int potVal;
int angle ;
void setup() {
  myServo.attach(9);


  Serial.begin(9600);
  }

void loop(){
  potVal = analogRead(potPin);
  Serial.print("potVal: ");
  Serial.print(potVal);
  angle = map(potVal, 0, 1023, 0, 179);
  Serial.print(", angle: ");
  Serial.println(angle);
  myServo.write(angle);
  delay(15);
}
```

