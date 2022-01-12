# Proyecto

En el día de hoy, junto a [Christian](https://github.com/Tabrih) he hecho el proyecto Arduino llamado Bola de Cristal.

# Resumen

Este proyecto consiste en "imitar" una bola de cristal en nuestra protoboard a través de una pantalla lcd y así predecir nuestro futuro, como haría mismamente una bola de cristal. No únicamente usaremos una pantalla lcd, si no que también haremos servir un interruptor de inclinación o un potenciómetro, como ya hemos utilizado en anteriores proyectos. En nuestro caso hemos cambiado algunas de las respuestas que nos podría decir la bola ya que no nos gustaban o no cabian en la pantalla.

Por último hemos probado de utilizarla con un botón en vez de con un tilt sensor y sinceramente es más cómodo de usar.

# Fotos o Vídeos

- Montaje

![](https://github.com/Tabrih/Arduino/blob/main/Archivos/IMG_20220112_125450.jpg)

- Encendido

![](https://github.com/Tabrih/Arduino/blob/main/Archivos/IMG_20220112_125700.jpg)

- [Vídeo de como funciona](https://raw.githubusercontent.com/Tabrih/Arduino/main/Archivos/VID_20220112_125524.mp4)

## Variación con Botón

- Montaje

![](https://github.com/Tabrih/Arduino/blob/main/Archivos/IMG_20220112_125734.jpg)

- [Vídeo de como funciona](https://raw.githubusercontent.com/Tabrih/Arduino/main/Archivos/VID_20220112_125753.mp4)

# Código 

Aquí se encuentra el código de este proyecto:

```
#include <LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
const int switchPin = 6;
int switchState = 0;
int prevSwitchState = 0;
int reply;
void setup() {
  lcd.begin(16,2);
  pinMode(switchPin,INPUT);
  lcd.print("Que dice");
  lcd.setCursor(0, 1);
  lcd.print("la bola");
}
void loop(){
  switchState = digitalRead(switchPin);
  if (switchState != prevSwitchState) {
    if (switchState == LOW) {
      reply = random(8);
      lcd.clear();
      lcd.setCursor(0, 0);
      lcd.print("La bola dice:");
      lcd.setCursor(0, 1);
      switch(reply){
        case 0:
        lcd.print("Si");
        break;
         case 1:
        lcd.print("Probablemente");
        break;
         case 2:
        lcd.print("Desde Luego");
        break;
         case 3:
        lcd.print("Pinta bien");
        break;
         case 4:
        lcd.print("Pinta mal");
        break;
         case 5:
        lcd.print("Otra vez sera");
        break;
         case 6:
        lcd.print("Lo dudo");
        break;
         case 7:
        lcd.print("No");
        break;
      }
    }
  }
  prevSwitchState = switchState;
}
```
