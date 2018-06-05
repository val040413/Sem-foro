const int CAR_RED=12; //assign the car light
const int CAR_YELLOW=11;
const int CAR_GREEN=10;
const int PED_RED=9; // asing the pedestrian light
const int PED_GREEN=8;
const int BUTTON = 2; // button pin
int crossTime = 10000; //time alloyoud to cross
unsigned long changeTime; //time since BUTTON pressed
int state = LOW; //if is push button

void setup() {
  // put your setup code here, to run once:
  pinMode(CAR_RED,OUTPUT);
  pinMode(CAR_YELLOW,OUTPUT);
  pinMode(CAR_GREEN,OUTPUT);
  pinMode(PED_RED,OUTPUT);
  pinMode(PED_GREEN,OUTPUT);
  pinMode(BUTTON,INPUT); // button on pin 2
  //turn on the green light
  digitalWrite(CAR_GREEN,HIGH);
  digitalWrite(PED_RED,HIGH);
}

void loop() {
  // put your main code here, to run repeatedly:
  if (digitalRead(BUTTON)) //Change of state is button is pressed
    state = HIGH;
  if (state==HIGH && (millis()-changeTime)>crossTime) {
    changeLight();
    state = LOW;
  }
}

void changeLight(){
  digitalWrite(CAR_GREEN,LOW); //green off
  digitalWrite(CAR_YELLOW,HIGH);  //yellow on
  delay(2000); //wait 2 seconds
  digitalWrite(CAR_YELLOW,LOW); //green off
  digitalWrite(CAR_RED,HIGH);  //yellow on
  delay(2000); //wait 2 seconds
  digitalWrite(PED_RED,LOW); //green off
  digitalWrite(PED_GREEN,HIGH);  //yellow on
  delay(crossTime); //wait for 
  for (int i=0; i<10; i++){
    digitalWrite(PED_RED,HIGH);
    delay(250);
    digitalWrite(PED_GREEN,LOW);
    delay(250);
  }
  digitalWrite(PED_RED,HIGH);
  delay(500);
  digitalWrite(CAR_YELLOW,HIGH);
  digitalWrite(CAR_RED,LOW);
  delay(1000);
  digitalWrite(CAR_GREEN,HIGH);
  digitalWrite(CAR_YELLOW,LOW);

  //record the time size last change of lights
  changeTime = millis();
  //then return to the my program loop
}
