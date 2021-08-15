#include<Servo.h>


Servo ts;
Servo mp;
Servo ss;
Servo st;

const int coilbelt = 3;
const int coilmotor = 4;
const int relay_coil = 5;
const int stirmotor = 6;
int Signal;


const int tss;
const int mps;
const int sss;
const int sts;

void setup(){

 pinMode(coilbelt,OUTPUT);
 pinMode(coilmotor,OUTPUT);
 pinMode(relay_coil,OUTPUT);
 pinMode(stirmotor,OUTPUT);

 ts.attach(8);
 mp.attach(9);
 ss.attach(10);
 st.attach(11);
 
ts.write(180);
mp.write(180);
ss.write(180);
st.write(180); 

int tss = analogRead(A0);
int mps = analogRead(A1);
int sss = analogRead(A2);
int sts = analogRead(A3);


int Signal= digitalRead(7);
}
void loop(){

if (Signal=HIGH) {

digitalwrite(coilbelt,HIGH);

if(tss=HIGH){

digitalwrite(coilbelt,LOW);  
ts.write(90);
delay(1000);
ts.write(180);
}
else{
digitalwrite(coilbelt,HIGH);
}  

if(mps=HIGH){
digitalwrite(coilbelt,LOW);  
mp.write(90);
delay(1000);
mp.write(180);
}
else{
digitalwrite(coilbelt,HIGH);
}


if(sss=HIGH){
digitalwrite(coilbelt,LOW);  
ss.write(90);
delay(1000);
ss.write(180);
}
else{
digitalwrite(coilbelt,HIGH);
}  


if(sts=HIGH){
  digitalwrite(coilbelt,LOW);
  digitalwrite(stirmotor,HIGH);

  st.write(90);
  delay(5000);
  st.write(135);
  delay(2500);
  st.write(75);  
  delay(3000);
  digitalwrite(stirmotor,LOW);
}
else{
  digitalwrite(coilmotor,HIGH);  
} 
}
}
