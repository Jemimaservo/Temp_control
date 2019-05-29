# Temp_control
int ledgreen=7;
int ledyellow=5;
int ledred=9;
int tempsensor=A1;
int fan1=12;
int fan2=13;
void setup() {
  // put your setup code here, to run once:
  pinMode(ledgreen,OUTPUT);
  pinMode(ledyellow,OUTPUT);
  pinMode(ledred,OUTPUT);
  pinMode(fan1,OUTPUT);
  pinMode(fan2,OUTPUT);
  pinMode(tempsensor,INPUT);
  Serial.begin(9600);

}

void loop() {
  // put your main code here, to run repeatedly:
  float jemima= analogRead(tempsensor);
  jemima=(jemima*500)/1023;
  Serial.print("tempsensorin c:");
  Serial.println(jemima);
  if (jemima < 25.0) {
    digitalWrite(ledgreen,LOW);
    digitalWrite(ledyellow,HIGH);
    digitalWrite(ledred,LOW);
    digitalWrite(fan1,LOW);
    digitalWrite(fan2,LOW);

  }
else if (jemima >= 29.0 && jemima < 31.0) {
    digitalWrite(ledgreen,LOW);
    digitalWrite(ledyellow,LOW);
    digitalWrite(ledred,HIGH);
    digitalWrite(fan1,HIGH);
    digitalWrite(fan2,LOW);
}
else if (jemima >= 31.0) {
  digitalWrite(ledgreen,LOW);
    digitalWrite(ledyellow,LOW);
    digitalWrite(ledred,HIGH);
    digitalWrite(fan1,HIGH);
    digitalWrite(fan2,HIGH);
}

else {
  digitalWrite(ledgreen,HIGH);
    digitalWrite(ledyellow,LOW);
    digitalWrite(ledred,LOW);
    digitalWrite(fan1,LOW);
    digitalWrite(fan2,LOW);
}

}
