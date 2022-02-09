# Proyecto

En el día de hoy, junto a [David](https://github.com/DavidMenCam) y [Chritian](https://github.com/Tabrih), hemos trabajado en el proyecto de Arduino llama Zoótropo.

## Resumen 

El proyecto consiste en crear imágenes en movimientos conectando un motor a un puenteH y algunas imágenes fijas.

Los puentes H son un tipo de componente comúnmente llamado Circuito integrado. Ayudan a simpiflicar circuitos más complejos al colocarlos en un comoponente fácil de reemplazar.

## Código

Aquí tenéis el código del proyecto:

```C++
const int controlPin1 = 2;
const int controlPin2 = 3;
const int enablePin = 9;
const int directionSwitchPin = 4;
const int onOffSwitchStateSwitchPin = 5;
const int potPin = A0;

int onOffSwitchState = 0;
int previousOnOffSwitchState = 0;
int directionSwitchState = 0;
int previousDirectionSwitchState =0;
int motorEnabled = 0;
int motorSpeed = 0;

int motorDirection = 1;
void setup(){ 
  pinMode(directionSwitchPin, INPUT);
  pinMode(onOffSwitchStateSwitchPin, INPUT);
  pinMode(controlPin1, OUTPUT);
  pinMode(controlPin2, OUTPUT);
  pinMode(enablePin, OUTPUT);
  digitalWrite(enablePin, LOW);
  Serial.begin(9600);
}
void loop(){
  onOffSwitchState = digitalRead(onOffSwitchStateSwitchPin);
  delay(1);
  directionSwitchState = digitalRead(directionSwitchPin);
  motorSpeed = analogRead(potPin)/4;
  Serial.println("Valor del botón On/OFf:");
  Serial.println(onOffSwitchState);
  Serial.println("Valor del botón Dirección:");
  Serial.println(directionSwitchState);
    Serial.println("Valor de la velocidad:");
  Serial.println(motorSpeed);
  if(onOffSwitchState != previousOnOffSwitchState){
    if(onOffSwitchState == HIGH){
      motorEnabled = !motorEnabled;
    }
  }
  if (directionSwitchState !=
  previousDirectionSwitchState) {
  if (directionSwitchState == HIGH) {
    motorDirection = !motorDirection;
    }
  }
  if(motorDirection ==1) {
    digitalWrite(controlPin1, HIGH);
    digitalWrite(controlPin2, LOW);
  }
  else {
    digitalWrite(controlPin1,LOW);
    digitalWrite(controlPin2,HIGH); 
  }
  if (motorEnabled == 1) {
    analogWrite(enablePin, motorSpeed);
  }
  else {
    analogWrite(enablePin, 0);
  }
  previousDirectionSwitchState =

```


# Imágenes

En este caso la imagen es de [Stiven](https://github.com/St1v3n3223/) ya que no encontré la mía, pero sirve igual:

![](https://raw.githubusercontent.com/St1v3n3223/Arduino/main/WhatsApp%20Image%202022-01-19%20at%2012.49.39.jpeg)
