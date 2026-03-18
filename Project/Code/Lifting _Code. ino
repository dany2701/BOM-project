#define BottomSensor   2  
#define TopSensor      3  
#define motorPin1      8  
#define motorPin2      7  
#define enable         9  
unsigned long timer = 0; 
bool motorRunning = false; 
void setup() {
  pinMode(BottomSensor, INPUT);
  pinMode(TopSensor, INPUT);
  pinMode(motorPin1, OUTPUT);
  pinMode(motorPin2, OUTPUT);
  pinMode(enable, OUTPUT);
}
void loop() {
  if(digitalRead(BottomSensor) == HIGH && !motorRunning){
    timer=millis();
    digitalWrite(motorPin1,HIGH);
    digitalWrite(motorPin2,LOW);
    analogWrite(enable,200);
    motorRunning = true;
  }
  if(digitalRead(TopSensor) == HIGH){
    digitalWrite(motorPin1,LOW);
    digitalWrite(motorPin2,LOW);
    analogWrite(enable,0);
    motorRunning = false;
  }
  if (millis() - timer > 170000 && motorRunning ) {
    digitalWrite(motorPin1, LOW);
    digitalWrite(motorPin2, LOW);
    analogWrite(enable, 0);
    motorRunning = false;
  }
}
