# Brushless code 
>int buttonState = 0;
int potensio = 0;
int saveData = 0;
int pinA = 7;
int pinB = 8;
int pwm = 9;
void setup()
{
  pinMode(2, INPUT);
  pinMode(7, OUTPUT);
  pinMode(8, OUTPUT);
}
void loop()
{
  buttonState = digitalRead(2);
  if(buttonState == LOW){
    right();
  }
  else{
    left();
  }
  delay(10);
}
void right()
{
  digitalWrite(pinA, LOW);
  digitalWrite(pinB, HIGH);
  saveData = analogRead(potensio);
  analogWrite(pwm, saveData);
  delay(15);
}
  void left()
{
  digitalWrite(pinA, HIGH);
  digitalWrite(pinB, LOW);
  saveData = analogRead(potensio);
  analogWrite(pwm, saveData);
  delay(15);
}
