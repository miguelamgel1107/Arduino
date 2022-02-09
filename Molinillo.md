
                                                                                                                  
# Proyecto                                                        

En el dia de hoy he trabajado en el proyecto de arduino llamado molinillo motorizado con [David](https://github.com/DavidMenCam) y [Miguel Ángel](https://github.com/miguelamgel1107) .

## Resumen

Este proyecto consiste en hacer girar un molinillo de colores con un motor. Para ello usaremos transistores, motores, un diodo, etc...

Los transistores permiten controlar fuentes de alta corriente y alto voltaje desde la salida de baja corriente del Arduino, cosa que nos vendrá muy bien.

El motor conduce la energía al molinillo, el cual gracias a la energia que le proporciona el motor, logra girar, logrando así el objetivo del proyecto.


## Código

Aqui está el código del proyecto: 


```C++
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
## Imágenes o Vídeos

Aquí tenéis una imagen del proyecto:

![](https://github.com/Tabrih/Arduino/blob/main/Archivos/IMG_20220119_101936.jpg)

[Y aquí tenéis el vídeo del mismo](https://raw.githubusercontent.com/Tabrih/Arduino/main/Archivos/VID_20220119_102053.mp4)
