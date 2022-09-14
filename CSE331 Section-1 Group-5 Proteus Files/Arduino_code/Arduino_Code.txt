int pinOut1 = 5;
int pinOut2 = 4;
int pinOut3 = 3;
int pinOut4 = 2;
int pinA = 11;
int pinB = 10;
int pinC = 9;
int pinD = 8;
void setup()
{
pinMode(pinOut1, OUTPUT);
pinMode(pinOut2, OUTPUT);
pinMode(pinOut3, OUTPUT);
pinMode(pinOut4, OUTPUT);
pinMode(pinA, INPUT);
pinMode(pinB, INPUT);
pinMode(pinC, INPUT);
pinMode(pinD, INPUT);
 
 
}
void loop()
{
boolean pinAState = digitalRead(pinA);
boolean pinBState = digitalRead(pinB);
boolean pinCState = digitalRead(pinC);
boolean pinDState = digitalRead(pinD);
boolean pinorOutState;
boolean pinorOutState1;
boolean pinorOutState2;
boolean pinorOutState3;
pinorOutState =((!pinAState)&(!pinCState)&(!pinDState))|((!pinBState)&(pinCState)&(pinDState))|((pinAState)&(pinBState)&(pinCState))|((pinAState)&(pinBState)&(pinDState));
digitalWrite(pinOut1, pinorOutState);
pinorOutState1 =((!pinAState)&(pinBState)&(!pinCState))|((pinAState)&(pinBState)&(pinDState))|((pinCState)&(!pinDState))|((pinAState)&(pinCState));
digitalWrite(pinOut2, pinorOutState1);
pinorOutState2 =
((!pinAState)&(!pinBState)&(!pinCState))|((!pinAState)&(!pinDState))|((!pinAState)&(pinBState)&(pinCState))|((!pinBState)&(!pinDState));
digitalWrite(pinOut3, pinorOutState2);
 
 
pinorOutState3 =
((!pinAState)&(!pinBState)&(!pinCState)&(pinDState))|((!pinAState)&(!pinBState)&(pinCState)&(!pinDState))|((pinAState)&(pinBState)&(pinCState)&(!pinDState))|((pinAState)&(!pinBState)&(!pinCState)&(!pinDState))|((pinAState)&(!pinBState)&(pinCState)&(pinDState));
digitalWrite(pinOut4, pinorOutState3);
}
