# Primera Prueba

El programa ARDUINO IDE dió error: " can't open " " permission denied ".

El programa lanzó una excepción y detuvo el programa.
Esto por un tema de permisos de usuario.

![](https://github.com/Tabrih/Arduino/blob/main/Error%20arduino%201.png)

## Revisar Componentes Electricos

### Protoboard
El protoboard es el lugar principal en el que vais a construir circuitos. El que viene en vuestro kit es de tipo sin soldaduras, llamado asi porque no tenéis que soldar nada, algo así  como un kit de LEGO en forma electónico.
![](https://github.com/miguelamgel1107/Arduino/blob/main/arduino.png)
![](https://github.com/miguelamgel1107/Arduino/blob/main/unknown.png)
![](https://github.com/miguelamgel1107/Arduino/blob/main/unknown1)

# Circuitos Eléctricos

## Primeros Circuitos

### Circuito simple

5v---LED---GND

Ete pese a funcionar y dar luz genera dos problemas:

-1:Se calienta y es incómodo de tocar.

-2:Puede fundir el LED.

### Circuito en serie

Si desconectamos una parte no funciona

### Circuito en paralelo

Da igual si una parte se deconecta

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
