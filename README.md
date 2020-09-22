# ARDUINO-NO7
這次的題目如下</p>

按一次開關</p>
STEP0 ○○○○○○○○</p>
STEP1 ●○○○○○○○</p>
STEP2 ○●○○○○○○</p>
STEP3 ○○●○○○○○</p>
STEP4 ○○○●○○○○</p>
STEP5 ○○○○●○○○</p>
STEP6 ○○○○○●○○</p>
STEP7 ○○○○○○●○</p>
STEP8 ○○○○○○○●</p>

再按一次開關</p>
STEP0 ○○○○○○○○</p>
STEP1 ○○○○○○○●</p>
STEP2 ○○○○○○●○</p>
STEP3 ○○○○○●○○</p>
STEP4 ○○○○●○○○</p>
STEP5 ○○○●○○○○</p>
STEP6 ○○●○○○○○</p>
STEP7 ○●○○○○○○</p>
STEP8 ●○○○○○○○</p>
STEP9 reset</p>

按第三次開關後完全不亮</p>

三個狀態循環</p>
程式如下</p>
```c++
void setup() {
  // put your setup code here, to run once:
  pinMode(2,INPUT);
  for(int i=3;i<11;i++)
  {
  pinMode(i,OUTPUT);
  digitalWrite(i,HIGH);
  }
}
int a =1;
void loop() {
  // put your main code here, to run repeatedly:

    if(digitalRead(2)==0)
    { 
      while(digitalRead(2)==0){delay(20);}
      a = a + 1;
      if(a>3)a = 1;
     
      
    }
switch(a)
{
  case 1:
{
 for(int f = 3;f>11;f++)
        {
          
          digitalWrite(f,HIGH);   
        }
    break;
}

  case 2:
  {
     for(int f = 11;f>=3;f--)
        {
          digitalWrite(f,LOW);
          delay(150);
          digitalWrite(f,HIGH);   
        }
break;
  }

    default :
    for(int f = 3;f>10;f++)
        {
          
          digitalWrite(f,HIGH);   
        }
case 3:
{
        for(int f = 3;f<=11;f++)
        {
          digitalWrite(f,LOW);
          delay(150);
          digitalWrite(f,HIGH);   
        }
   break;
}

}
}
```
