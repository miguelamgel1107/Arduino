# Operaciones

IF (Variable y valor fijo), Si (True), No (False)

Output -> Stiven actívate

EJEMPLO :

Temperatura (15 ºC - 80 ºC)

Sensor Value (0 - 1024)

Se puede encadenar infinitas veces

  * Leer Pinao -> Analog Read -> 0 - 1023 (8 bytes)

  * Transforma los valores y, de regalo, las pinta en pantalla.
  
  * Decidir

Digital Write es una función que nos pide un número de pin y el valor HIGH(1) o LOW(0). Si el valor es HIGH, la placa suministrará 5 Voltios
en ese pin. Si el valor es LOW, la placa suministrará 0 voltios en ese pin. Si hay 5 voltios, se activarán los circuitos* Si es 0V no se activarán.


  * Depende del hardware y como esté conectado.

} else if ( temperature >= baselineTemp+2 && temperature < baselineTemp+4){


digitalWrite(2,HIGH),


digitalWrite(3,LOW),


digitalWrite(4,LOW),


} else if ( temperature >= baselineTemp+4 && temperature < baselineTemp+6){


digitalWrite(2,HIGH),


digitalWrite(3,HIGH),


digitalWrite(4,LOW),


} else if ( temperature >= baselineTemp+4)


digitalWrite(2,HIGH),


digitalWrite(3,HIGH),


digitalWrite(4,HIGH),
