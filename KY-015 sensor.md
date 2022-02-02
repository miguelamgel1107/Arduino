# KY-015

El dia de hoy eh hecho un trabajo junto con [David](https://github.com/DavidMenCam) , 
primero de todo hemos entrado a una pagina de un objeto llamado ky.015 el cual es un sensor de temperatura y humedad.

Ahora usamos partes del codigo que habia en la pagina para ver en el monitor serie la humedad y temperatura que detecta el sensor.

Eh aqui el codigo usado.

```c++
#include "DHT.h"
const int sensor_pin_ky015 = 10;           
#define DHT1 DHT11

float humedad_ky015;                       
float temperatura_ky015;

DHT dht11(sensor_pin_ky015, DHT11); 

void setup() {

 Serial.begin(9600);


  dht11.begin (); 
}

void loop() {
  delay(2000);                             
  humedad_ky015 = dht11.readHumidity();            
  temperatura_ky015 = dht11.readTemperature();
  //Comprobamos si la lectura a fallado. La instruccion isnan, comprueba si la variable
  //que le pasamos tiene un valor representativo.  
  //Primero al dht11 incluido en la placa ky-015
   if (isnan(humedad_ky015) || isnan(temperatura_ky015)) {
   
    Serial.println ("Error de lectura en KY-015");   
  }
else {
   

    Serial.print("KY-015: ");               //mandamos texto al visor serie
    Serial.print("Humedad = ");             //mandamos texto al visor serie
    Serial.print(humedad_ky015,1);          //mandamos el valor medido de humedad con 1 decimal
    Serial.print(" %\t");                   //mandamos el simbolo % y un tabulador
    Serial.print("Temperatura = ");         //mandamos texto al visor serie
    Serial.print(temperatura_ky015,1);      //mandamos el valor medido de temperatura con 1 decimal
    Serial.println("ºC");                     //mandamos texto al visor serie
  }

}
```

Aqui una imagen de como va conectado el sensor al arduino.

 ![](https://github.com/DavidMenCam/Arduino/blob/main/IMG_20220202_123646.jpg?raw=true)
 
### Informacion extra :

Cuando la humedad sube mucho es bastante mas complicadio alterar la temperatura que recibe el sensor .
