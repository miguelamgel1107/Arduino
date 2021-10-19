# Primera Prueba
Intentamos programar el programa de ejemplo blink.ino pero no habia permiso para programar por el USB: ARV dude: Lanzó una excepcion y detuvo el programa, lo que ocurrió fue que el programa que habla con el USB no tenia permisos. 

![](https://github.com/Tabrih/Arduino/blob/main/Error%20arduino%201.png)

## Revisar Componentes Electricos

### Protoboard
El protoboard es el lugar principal en el que vais a construir circuitos. El que viene en vuestro kit es de tipo sin soldaduras, llamado asi porque no tenéis que soldar nada, algo así  como un kit de LEGO en forma electónico.

# Circuitos Eléctricos

## Primeros Circuitos

### Circuito simple

5v---LED---GND

Este pese a funcionar y dar luz genera dos problemas:

-1:Se calienta y es incómodo de tocar.

-2:Puede fundir el LED.

### Circuito con boton
![](https://github.com/miguelamgel1107/Arduino/blob/main/arduino.png)

### Circuito en serie

Si desconectamos una parte no funciona

![](https://raw.githubusercontent.com/Tabrih/Arduino/main/IMG_20211006_124850.jpg)

Fuente:[Christian](https://github.com/Tabrih)

### Circuito en paralelo

Da igual si una parte se desconecta

![](https://raw.githubusercontent.com/Tabrih/Arduino/main/IMG_20211006_123213.jpg)

Fuente:[Christian](https://github.com/Tabrih)

### Circuito en serie 2

![](https://github.com/miguelamgel1107/Arduino/blob/main/unknown.png)
![](https://github.com/miguelamgel1107/Arduino/blob/main/unknown1)

### Circuito en paralelo 2

![](https://github.com/Tabrih/Arduino/blob/main/IMG_20211006_135736.jpg)
![](https://github.com/Tabrih/Arduino/blob/main/IMG_20211006_135739.jpg)
![](https://github.com/Tabrih/Arduino/blob/main/IMG_20211006_135745.jpg)

## Apuntes Sobre Electricidad

Voltaje --> Altura (Diferencia de potencial)

Intensidad o Amperaje --> cantidad de agua o rotuladores

Resistencia --> Resistencia al paso del agua o rotulador

Intensidad = Voltaje ÷ Resistencia ---> Ley de Ohm

Voltaje = Intesidad x Voltaje

Resistencia = Voltaje ÷ Intensidad

### Por qué necesitamos resistencias con los LEDs?

Tenemos 2 circuitos

Circuito 1 : 5V,GND 0V

Circuito 2 : 5V, bombilla, GND 0V

El voltaje de los dos circuitos es 5V.

Y la resistencia? Circuito 1, 1 Ohm Circuito 2 440 Ohms

5V ÷ 441 Ohms = 0,01133 A = 11,33 mA

5V ÷ 1 Ohm = 5 A

5V ÷ 0 Ohm = ∞ A (Cortocircuito) ---> Evitar

## Morse y las funciones

-Aqui podemos ver lo que hicimos en la prueba de Morse_1.

![](https://github.com/DavidMenCam/Arduino/blob/main/Captura%20de%20pantalla%20de%202021-10-13%2012-49-56.png)

-Aqui esta el enlace a lo que hicimos en la prueba de [Morse_2](https://github.com/DavidMenCam/Arduino/blob/main/morse_2/morse_2.ino)

-Aqui esta el enlace a lo que hicimos en la prueba de [Morse_3](https://github.com/DavidMenCam/Arduino/blob/main/morse_3/morse_3.ino)

### Alfabeto en codigo morse 

![](https://github.com/miguelamgel1107/Arduino/blob/main/img_como_es_el_alfabeto_morse_15589_600.jpg)

## Como Programar Arduino

-Primero tenemos arduino ide instalado.
-Tenemos un usuario con permisos.
-Conectamos el arduino por USB.
-Cargamos el programa blink.ino. Archivo-ejemplos-1.basics-blink
-Pulsamos el botón subir.
