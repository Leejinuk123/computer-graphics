> ## 1. 프로세싱 그림판 펜 기능 구현하기
## 핵심 Keywords :
    line() : 좌표 함수
    pmouseX, pmouseY, mouseX(현재 마우스의 위치 X좌표), mouseY(현재 마우스의 Y위치 좌표)
    stroke(0,255,0) 펜의 색깔
    strokeWeight() 펜의 굵기
  

## 예제 1 : 
```processing
 void setup(){
  size(500,500);
  stroke(0,255,0); //color
  strokeWeight(16); //size pixel
}
void draw(){
  if(mousePressed)
      line(pmouseX,pmouseY,mouseX,mouseY);  
}
```


![제목 없음](https://user-images.githubusercontent.com/50895677/76850874-9d7a4400-688b-11ea-91d9-8172ca0e28cf.png)
