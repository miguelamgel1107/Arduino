## SNIPPET

Este proyecto lo hice junto a [David](https://github.com/DavidMenCam)

Comenzamos con el mismo concepto y codigo que el de la lampara de colores Con el mimso codigo  todo haciendo que la luz cambiara de color con los potenciadores 

Tuvimos algunos problemas pero despues del codigo  empezamos cambieando el codigo actual .

Cambiamos el codigo original combinandolo con el codigo de [Chechiliaa](https://github.com/chechiliaa) de [Snippet del botón malote](https://github.com/chechiliaa/arduino/blob/main/snippet_kill_switch.cpp)
En el hardware agregamos un boton y lo conectamos al pin 2 y al GND.
En el codigo tuvimos un problema que cuando apagamos el boton el led se quedaba encendido asi que tuvimos que agregar un void con la funcion de apagar el boton y agregarlo al loop asi arreglamos el problema.
lo que hace el codigo es que el circuito funciona igual pero con el cambio que si el boton esta encendido el circuito esta encendido y si esta apagado el circuito se apaga.

aqui esta el codigo modificado.

```const int greenLEDPin = 9;
const int redLEDPin = 11;
const int blueLEDPin = 10;
const int redSensorPin = A0;
const int greenSensorPin = A1;
const int blueSensorPin = A2;
int redValue = 0;
int greenValue = 0;
int blueValue = 0;
int redSensorValue = 0;
int greenSensorValue = 0;
int blueSensorValue = 0;
int switchState = 0;
bool isTheButtonBeingPressed = false;
bool play = false;
int buttonPin = 2;

void setup() {
  Serial.begin(9600);
  pinMode(buttonPin, INPUT);
  pinMode(greenLEDPin,OUTPUT);
  pinMode(redLEDPin,OUTPUT);
  pinMode(blueLEDPin,OUTPUT);
}
void encenderLampara(){
redSensorValue = analogRead(redSensorPin);
  delay(5);
  greenSensorValue = analogRead(greenSensorPin);
  delay(5);
  blueSensorValue = analogRead(blueSensorPin);
  Serial.print("Raw Sensor Values \t Red: ");
  Serial.print(redSensorValue);
  Serial.print("\t Green: ");
  Serial.print(greenSensorValue);
  Serial.print("\t Blue: ");
  Serial.print(blueSensorValue);
  redValue = redSensorValue/4;
  greenValue = greenSensorValue/4;
  blueValue = blueSensorValue/4;
  Serial.print("Mapped Sensor Values \t Red: ");
  Serial.print(redValue);
  Serial.print("\t Green: ");
  Serial.print(greenValue);
  Serial.print("\t Blue: ");
  Serial.println(blueValue);
  analogWrite(redLEDPin, redValue);
  analogWrite(greenLEDPin, greenValue);
  analogWrite(blueLEDPin, blueValue);
  }
void apagarLampara(){
   analogWrite(redLEDPin, 0);
  analogWrite(greenLEDPin, 0);
  analogWrite(blueLEDPin, 0);
}
void loop() {
 checkButton();
  if (play) {
     encenderLampara();}
  else {
    apagarLampara();
    }  
}
void checkButton(){
  switchState = digitalRead(buttonPin);
  Serial.println(switchState);
 if (switchState == HIGH && !isTheButtonBeingPressed){
    play = !play;
    isTheButtonBeingPressed = true;
  }
  if (switchState == LOW)
  {
  isTheButtonBeingPressed = false;
  }
}
