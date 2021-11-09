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

