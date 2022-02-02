# Joystick

El dia de hoy eh trabjado junto con [David](https://github.com/DavidMenCam), hoy nos dieron un peuqeño joystick que teniamos que conectar al arduino para ver si funcionaba en condiciones .
con un codigo que revisa todas sus acciones en la herramienta de monitor serie. Eh aqui su codigo 

```c++

const int pinBoton = 3; 
const int pinEjeY = A1; 
const int pinEjeX = A0; 
 
void setup() {
  pinMode(pinBoton, INPUT);
  digitalWrite(pinBoton, HIGH);
  Serial.begin(9600);
}
 
void loop() {
  Serial.print("Boton:  ");
  Serial.print(digitalRead(pinBoton));
  Serial.print("\n");
  Serial.print("Eje X: ");
  Serial.print(analogRead(pinEjeX));
  Serial.print("\n"); //esto es un salto de linea
  Serial.print("Eje Y: ");
  Serial.println(analogRead(pinEjeY));
  Serial.print("\n\n");
  delay(150);
}
 ```
 y despues de eso hemos conectado 4 ñeds con la forma de joystick y hemos hecho que al mover el joystick hacia un lado brillara el led de ese lado y que cuando se pulsara el joystick todos los leds se encendieran.
 
 Eh aqui el codigo que hemos usado y un video de como funciona y como esta montado.
 
 
 ```c++
 const int pinBoton = 3; 
const int pinEjeY = A1; 
const int pinEjeX = A0; 
int valorEjeX;
int valorEjeY;
int swichState;
 
void setup() {
  

  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(6,OUTPUT);
  pinMode(7,OUTPUT);
  pinMode(3,INPUT);
  pinMode(pinBoton, INPUT);
  digitalWrite(pinBoton, HIGH);
  Serial.begin(9600);
}

 void joystick(){
  
  if (valorEjeX > 512 && valorEjeY < 512) {
    //led 1
    digitalWrite(4,HIGH);
    digitalWrite(5,LOW);
    digitalWrite(6,LOW);
    digitalWrite(7,LOW);
   
  }
  if (valorEjeX < 512 && valorEjeY > 512) {
    //led 2
    digitalWrite(4,LOW);
    digitalWrite(5,HIGH);
    digitalWrite(6,LOW);
    digitalWrite(7,LOW);
  }
    if (valorEjeY < 400 && valorEjeX > 450) {
    //led 3
     digitalWrite(7,HIGH);
    digitalWrite(6,LOW);
   digitalWrite(4,LOW);
    digitalWrite(5,LOW);
  }
  if (valorEjeX < 400 && valorEjeY > 450)
  {
    //led 4
    digitalWrite(6,HIGH);
     digitalWrite(7,LOW);
    digitalWrite(5,LOW);
    digitalWrite(4,LOW);}

 
}
void loop() {
  valorEjeX = analogRead(pinEjeX);
  valorEjeY = analogRead(pinEjeY);
  swichState = digitalRead(pinBoton);
  Serial.print("Boton:  ");
  Serial.print(swichState);
  Serial.print("\n");
  Serial.print("Eje X: ");
  Serial.print(valorEjeX);
  Serial.print("\n"); //esto es un salto de linea
  Serial.print("Eje Y: ");
  Serial.println(valorEjeY);
  Serial.print("\n\n");
  delay(150);
if (swichState == LOW){
  digitalWrite(4,HIGH);
    digitalWrite(5,HIGH);
    digitalWrite(6,HIGH);
    digitalWrite(7,HIGH);
}
else {
  joystick();0
}
  
}
```                  
                 
  [Enlace al codigo](https://github.com/DavidMenCam/Arduino/blob/main/C%C3%B3digos/joiystickvariante.ino)
  
  [Video de muestra](https://raw.githubusercontent.com/DavidMenCam/Arduino/main/VID_20220202_105511.mp4)
