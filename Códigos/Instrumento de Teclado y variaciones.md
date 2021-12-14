
Original

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









































Variante 1


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

Variante Kill Switch



```C++
int switchState = 0;
bool isTheButtonBeingPressed = false;
bool play = false;
int buttonPin = 2;
int notes[] = {262,294,330,349,392,440};
void setup() {
  pinMode(buttonPin, INPUT);
  Serial.begin(9600);
}
void loop() {
 checkButton();
  if (play) {
    tocarPiano();
  }
}


void checkButton(){
  switchState = digitalRead(buttonPin);
  if (switchState == HIGH && !isTheButtonBeingPressed){
    play = !play;
    isTheButtonBeingPressed = true;
  }
  
  if (switchState == LOW)
  {
  isTheButtonBeingPressed = false;
  }

}
void tocarPiano(){
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


