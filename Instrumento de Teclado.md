                                                 
# Proyecto

Hoy, junto a [Christian](https://github.com/Tabrih), he realizado el proyecto Arduino Instrumento de Teclado.

## Resumen

El proyecto consta de simular una especie de piano en la protoboard de Arduino, pero en este caso los botones harán de teclas. Pero solo con estos no podríamos hacer nada, necesitaremos el código Arduino del mismo para poderlo hacer funcionar. Con ambos correctos y funcionando podríamos hacer uso de él ya, e incluso ir probando variaciones de las frecuencias de las notas para hacer ritmos distintos.

Probamos a hacer una variación con 6 botones en vez de 4, y nos dimos cuenta que, al probar distintas frecuencias de notas, las frecuencias más bajas prácticamente no se escuchaban. Mejor dicho, las frecuencias músicales se dividen por octavas, exactamente 8, que se miden en Hz. Estás van desde los 16,3516 Hz a 7902,14 Hz, divididas entre las octavas que hemos comentado antes. En nuestro caso hemos escogido la mayoría de la octava 4, que van desde 261,626 Hz hasta 493,893 y se suelen escuchar bien.


## Código

Código Original:

```C++
int notes[] = {262,294,330,349};
void setup() {
  Serial.begin(9600);
}
void loop() {
  int keyVal = analogRead(A0);
  Serial.println(keyVal);
  if(keyVal == 1023){
    tone(8, notes[0]);
  }
else if(keyVal++ >= 990 && keyVal <= 1010){
  tone(8, notes[1],);
}
else if(keyVal >= 505 && keyVal <= 515){
  tone(8, notes[2]);
}
else if(keyVal >= 5 && keyVal <= 10){
  tone(8, notes[3]);
}
else{
  noTone(8);
}
}
```

Código Variante 1:

```C++

int notes[] = {262,294,330,349,392,440};
void setup() {
  Serial.begin(9600);
}
void loop() {
  int keyVal = analogRead(A0);
  Serial.println(keyVal);
  if(keyVal == 1023){
    tone(8, notes[0]);
  }
else if(keyVal++ >= 976 && keyVal <= 1009){
  tone(8, notes[5],20);
}
else if(keyVal >= 505 && keyVal <= 515){
  tone(8, notes[2]);
}
else if(keyVal >= 5 && keyVal <= 10){
  tone(8, notes[1]);
}
else if(keyVal >= 690 && keyVal <= 700){
  tone(8, notes[3]);
}
else if(keyVal >= 960 && keyVal <= 975){
  tone(8, notes[4]);
}
else if(keyVal >=1010 && keyVal <= 1023){
  tone(8, notes[6]);
}
else{
  noTone(8);
}
}

```

## Imágenes y vídeos

### Instrumento de Teclado original

![](https://github.com/Tabrih/Arduino/blob/main/Archivos/IMG_20211214_105502.jpg)

[Vídeo del Instrumento de Teclado](https://raw.githubusercontent.com/Tabrih/Arduino/main/Archivos/VID_20211214_105519.mp4)



### Variación 1 del Instrumento de Teclado

![](https://github.com/miguelamgel1107/Arduino/blob/main/Archivos/IMG_20211214_121155.jpg)

[Vídeo de la variante del Instrumento de Teclado con 6 teclas](https://raw.githubusercontent.com/miguelamgel1107/Arduino/main/Archivos/VID_20211214_121205.mp4)
