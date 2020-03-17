> ## 1. 프로세싱 그림판 펜 기능 구현하기
## 핵심 Keywords :
  line() : 좌표 함수
  pmouseX, pmouseY, mouseX, mouseY
  stroke(0,255,0) 펜의 색깔
  strokeWeight() 펜의 굵기


## 예제 1 : 
```processing
void setup(){
  size(500,500);
  
}
int h=0;
void draw(){
  background(0); //backgraound color 0=black 255=white
  fill(0,255,0); //R,G,B
  //ellipse(150,150,100,100);
  ellipse(250,h+=5,200,200);
  //h++ = h=h+1 = h+=1;
  //println(frameRate); //frame print
  
  if(h>500) h=0;
  
}
```
