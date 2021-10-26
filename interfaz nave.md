# Proyecto Interfaz Nave 
En el día de hoy he aprendido, junto a [Christian](https://github.com/Tabrih) y a [David](https://github.com/DavidMenCam), a realizar la interfaz de nave espacial.
## Resumen / Montaje 

Ahora os explicaré, tanto por texto como por fotos como aprendimos a hacerlo.

En nuestro caso, la LED de la izquierda permanecerá encendida hasta que pulse el botón. Cuando Arduino reciba la señal del botón pulsado, la luz de la izquierda se apaga y se encienden otras dos luces que comienzan a parpadear.

Conectar la placa de pruebas a las conexiones de 5V y masa de Arduino. Colocar los dos diodos LED sobre la placa de pruebas. Conectar el cátodo (patilla corta) de cada LED masa a través de una resistencia de 220 ohmios. Conectar el ánodo (patilla larga) del LED de la izquierda al pin 3 de Arduino. Conectar los ánodos de los otros dos LEDs a los pins 4 y 5 respectivamente.

Colocar el pulsador sobre la placa de pruebas. Conectar un extremo a la alimentación y el otro terminal del pulsador al 2 de Arduino. También necesita añadir una resistencia de 10K ohmios desde masa al pin del interruptor que va conectado a Arduino. Esta resistencia de puesta a cero conecta el pin a masa cuando el pulsador está abierto, así que Arduino lee LOW cuando no hay tensión en ese pin del pulsador.

Para crear una variable, es necesario declarar de que tipo se trata. Una variable de tipo int guardará un numero entero (también llamado integer); eso significa que almacena cualquier número sin decimales. Cuando se declara una variable, normalmente también se le asigna a la vez un valor inicial. Las declaraciones de la variables siempre deben de finalizar con un punto y coma (;). La función setup() solo se ejecuta una vez, cuando Arduino recibe la alimentación para funcionar. Esta función define un bloque, el cual se abre con una llave “{“ y se cierra con otra llave “}”, en donde se escriben las instrucciones que configuran los pins digitales de Arduino como entradas o como salidas, usando para ello una función llamada pindMode(). Los pins conectados a los LEDs serán OUTPUTs y el pin de un pulsador será una INPUT. La función loop() se ejecuta continuamente después de que la función setup() se haya completado. A través de las instrucciones que se incluyen dentro del bloque después de la función loop() es donde se comprobará el voltaje de las entradas y si las salidas están activadas o desactivadas. Para verificar el nivel de voltaje de una entrada digital, se utiliza la función digitalRead() la cual comprueba el voltaje en el pin elegido. Para saber que pin debe de verificar digitalRead() espera un argumento. Los argumentos son información que se le pasa a las funciones diciéndoles como deben de realizar su trabajo. Por ejemplo, digitalRead() necesita un argumento: que pin debe verificar. En el programa de Interface de la Nave Espacial, digitalRead() va a verificar el estado del pin 2 para después almacenar el valor dentro de la variable switchState. Si hay voltaje en el pin 2 cuando digitalRead() es llamada, entonces la variable switchState almacena un valor HIGH (o 1). Si no hay voltaje en el pin 2, switchState almacenará el valor LOW (o 0).

## Codigo 

[Este es el codigo de el arudino de la interfaz de la nave ](https://github.com/DavidMenCam/Arduino/blob/main/variacion%201/lo_o_ko_k_l.ino)

[video del interfaz en funcionamiento](https://youtu.be/ey4Wmv3uzh4)

## Variaciones

En esta variacion invertimos el funcionamiento del arduino ahora cuando el boton no esta pulsado los LEDs parpadean continuamente y cuando se pulsa el boton dejan de parpadear y el primer Led queda encendido.

[Variacion 1](https://github.com/DavidMenCam/Arduino/blob/main/variacion%202/low.ino)

y aqui esta el ejemplo en video para que lo podais ver 

[Variacion 1 video](https://www.youtube.com/watch?v=Sl5UKPwK2mo)


En la ultima añadimos un cuato led y repetimos el funcionamiento de la variacion 1 , la diferencia es que tenia un Led de mas 

[Codido de la ultima variacion ]()

[Video de la ultima variacion](https://youtu.be/B4rhuzqbJ8I)

