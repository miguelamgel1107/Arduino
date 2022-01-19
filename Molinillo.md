
                                                          19 de Enero de 2022
                                                          
                                                          
# Proyecto                                                        
                                                         
En el dia de hoy he trabajado en el proyecto de arduino llamado molinillo motorizado con [Christian](https://github.com/Tabrih) y [David](https://github.com/DavidMenCam) 
  
## Resumen

Este proyecto consiste en hacer girar un molinillo de colores con un motor. Para ello usaremos transistores, motores, un diodo, etc...

Los transistores permiten controlar fuentes de alta corriente y alto voltaje desde la salida de baja corriente del Arduino, cosa que nos vendrá muy bien.

El motor conduce la energía al molinillo, el cual gracias a la energia que le proporciona el motor, logra girar, logrando así el objetivo del proyecto.


## Código

Aqui está el código del proyecto: 


```
const int switchPin = 2;
const int motorPin = 9;
int switchState = 0;
void setup() {
  pinMode(motorPin,OUTPUT);
  pinMode(switchPin,INPUT);
}
void loop(){
  switchState = digitalRead(switchPin);
  if (switchState == HIGH) {
    digitalWrite(motorPin, HIGH);
  }
  else {
    digitalWrite(motorPin, LOW);
  }
}
```



  
