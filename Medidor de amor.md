# love-o-Meter
En el día de hoy he aprendido, junto a [Christian](https://github.com/Tabrih) y a [David](https://github.com/DavidMenCam), a realizar el love-o-meter.
## Resumen/Montaje

 Tal como lo ha estado haciendo en proyectos anteriores, conectar la placa de 
 pruebas a la alimentación y a masa.
 Conectar el cátodo (terminal corto) de cada diodo LED a masa a través de una 
 resistencia en serie de 220 ohmios. Conectar los ánodos de los LEDs  a los 
 terminales 2, 3 y 4 respectivamente. Estos diodos serán los indicadores de este 
 proyecto.
 Colocar el sensor de temperatura TMP36 sobre la placa de pruebas con la parte 
 curvada de su cuerpo mirando hacía el lado contrario de la placa Arduino (la 
 colocación de los terminales es importante) como se muestra en la figura 2. 
 Conectar el terminal de la izquierda de la cara plana del cuerpo a la alimentación 
 y el terminal derecho a masa. Conectar el pin central al pin A0 de la placa 
 Arduino. Este pin es la entrada analógica 0.
 
 ## El codigo 
 
 Las constantes son similares a las variables (guardar información) las cuales permiten usar
un único nombre con los datos del programa, pero a diferencia de las variables su 
contenido no se puede cambiar.

Dentro del bloque de la configuración “setup()” vamos a usar un nuevo comando, 
Serial.begin()

La siguiente instrucción for() define algunos de los pins como salidas digitales dentro de 
un bucle. Algunos de estos pins ya se han usado con los LEDs en el proyecto anterior. 

El siguiente bloque de código es el programa en sí, el cual comienza con la función loop(). 
Aquí se usa una variable llamada Valor_del_Sensor en donde se guarda la lectura del 
sensor.

[Codigo original](https://github.com/DavidMenCam/Arduino/blob/main/codigo_love_o_meter/codigo_love_o_meter.ino)


## Variaciones 

En esta variacion lo que hicimos fue quitar el sensor de temperatura y cambiarlo por un potenciometro haciendo que los LEDs se encendieran girando el potenciometro , aparte cambiamos en el codigo la temperatura por otro digitos del 0 al 1023

[Codigo de nustra variacion](https://github.com/DavidMenCam/Arduino/tree/main/variacion_02_love_meter)
