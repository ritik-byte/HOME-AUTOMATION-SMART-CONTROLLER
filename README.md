//# HOME-AUTOMATION-SMART-CONTROLLER
//We can oprate our home device through your smartphone ...we use aurdino microcontroller and bluetooth module

char val;
#define led1 2
#define led2 3
#define led3 4

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(led1,OUTPUT);
  pinMode(led2,OUTPUT);
  pinMode(led3,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  if (Serial.available())
  {
    val = Serial.read();
    Serial.println(val);
    if(val == 'A')
    digitalWrite(led1,HIGH);
    else if(val == 'a')
    digitalWrite(led1,LOW);
    else if(val == 'B')
    digitalWrite(led2,HIGH);
    else if(val == 'b')
    digitalWrite(led2,LOW);
    else if(val == 'C')
    digitalWrite(led3,HIGH); 
    else if(val == 'c')
    digitalWrite(led3,LOW); 
    }
}
