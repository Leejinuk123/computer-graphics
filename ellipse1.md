> ## 1. 프로세싱 원 만들기 : 
## 핵심 Keywords 
    size : 팝업창의 사이즈를 결정한다.
    fill : ellipse의 색깔을 RGB로 결정한다.
    ellipse : 원을 그린다.
    
* * *

## 예제 1 : 
    
```processing
size(500,500); //popup size
fill(0,255,0); //ellipse color r,g,b
ellipse(250,250,250,250); //circle size
fill(0,0,255);
ellipse(0,0,500,500);
fill(255,0,0);
ellipse(500,500,500,500);
```

![주석 2020-03-16 201038](https://user-images.githubusercontent.com/50895677/76815287-8a8e5200-6840-11ea-8bdb-e8e4607ef2ab.png)


> ## 2. 프로세싱 원 움직이기
## 핵심 Keywords
    frameRate : 프레임을 출력해준다.
    background : 백그라운드 색깔을 정할 수 있다. 0=black 255=white

* * *

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
