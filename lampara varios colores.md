## PWM (Pulse width modulation o Modulación por ancho de pulsos)

PROBLEMA : Tengo un arduino que suministra 5V a un LED ¿Cómo lo resuelvo? Con pulsos.

A mayor intensidad de corriente (A--> Amperios) el LED brilla más.

A menor intesidad de corriente el LED brilla menos. (Ver ley de Ohm)

Intensidad = Voltaje entre Resistencia

Si subimos o bajamos el voltaje, haremos lo mismo con la intensidad, suponiendo que la resistencia del circuito es la misma.

Entonces si conecto un LED con su resistencia de 220 Ohmnios a un voltaje de 5V o de 3,3V el LED brillará más con 5V y menos con 3,3V.

PULSOS -> Es una señal eléctrica

### Que es un pulso 

Un pulso eléctrico es una señal de voltaje medida en el tiempo.

Los ojos humanos pueden detectar cambios hasta en torno a 12 Herzios, a partir de 24 o 30 Herzios no son capaces.

Los pulsos modulados en ancho crean la ilusión de voltajes intermedios entre 0 y 5V. 
Para ello usan pulsos muy cortos que usaremos a través de la función Analog Write. 
Esta función solo funciona en pines con PWM.

Los pines con PWM están marcados con el símbolo ~ (tilde de la Ñ).

La función nos pide dos cosas :

- Por un lado ( y lo primero), el número de pin

- Por otro lado , un número entre 0 y 255

O significa 0% de voltaje, 255 significa 100% de voltaje (5V)

int = integer o número entero  

int significa que muestra variables en un tipos de dato númerico no decimal. Le asigna un espacio en memoria 

Otros tipos : 

- string -> Cadena de caracteres
- bool -> boleano y es verdadero (true) o falso (false)
- char -> un único caracter
- float -> números decimales

## Lampara de colores
Este proyecto lo realicé junto a David y Christian.

Para este proyecto necesitamos 3 fototransistores que detectan la luz, cada fototransistor sera un color, vamos a tener uno rojo otro azul y otro verde.
Dependiendo de la cantidad de luz que detecte el fototransistor sera la potencia que brille ese color.

[Aqui esta el codigo](https://github.com/DavidMenCam/Arduino/blob/main/arduino_ver_7.ino)

* Variable 1

Luego realizamos una varienate usando el mismo codigo petro cambiando los fototransistores por unos potenciadores para asi poder regular mejor la potencia que queremos que brille cada color.

Aqui una imagen para mostrar como se monta el circuito.

![](https://github.com/miguelamgel1107/Arduino/blob/main/IMG20211103140539.jpg)

* variable 2

Luego realizamos esta variable, la cual consistía en dos grandes cambios en el código y en protoboard:

En el código, el greenValue probamos a ponerle un valor de 10, así igual en blue y redValue.

En la protoboard, cambiamos los potenciadores por botones y, al mantenerlos pulsados, los LEDs se iluminan lentamente y al llegar a un punto determinado de brillo se apagan automáticamente.

[Este es el codigo de esta variante](https://github.com/DavidMenCam/Arduino/blob/main/lampara_colores_variacion1/lampara_colores_variacion1.ino)

![](https://github.com/miguelamgel1107/Arduino/blob/main/IMG20211109134734.jpg)
