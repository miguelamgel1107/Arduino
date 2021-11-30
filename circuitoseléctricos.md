# Circuitos Eléctricos

Los circuitos eléctricos se representan mediantes esquemas que permiten entender que elementos hay y su conexión entre sí. Para ello se usan símbolos.

   * Enlace circuitos eléctricos
   * Qué habéis dibujado
   * Qué es un condensador

## Include < servo.h

Los include son otros trozos de código

También conocidos como bibliotecas o librerías (library)

Se introducen al principio del código con la fórmula #include <nombre.h>

Otros lenguajes usan la palabra import

Servo my serve ;

Servo → Esto es un OBJETO instancia de en una VARIABLE

Los objetos tienen propiedades y métodos

Las propiedades son variables ( u objetos) que son sus atributos

Los objetos son funciones que pueden realizar

my Servo attach → método (9 → argumento)

PROGRAMA

Leer inputs → Procesar inputs → Sacar output

analogRead 0 - 1023 0 = 0V 1023 = 5V

angle = map (potVal, 0, 1023, 0, 179)

1r valor → valor a mapear ( potVal)

2do y 3r valor → intervalo (mínimo y máximo) de entrada

4to y 5to valor → intervalo (mínimo y máximo) de salida

potVAL → angle myServo.write(angle); (método)

0 → 0

1023 → 179

512 → 89
